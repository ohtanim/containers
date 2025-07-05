FROM amazonlinux:latest

USER root
RUN dnf install -q -y --nodocs \
       wget \
       gcc \
       gfortran \
       make \
       python3.12 \
       pip \
       openssl-devel \
       g++ \
       cmake \
       doxygen \
       vim-minimal \
       less \
       which \
       tar \
       git \
       openmpi-devel \
       hostname \
       ca-certificates && \
    dnf clean all

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
RUN python3.12 -m venv ~/venv
RUN . ~/venv/bin/activate; pip install --upgrade pip; pip install conan; conan profile detect
