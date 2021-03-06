# See here for image contents: https://github.com/microsoft/vscode-dev-containers/blob/master/containers/cpp/.devcontainer/base.Dockerfile
ARG VARIANT="focal"
FROM mcr.microsoft.com/vscode/devcontainers/cpp

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends xz-utils

ARG ZIG_VERSION="0.7.1"
ARG ZIG_ARCH="linux-x86_64"
RUN curl -L https://ziglang.org/download/${ZIG_VERSION}/zig-${ZIG_ARCH}-${ZIG_VERSION}.tar.xz | tar -xJ -C /opt
ENV PATH="/opt/zig-${ZIG_ARCH}-${ZIG_VERSION}:${PATH}"

RUN mkdir /opt/zls && curl -L https://github.com/zigtools/zls/releases/download/0.1.0/x86_64-linux.tar.xz | tar -xJ --strip-components=1 -C /opt/zls
ENV PATH="/opt/zls/zls:${PATH}"
