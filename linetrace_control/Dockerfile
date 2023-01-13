FROM python:3.9.10-slim-buster

RUN apt-get update
RUN apt-get install -y libopencv-dev
RUN pip install numpy --upgrade
RUN pip install opencv-python==4.5.5.64
RUN pip install opencv-contrib-python==4.5.5.64
RUN pip install djitellopy==2.4.0

RUN apt-get install -y patch
COPY djitellopy.patch tmp/djitellopy.patch
RUN patch usr/local/lib/python3.9/site-packages/djitellopy/tello.py < tmp/djitellopy.patch

COPY controller.py controller.py
