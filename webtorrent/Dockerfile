FROM alpine:latest
LABEL maintainer="Ricardo Rebello Sierra <contato@ricardosierra.com.br>"


## https://github.com/feross/webtorrent
# webtorrent(){
#   docker run -it --rm \
#     --net host \
#     -u $(id -u):$(id -g) \
#     -v "$PWD":/downloads \
#     -w /downloads \
#     ondrejmo/webtorrent "$@"
# }

RUN apk update && apk add nodejs \
  && rm -rf /var/cache/apk/*
RUN npm install -g webtorrent-cli \
  && rm -r /root/.npm

WORKDIR /downloads
VOLUME /downloads

ENTRYPOINT [ "webtorrent" ]
