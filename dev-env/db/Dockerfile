FROM postgres:16

# Time Zone & Language
RUN apt-get update && \
    apt-get install -y --no-install-recommends tzdata locales && \
    echo "Asia/Tokyo" > /etc/timezone && \
    ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    echo "ja_JP.UTF-8 UTF-8" >> /etc/locale.gen && \
    locale-gen ja_JP.UTF-8 && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Workdir
WORKDIR /usr/src/postgres-db/
RUN mkdir -p tmp/
COPY ./db/conn_db.sh ./conn-db.sh
RUN chmod 700 ./conn-db.sh
