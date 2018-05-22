FROM resin/rpi-raspbian:stretch

ENTRYPOINT []

# system packages for python 3.5 and pyinstaller
RUN sudo apt-get -y update
RUN sudo apt-get upgrade
RUN sudo apt-get -y install python3.5 python3-pip 
# packages for fetching from github repos
RUN sudo apt-get install git curl 

# requirements for pyinstaller
RUN sudo apt-get install -y build-essential python3-dev

# NeoPixel LED packages prerequisites 
RUN sudo apt-get install -y scons swig cython
RUN pip3 install setuptools

# Install NeoPixel
WORKDIR /rpi_ws281x
RUN git clone https://github.com/jgarff/rpi_ws281x .
RUN sudo scons
WORKDIR python
RUN python3 setup.py build
RUN python3 setup.py install

# Install miniconda to /miniconda
RUN curl -LO http://repo.continuum.io/miniconda/Miniconda3-latest-Linux-armv7l.sh
RUN bash Miniconda3-latest-Linux-armv7l.sh -p /miniconda -b
RUN rm Miniconda3-latest-Linux-armv7l.sh
ENV PATH=/miniconda/bin:${PATH}
RUN conda update -y conda

# build numpy from source - This is required for latest TensorFlow!
RUN git clone https://github.com/numpy/numpy.git numpy
RUN cd numpy; git checkout v1.14.2
RUN cd numpy; python3 setup.py install --user