# Dockerized ssh client

## Running

Autobuilds are available on [Docker hub](https://hub.docker.com/r/ijc25/alpine-ssh). Use:

    docker run -it --rm ijc25/ssh user@hostname

Or e.g.

    docker run -it --rm -v ~/.ssh/id_rsa:/root/.ssh/id_rsa ijc25/alpine-ssh user@hostname
