FROM resin/rpi-raspbian:stretch

ENTRYPOINT []

# System packages
RUN apt-get update; apt-get upgrade -y 
RUN apt-get install -y \
    libpq-dev \
    wget   \
    apt-utils \
    alsa-base \
    alsa-utils \
    git \
    build-essential \
    curl \
    libcurl4-openssl-dev \
    libssl-dev uuid-dev \
    portaudio19-dev \
    libblas-dev \
    liblapack-dev \
    libatlas-base-dev \
    bzip2 \
    python3.4 \
    python-pip \
    libboost-all-dev \ 
    cython \
&& rm -rf /var/lib/apt/lists/*

# Install miniconda to /miniconda
RUN curl -LO http://repo.continuum.io/miniconda/Miniconda-latest-Linux-armv7l.sh
RUN bash Miniconda-latest-Linux-armv7l.sh -p /miniconda -b
RUN rm Miniconda-latest-Linux-armv7l.sh
ENV PATH=/miniconda/bin:${PATH}
RUN conda update -y conda

# Build numpy from source - This is required for latest TensorFlow (ML package)!
RUN git clone https://github.com/numpy/numpy.git numpy
RUN cd numpy; git checkout v1.14.2
RUN cd numpy; python setup.py install --user

