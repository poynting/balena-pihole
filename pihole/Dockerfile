# https://hub.docker.com/r/pihole/pihole/tags
FROM pihole/pihole:2022.05

WORKDIR /usr/src/app

COPY cont-init.d/ /etc/cont-init.d/

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV INTERFACE eth0
ENV DNSMASQ_LISTENING single
ENV PIHOLE_DNS_ 1.1.1.1;1.0.0.1
ENV WEBPASSWORD balena
ENV VIRTUAL_HOST balena-devices.com