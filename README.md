This repo contains a **Nextcloud** (with fpm,redis,cron), a **Gitlab** (with runner), a **Prometheus** (with grafana) and a **Worpress** instance on **Nginx**.
The webserver works with an `jrcs/letsencrypt-nginx-proxy-companion` container, which brings `SSL` support by setting two variables.

## Intention

One compose file describing and manging all services at once and kinda independently.
All services are grouped and groups shall not depend on each other, so each group can be commented out anytime.

## Disclaimer

This repo describes my running instances of services I do like to host myself. I'm a developer and do some DevOps stuff for my own exclusive and private usage. So this is not a professional setup, but works for me.
Any kind of contribution is welcome, add more service groups to your liking and bring it up :)

## Requirements

* open Firewallports (80,443)
* valid MX Record pointing to your servers ip address
* a greeting on `STDOUT` when running `docker run hello-world`
* filled .env file

## Install

`git clone *url* && cd *repo_name* && git clone https://github.com/vegasbrianc/prometheus.git monitor`

## Relevant Documentaion

[Nextcloud Docker Hub](https://hub.docker.com/_/nextcloud)

[Nextcloud Docker Repo](https://github.com/nextcloud/docker)

[Nextcloud Admin Manual](https://docs.nextcloud.com/server/16/admin_manual/contents.html)

---

[Gitlab Docker Hub](https://hub.docker.com/_/gitlab-community-edition)

[Gitlab Admin Manual](https://docs.gitlab.com/ee/administration)

---

[Wordpress Docker Hub](https://hub.docker.com/_/wordpress)

---

[Letsencrypt-nginx-proxy-companion](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion/)

[Nginx-proxy](https://github.com/jwilder/nginx-proxy)

---

[Prometheus](https://github.com/vegasbrianc/prometheus)

[Grafana](https://grafana.com/docs/)


## References

[Nextcloud compose file:](https://github.com/nextcloud/docker/blob/master/.examples/docker-compose/with-nginx-proxy/mariadb-cron-redis/fpm/docker-compose.yml)

[Nextcloud app Dockerfile:](https://github.com/nextcloud/docker/blob/master/.examples/dockerfiles/full/fpm/Dockerfile)

[Nextcloud nginx.conf](https://github.com/nextcloud/docker/blob/master/.examples/docker-compose/with-nginx-proxy-self-signed-ssl/mariadb/fpm/web/nginx.conf)

## Todos

* Use networks for groups
* Nextcloud office

### Bookmarks
[Matrix](https://hub.docker.com/r/matrixdotorg/synapse)

[More generic Way for compose organisation](https://github.com/evertramos/docker-compose-letsencrypt-nginx-proxy-companion)

[Nextcloud office](https://github.com/smehrbrodt/nextcloud-libreoffice-online)

[Awesome list of solf-hosting software](https://github.com/Kickball/awesome-selfhosted)
