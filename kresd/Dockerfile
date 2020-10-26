FROM alpine:3.12

RUN apk add --no-cache ca-certificates dns-root-hints dnssec-root knot-resolver lua-http tini

RUN cp /usr/share/dnssec-root/trusted-key.key /etc/knot-resolver/trusted-key.key

ENTRYPOINT ["/sbin/tini", "--", "/usr/sbin/kresd"]

CMD ["-n", "-c", "/etc/knot-resolver/kresd.conf"]

