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
RUN curl -LO http://repo.continuum.io/miniconda/Miniconda3-latest-Linux-armv7l.sh
RUN bash Miniconda3-latest-Linux-armv7l.sh -p /miniconda -b
RUN rm Miniconda3-latest-Linux-armv7l.sh
ENV PATH=/miniconda/bin:${PATH}
RUN conda update -y conda


