FROM alpine:edge

ENV LOCAL_IP       0.0.0.0
ENV LOCAL_PORT     5353
ENV RESOLVER_IP    208.67.220.220
ENV RESOLVER_PORT  53
ENV PROVIDER_NAME  2.dnscrypt-cert.opendns.com
ENV PROVIDER_KEY   B735:1140:206F:225D:3E2B:D822:D7FD:691E:A1C3:3CC8:D666:8D0C:BE04:BFAB:CA43:FB79 
ENV LOG_LEVEL      6

RUN set -xe \
    && apk add --no-cache dnscrypt-proxy

EXPOSE $LOCAL_PORT/tcp $LOCAL_PORT/udp

CMD dnscrypt-proxy --local-address=$LOCAL_IP:$LOCAL_PORT \
                   --provider-name=$PROVIDER_NAME \
                   --provider-key=$PROVIDER_KEY \
                   --resolver-address=$RESOLVER_IP:$RESOLVER_PORT \
                   --loglevel=$LOG_LEVEL
