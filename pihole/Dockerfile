# https://hub.docker.com/r/pihole/pihole/tags
FROM pihole/pihole:2022.08.2

WORKDIR /usr/src/app

COPY cont-init.d/ /etc/cont-init.d/

COPY services/ /etc/services.d/

RUN chmod +x /etc/cont-init.d/10-custom.sh && \
	chmod +x /etc/services.d/padd/*

ENV DEBIAN_FRONTEND noninteractive

# hadolint ignore=DL3008
RUN apt-get update && \
	apt-get install --no-install-recommends -y console-setup dbus netcat && \
	apt-get clean && rm -rf /var/lib/apt/lists/*

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV INTERFACE eth0
ENV DNSMASQ_LISTENING single
ENV PIHOLE_DNS_ 1.1.1.1;1.0.0.1
ENV WEBPASSWORD balena
ENV VIRTUAL_HOST balena-devices.com