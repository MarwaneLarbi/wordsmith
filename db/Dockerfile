FROM postgres:13

COPY . /docker-entrypoint-initdb.d
ENV POSTGRES_HOST_AUTH_METHOD=trust