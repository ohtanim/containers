FROM almalinux:latest

USER root
RUN dnf install -q -y --nodocs \
       wget \
       gcc \
       gfortran \
       make \
       python3.12 \
       python3.12-devel \
       pip \
       openssl-devel \
       g++ \
       cmake \
       ca-certificates && \
    dnf clean all

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
RUN python3.12 -m venv ~/venv
RUN . ~/venv/bin/activate; pip install --upgrade pip
