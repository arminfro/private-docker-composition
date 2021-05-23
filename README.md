# Services

* Cloud
  * with Nextcloud(fpm), Redis caching, Collabora office and Cron tasks
* Git
  * with Gitlab community edition and a Gitlab runner container
* Matrix
  * decentralized communication

Intention is one compose file with many services at once but independent in the scope of groups (so each group can be deactived anytime).

There is also a Webserver group (with nginx-proxy-companion service) which is not optional.

# Requirements

* open firewall-ports (80,443)
* valid A Record pointing to your servers ip address
* a greeting on `STDOUT` when running `docker run hello-world`
* filled .env file

# Install

`git clone https://github.com/armin86er/private-docker-composition.git && cd private-docker-composition`

## Nextcloud

Configure after start at the web frontend your database, user is `nextcloud_db_user`, database name is `nextcloud_db` and db server adress is `nextcloud_db:3306`

## Matrix

`docker run -it --rm -v "./matrix/data:/data" -e SYNAPSE_SERVER_NAME=matrix.example.de -e SYNAPSE_REPORT_STATS=yes matrixdotorg/synapse:latest generate`

edit `homeserver.yml` and start

`docker-compose exec matrix_synapse bash`

`register_new_matrix_user -c /data/homeserver.yaml http://localhost:8008`

## Gitlab

Gitlabs runner needs configuration at the web frontend.

# Docs

[Nextcloud Docker Hub](https://hub.docker.com/_/nextcloud)

[Nextcloud Docker Repo](https://github.com/nextcloud/docker)

[Nextcloud Admin Manual](https://docs.nextcloud.com/server/16/admin_manual/contents.html)

---

[Gitlab Docker Hub](https://hub.docker.com/_/gitlab-community-edition)

[Gitlab Admin Manual](https://docs.gitlab.com/ee/administration)

---

[Matrix](https://matrix.org/docs/develop)

[Synapse](https://github.com/matrix-org/synapse/tree/develop/docs)

---

[Letsencrypt-nginx-proxy-companion](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion/)

[Nginx-proxy](https://github.com/jwilder/nginx-proxy)

## References

[Nextcloud compose file:](https://github.com/nextcloud/docker/blob/master/.examples/docker-compose/with-nginx-proxy/mariadb-cron-redis/fpm/docker-compose.yml)

[Nextcloud app Dockerfile:](https://github.com/nextcloud/docker/blob/master/.examples/dockerfiles/full/fpm/Dockerfile)

[Nextcloud nginx.conf](https://github.com/nextcloud/docker/blob/master/.examples/docker-compose/with-nginx-proxy-self-signed-ssl/mariadb/fpm/web/nginx.conf)

[Collabora in Docker](https://www.collaboraoffice.com/code/docker/)

[Nextcloud Collabora](https://nextcloud.com/collaboraonline/)

### Bookmarks

[Matrix ansible playbook](https://github.com/spantaleev/matrix-docker-ansible-deploy)

[More generic Way for compose organisation](https://github.com/evertramos/docker-compose-letsencrypt-nginx-proxy-companion)

[Awesome list of solf-hosting software](https://github.com/Kickball/awesome-selfhosted)
