FROM racket/racket:8.8
WORKDIR /app
RUN apt update -y && apt upgrade -y \
    && apt install -y --no-install-recommends git curl \
    && apt autoclean -y \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && curl https://docs.breezewiki.com/files/breezewiki-dist.tar.gz | tar xvz
    && ./breezewiki-dist/bin/dist
EXPOSE 10416
CMD ["racket", "dist.rkt"]
