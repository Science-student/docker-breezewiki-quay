FROM debian:latest

WORKDIR /app

# Install dependencies and clean up package manager cache
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y git wget && \
    apt-get autoclean && \
    apt-get autoremove && \
    rm -rf /var/lib/apt/lists/*

# Download and extract the Breezewiki distribution
RUN wget -qO- https://docs.breezewiki.com/files/breezewiki-dist.tar.gz | tar xz -C /app

# Expose the Breezewiki server port
EXPOSE 10416

# Start the Breezewiki server
CMD ["/app/breezewiki-dist/bin/dist"]
