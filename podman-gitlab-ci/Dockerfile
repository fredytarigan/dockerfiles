FROM quay.io/podman/stable:v5.6.2@sha256:f34622fd2dd9428eee170a2b9d507b48ed43ae845eb669987584e2ac3799255d

ENV VAULT_VERSION="1.20.4"
ENV ENVSUBST_VERSION="1.4.3"

## Update packages
RUN dnf -y update \
    && dnf -y upgrade \
    && dnf install -y jq curl unzip \
    && dnf clean all

## Install vault binary
RUN curl -fsSL https://releases.hashicorp.com/vault/${VAULT_VERSION}/vault_${VAULT_VERSION}_linux_amd64.zip -o vault.zip \
    && unzip vault.zip -d /usr/local/bin/ \
    && chmod +x /usr/local/bin/vault \
    && rm vault.zip

## Install envsubst binary
RUN curl -L https://github.com/a8m/envsubst/releases/download/v${ENVSUBST_VERSION}/envsubst-Linux-x86_64 -o /usr/local/bin/envsubst \
    && chmod +x /usr/local/bin/envsubst