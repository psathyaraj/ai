FROM ubuntu:16.04

MAINTAINER Prowareness(r.sathyaraj.octoplus@prowareness.nl)

RUN apt-get clean && apt-get update \
    && apt-get install locales \
    && locale-gen en_US.UTF-8

ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8

ENV TZ=Etc/UTC
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update && apt-get install -y software-properties-common

RUN add-apt-repository ppa:deadsnakes/ppa

RUN apt-get update \
    && apt-get install -y python3.6 python3-pip python3-dev libjpeg8-dev libpng-dev zlib1g-dev

RUN ln -s /usr/lib/x86_64-linux-gnu/libjpeg.so /usr/lib

RUN python3 -m pip install --user numpy==1.13.3 scipy moviepy h5py tensorflow Pillow==3.1.1 lmdb opencv-python cryptography six

ADD . /ai

WORKDIR /ai



