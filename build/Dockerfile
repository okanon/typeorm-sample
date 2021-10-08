FROM postgres:14.0

RUN localedef -i ja_JP -c -f UTF-8 -A /usr/share/locale/locale.alias ja_JP.UTF-8

ENV LANG en_US.UTF-8
ENV TZ=UTC
ENV POSTGRES_HOST_AUTH_METHOD trust

COPY 000001_create_typeorm_sample_db.sql /docker-entrypoint-initdb.d/