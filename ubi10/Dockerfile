FROM registry.access.redhat.com/ubi10/ubi

USER root
RUN (dnf upgrade --disableplugin=subscription-manager -y || dnf upgrade --disableplugin=subscription-manager -y --nobest) && \
    dnf install -q -y --nodocs \
       wget \
       gcc \
       make \
       openssl-devel \
       g++ \
       cmake \
       clang \
       clang-devel \ 
       git \
       scl-utils \
       python3-devel \
       ca-certificates && \
    dnf clean all

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
RUN python3 -m venv ~/venv
RUN . ~/venv/bin/activate; pip install --upgrade pip
