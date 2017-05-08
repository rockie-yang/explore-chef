FROM debian:jessie

RUN apt-get update \
  && apt-get install -y git curl sed vim wget
  
ARG CHANNEL=stable
ARG VERSION=1.3.43
# https://packages.chef.io/files/stable/chefdk/1.3.43/debian/8/chefdk_1.3.43-1_amd64.deb
RUN wget https://packages.chef.io/files/stable/chefdk/1.3.43/debian/8/chefdk_1.3.43-1_amd64.deb -O /tmp/chefdk.deb \
    && dpkg -i /tmp/chefdk.deb \
    && rm /tmp/chefdk.deb

RUN apt-get clean autoclean \
  && apt-get autoremove -y --force-yes \
  && rm -rf /tmp/* \
  && rm -rf ~/.m2 ~/.npm ~/.cache \
  && rm -rf /var/lib/{apt,dpkg,cache,log}/


VOLUME [ "/opt/chef" ]
