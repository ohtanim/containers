FROM rockylinux:9

USER root
RUN dnf install -q -y --nodocs \
       wget \
       gcc \
       gfortran \
       make \
       python3.11 \
       python3.11-devel \
       pip \
       openssl-devel \
       g++ \
       cmake \
       ca-certificates && \
    dnf clean all

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
RUN python3.11 -m venv ~/venv
RUN . ~/venv/bin/activate; pip install --upgrade pip
