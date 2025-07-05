FROM registry.access.redhat.com/ubi8/python-311

USER root
RUN (dnf upgrade --disableplugin=subscription-manager -y || dnf upgrade --disableplugin=subscription-manager -y --nobest) && \
    dnf install -q -y --nodocs \
       wget \
       gcc \
       make \
       openssl-devel \
       cmake \
       clang \
       clang-devel \
       scl-utils \
       ca-certificates && \
    dnf clean all

USER 1001
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
RUN python3.11 -m venv ~/venv
RUN . ~/venv/bin/activate; pip install --upgrade pip
