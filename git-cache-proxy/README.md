# Dockerized git-cache-proxy

Run [git-cache-proxy](https://www.chiark.greenend.org.uk/ucgi/~ian/git?p=chiark-utils.git;a=blob;f=scripts/git-cache-proxy)
as a [Docker](https://www.docker.com) container.

## Running

Autobuilds are available on [Docker
hub](https://hub.docker.com/r/ijc25/git-cache-proxy) and listen on
port 9419, which you should map to your host e.g:

    docker run -p 9419:9419 ijc25/git-cache-proxy:latest

## Using

From the [top of the script](https://www.chiark.greenend.org.uk/ucgi/~ian/git?p=chiark-utils.git;a=blob;f=scripts/git-cache-proxy#l11)
```
# usage: run it on some port, and then clone or fetch
#  "git://<realhost>:<realport>/<real-git-url>[ <options>]"
# where <real-git-url> is http://<host>/... or git://<host>/...
# and <options> is zero or more (whitespace-separated) of
#    [<some-option>]      will be ignored if not recognised
#    {<some-option>}      error if not recognised
# options currently known:
#    fetch=must           fail if the fetch/clone from upstream fails
#    fetch=no             just use what is in the cache
#    fetch=try            use what is in the cache if the fetch/clone fails
#    timeout=<seconds>    length of time to allow for fetch/clone
```

Where `<realhost>` will be your Docker host (perhaps `localhost`) and
if you used `-p 9419:9419` as above then `<realport>` will be `9419`. e.g.
```
git clone git://localhost:9419/https://github.com/ijc/Dockerfiles
```
