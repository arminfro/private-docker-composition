This repo contains a **Nextcloud** (with fpm,redis,cron), a **Gitlab** (with runner) and a **Worpress** instance on **Nginx**.
The webserver works with an `jrcs/letsencrypt-nginx-proxy-companion` container, which brings `SSL` support by setting two variables.

## Intention

One compose file describing and manging all services at once and independently. All services are grouped and groups shall not depend on each other.

## Requirements

* open Firewallports (80,443)
* valid MX Record pointing to your servers ip address
* a greeting on `STDOUT` when running `docker run hello-world`
* filled .env file

## Relevant Documentaion

[Nextcloud Docker Hub](https://hub.docker.com/_/nextcloud)

[Nextcloud Docker Repo](https://github.com/nextcloud/docker)

[Nextcloud Admin Manual](https://docs.nextcloud.com/server/16/admin_manual/contents.html)


[Gitlab Docker Hub](https://hub.docker.com/_/gitlab-community-edition)

[Gitlab Admin Manual](https://docs.gitlab.com/ee/administration)


[Wordpress Docker Hub](https://hub.docker.com/_/wordpress)


[letsencrypt-nginx-proxy-companion](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion/)

[nginx-proxy](https://github.com/jwilder/nginx-proxy)


## References

[Nextcloud compose file:](https://github.com/nextcloud/docker/blob/master/.examples/docker-compose/with-nginx-proxy/mariadb-cron-redis/fpm/docker-compose.yml)

[Nextcloud app Dockerfile:](https://github.com/nextcloud/docker/blob/master/.examples/dockerfiles/full/fpm/Dockerfile)

[Nextcloud nginx.conf](https://github.com/nextcloud/docker/blob/master/.examples/docker-compose/with-nginx-proxy-self-signed-ssl/mariadb/fpm/web/nginx.conf)

## Disclaimer
This repo describes my running instances of services I do like to host myself. I'm a developer and I do some DevOps stuff for my own exclusive and private usage. So this is not a professional setup, but works for me.

### Bookmarks
[matrix](https://hub.docker.com/r/matrixdotorg/synapse)

[Interesting project](https://github.com/evertramos/docker-compose-letsencrypt-nginx-proxy-companion)

[Nextcloud office](https://github.com/smehrbrodt/nextcloud-libreoffice-online)

[Awesome list of solf-hosting software](https://github.com/Kickball/awesome-selfhosted)
