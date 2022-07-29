FROM ubuntu:20.04

ENV PATH="$PATH:/usr/local/USD/bin"
ENV PYTHONPATH="$PYTHONPATH:/usr/local/USD/lib/python"
ENV LIBGL_ALWAYS_SOFTWARE=1

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \ 
	build-essential \
	cmake \
	git \
	libglew-dev \
        libglib2.0-0 \
	libx11-dev \
	python \
	python3 \
        python3-dev \
 	python3-pip \
        python3-pyqt5 \
        python3-numpy && \
    rm -rf /var/lib/apt/lists/*


RUN pip3 install --no-cache-dir PySide2 PyOpenGL jinja2

RUN git clone https://github.com/PixarAnimationStudios/USD
    
RUN python3 USD/build_scripts/build_usd.py /usr/local/USD

WORKDIR /opt/

CMD ["/bin/bash"]
