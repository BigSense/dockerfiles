FROM ubuntu

RUN apt-get update && \
    apt-get install -y gnupg1 && \
    echo "deb http://repo.aptly.info/ squeeze main" >> /etc/apt/sources.list && \
    apt-key adv --keyserver pool.sks-keyservers.net --recv-keys ED75B5A4483DA07C && \
    apt-get update && \
    DEBIAN_FRONTEND='noninteractive' \
    apt-get install -y expect aptly createrepo python3  gpgv1 && \
    rm -rf /var/lib/apt/lists/*

ENV BIN_DIR /repoman-bin
ENV REPO_DIR /repoman

RUN mkdir -p $BIN_DIR
COPY rpmsign $BIN_DIR
COPY publish $BIN_DIR
COPY aptly.conf $BIN_DIR

VOLUME ["/repoman"]

CMD "$BIN_DIR/publish"
