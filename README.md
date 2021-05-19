This repo describes groups of Docker services. Each group shall be independently of each other.

Current Groups:

* Cloud
  * with Nextcloud(fpm), Redis caching, Collabora office and Cron tasks
* Git
  * with Gitlab community edition and a Gitlab runner container

Intention is one compose file with many services at once but independent in the scope of groups (so each group can be deactived anytime).

There is also a Webserver group (with nginx-proxy-companion service) which is not optional.

## Requirements

* open firewall-ports (80,443)
* valid A Record pointing to your servers ip address
* a greeting on `STDOUT` when running `docker run hello-world`
* filled .env file

## Install

`git clone https://github.com/armin86er/private-docker-composition.git && cd private-docker-composition && git clone https://github.com/vegasbrianc/prometheus.git monitor`

## Relevant Documentaion

[Nextcloud Docker Hub](https://hub.docker.com/_/nextcloud)

[Nextcloud Docker Repo](https://github.com/nextcloud/docker)

[Nextcloud Admin Manual](https://docs.nextcloud.com/server/16/admin_manual/contents.html)

---

[Gitlab Docker Hub](https://hub.docker.com/_/gitlab-community-edition)

[Gitlab Admin Manual](https://docs.gitlab.com/ee/administration)

---

[Letsencrypt-nginx-proxy-companion](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion/)

[Nginx-proxy](https://github.com/jwilder/nginx-proxy)

## References

[Nextcloud compose file:](https://github.com/nextcloud/docker/blob/master/.examples/docker-compose/with-nginx-proxy/mariadb-cron-redis/fpm/docker-compose.yml)

[Nextcloud app Dockerfile:](https://github.com/nextcloud/docker/blob/master/.examples/dockerfiles/full/fpm/Dockerfile)

[Nextcloud nginx.conf](https://github.com/nextcloud/docker/blob/master/.examples/docker-compose/with-nginx-proxy-self-signed-ssl/mariadb/fpm/web/nginx.conf)

[Collabora in Docker](https://www.collaboraoffice.com/code/docker/)

[Nextcloud Collabora](https://nextcloud.com/collaboraonline/)

## Todos

[x] Use networks for groups

[ ] Adding Collabora Templates to Nextcloud

### Bookmarks

[Matrix](https://hub.docker.com/r/matrixdotorg/synapse)

[More generic Way for compose organisation](https://github.com/evertramos/docker-compose-letsencrypt-nginx-proxy-companion)

[Nextcloud office](https://github.com/smehrbrodt/nextcloud-libreoffice-online)

[Awesome list of solf-hosting software](https://github.com/Kickball/awesome-selfhosted)

## Disclaimer

I'm a developer and do some DevOps stuff for my own exclusive and private usage. So this is not a professional setup, but works for me.
