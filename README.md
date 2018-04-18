# Usable Docker for IoT Devices
This repo contains re-usable Docker Images for IoT Devices. Currently i have pushed set of dockerfile images that is needed to get started faster on raspberry pi based iot devices.

# Overview

On each folder, i have a created a docker file that targets different image configurations based on your needs. Here is the details:

1. **rpi-stretch-miniconda**:
This is a dockerfile that contains miniconda in addition to system packages for Microsoft IoT Hub, Python 2.7 and more. 

2. **rpi-stretch-miniconda3**:
This is a dockerfile that contains miniconda 3 in addition to system packages for Microsoft IoT Hub, Python 3.4 and more. 

3. **rpi-stretch-miniconda-numpy**:
This is a dockerfile that contains miniconda in addition to system packages for Microsoft IoT Hub, Python 2.7, numpy and more.  This is useful if you are planning to use Machine Learning libraries such as: TensorFlow which requires numpy. The reason for compiling numpy from source is due to issues running TF using pip install numpy or conda install numpy on the Raspberry PI.

4. **rpi-stretch-miniconda3-numpy**:
This is a dockerfile that contains miniconda 3 in addition to system packages for Microsoft IoT Hub, Python 3.4, numpy and more.  This is useful if you are planning to use Machine Learning libraries such as: TensorFlow which requires numpy. The reason for compiling numpy from source is due to issues running TF using pip install numpy or conda install numpy on the Raspberry PI.
