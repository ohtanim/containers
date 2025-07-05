FROM --platform=linux/amd64 registry.access.redhat.com/ubi9/python-311

USER root
RUN (dnf upgrade --disableplugin=subscription-manager -y || dnf upgrade --disableplugin=subscription-manager -y --nobest) && \
    dnf install -q -y --nodocs \
       wget \
       gcc \
       gcc-toolset-13 \
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

USER 1001
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
RUN python3.11 -m venv ~/venv
RUN . ~/venv/bin/activate; pip install --upgrade pip
