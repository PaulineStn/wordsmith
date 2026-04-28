FROM postgres:18.3-alpine3.23
ENV POSTGRES_HOST_AUTH_METHOD=trust

COPY words.sql /docker-entrypoint-initdb.d/