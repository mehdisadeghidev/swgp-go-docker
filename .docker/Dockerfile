FROM alpine:3.20

WORKDIR /app

RUN apk update && apk add wget zstd

RUN wget https://github.com/database64128/swgp-go/releases/download/v1.5.0/swgp-go-v1.5.0-linux-x86-64-v2.tar.zst

RUN zstd -dc swgp-go-v1.5.0-linux-x86-64-v2.tar.zst	 | tar -xf -

RUN mv swgp-go /app/

RUN chmod +x /app/swgp-go

CMD ["/app/swgp-go", "-confPath", "/app/config.json", "-logLevel", "error"]
