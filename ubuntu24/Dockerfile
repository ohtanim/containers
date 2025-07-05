FROM ubuntu:24.04

USER root
RUN ln -snf /usr/share/zoneinfo/$CONTAINER_TIMEZONE /etc/localtime && echo $CONTAINER_TIMEZONE > /etc/timezone
RUN apt update -y && \
    apt install -y \
       wget \
       gcc \
       gfortran \
       make \
       pkg-config \
       python3.12 \
       python3-venv \
       python3-pip \
       pip \
       libssl-dev \
       cmake \
       vim \
       less \
       doxygen \
       curl

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
RUN python3.12 -m venv ~/venv
RUN . ~/venv/bin/activate; pip install --upgrade pip
