# see, https://github.com/eXtalionLab/nextcloud_docker/blob/master/docker/coturn/Dockerfile
# the different stages of this Dockerfile are meant to be built into separate images
# https://docs.docker.com/develop/develop-images/multistage-build/#stop-at-a-specific-build-stage
# https://docs.docker.com/compose/compose-file/#target


# https://docs.docker.com/engine/reference/builder/#understand-how-arg-and-from-interact
ARG COTURN_VERSION=latest


# "coturn" stage
FROM coturn/coturn:${COTURN_VERSION}

COPY turnserver.conf /etc/turnserver.conf

COPY docker-entrypoint.sh /docker-entrypoint.sh

ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["turnserver"]
