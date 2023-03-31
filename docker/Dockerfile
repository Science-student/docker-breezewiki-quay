FROM racket/racket:8.8
WORKDIR /app
RUN apt update -y && apt upgrade -y \
    && apt install -y --no-install-recommends git wget \
    && apt autoclean -y \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && wget https://docs.breezewiki.com/files/breezewiki-dist.tar.gz
    && ./breezewiki-dist/bin/dist
EXPOSE 10416
CMD ["racket", "dist.rkt"]
