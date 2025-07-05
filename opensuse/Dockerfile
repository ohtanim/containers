FROM opensuse/leap:latest

USER root
RUN zypper install -y \
       wget \
       gcc \
       gcc-c++ \
       gcc-fortran \
       make \
       cmake \
       python312 \
       python312-devel \
       python312-pip \
       openssl-devel \
       gdb \
       vim \
       less \
       ca-certificates

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
RUN python3.12 -m venv ~/venv
RUN . ~/venv/bin/activate; pip install --upgrade pip
