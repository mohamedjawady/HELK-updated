# HELK script: HELK Base Image Dockerfile
# HELK build version: 0.9 (Alpha)
# Author: Roberto Rodriguez (@Cyb3rWard0g)
# License: GPL-3.0

FROM phusion/baseimage:noble-1.0.0
LABEL maintainer="Ignace De Cock @Krapgras"
LABEL description="Dockerfile HELK Base Image.."

ENV DEBIAN_FRONTEND noninteractive

# *********** Installing Prerequisites ***************
# -qq : No output except for errors
RUN apt-get update && apt-get install -qqy --no-install-recommends \
  wget \
  sudo \
  nano \
  && apt-get -qy clean \
  autoremove \
  && rm -rf /var/lib/apt/lists/*

CMD ["/sbin/my_init"]