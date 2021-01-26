FROM curlimages/curl as getfly
USER root
RUN curl -o fly.tgz -L "https://github.com/concourse/concourse/releases/download/v6.7.3/fly-6.7.3-linux-amd64.tgz"
RUN tar -xvf fly.tgz
RUN chmod +x fly

FROM ubuntu:bionic
COPY --from=getfly fly /usr/local/bin/fly

RUN apt-get update \
 && apt install -y --no-install-recommends \
      git-core ca-certificates vim \
 && rm -rf /var/lib/apt/lists/*
