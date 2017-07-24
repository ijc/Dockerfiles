FROM debian:latest
RUN apt-get update && apt-get install --no-install-recommends -y chiark-scripts git openbsd-inetd ca-certificates
RUN useradd --system git-cache && mkdir /var/cache/git-cache-proxy && chown git-cache /var/cache/git-cache-proxy
RUN echo "9419 stream tcp nowait git-cache /usr/bin/git-cache-proxy git-cache-proxy -D" > /etc/inetd.conf
VOLUME /var/cache/git-cache-proxy
EXPOSE 9419
CMD /usr/sbin/inetd -d /etc/inetd.conf
