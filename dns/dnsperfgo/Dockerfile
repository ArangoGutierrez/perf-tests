# runtime image
FROM alpine:3.10
# install bind-tools to prevent nslookup from sending PTR queries for each response IP
RUN apk add --no-cache ca-certificates bash tcpdump git bind-tools
# This is to make sure dnstest compiled on debian can run in alpine/musl
RUN mkdir /lib64 && ln -s /lib/libc.musl-x86_64.so.1 /lib64/ld-linux-x86-64.so.2
COPY dnsperfgo /dnsperfgo
COPY dnsperfcgo /dnsperfcgo
ENTRYPOINT ["/dnsperfcgo"]
