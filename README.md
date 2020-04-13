# DEPRECATED

Please visit https://github.com/tpbtools/gp-haproxy

# Generic Platform - HAProxy Service

## Overview

Docker image and docker-compose sample configuration to bring up a HAProxy Service to the Teecke [Docker Generic Platform (GP)](https://github.com/teecke/docker-generic-platform).

## Configuration

The service is formed by one container:

- **haproxy**: based on [haproxy:2.1.3](https://hub.docker.com/_/haproxy?tab=tags&page=1&name=2.1.3-alpine) alpine docker image.

The image includes de `certbot` utility to manage Let's Encrypt certificates. In the near future it will include a set of scripts to get and renew the certificates.

## Operation

1. Use the `docker-compose.yml.sample` file as your docker-compose configuration file.

2. Install assets with `devcontrol assets-install`.

3. Start the service with `docker-compose up -d`.

4. Open the url <http://localhost> or <https://localhost> in a browser to access to the HAProxy service.

5. Manage backups of your files:

   1. Make a backup executing `docker-compose exec haproxy backup`.
   2. Find the current backup within the `/var/backups/gp/haproxy/` of the container.
   3. Extract the current backup executing `docker cp $(docker-compose ps -q haproxy):/var/backups/gp gp`.

6. Stop the service with `docker-compose stop`.

You can use this docker piece with the [Docker Generic Platform](https://github.com/teecke/docker-generic-platform) project.

## Known issues

None known
