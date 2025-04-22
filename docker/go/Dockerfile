ARG GO_VERSION=latest

FROM golang:${GO_VERSION}

ARG USER_ID
ARG GROUP_ID

RUN apt-get update && apt-get install --no-install-recommends --no-install-suggests -y \
    zsh

RUN useradd -s /bin/bash -d /home/gosearch -m gosearch
RUN groupmod -o -g ${GROUP_ID} gosearch && \
    usermod -o -u ${USER_ID} -g gosearch gosearch

USER gosearch

WORKDIR /home/gosearch/app

ENTRYPOINT ["tail", "-f", "/dev/null"]
