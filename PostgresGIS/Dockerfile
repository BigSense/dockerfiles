FROM postgres:11.1

RUN apt-get update && \
    DEBIAN_FRONTEND='noninteractive' apt-get install -y postgresql-11-postgis-2.5 && \
    rm -rf /var/lib/apt/lists/*
