FROM mysql:9.7
ENV MYSQL_ROOT_PASSWORD=root \
    MYSQL_DATABASE=appdb
VOLUME ["/var/lib/mysql"]
COPY init.sql /docker-entrypoint-initdb.d

HEALTHCHECK --interval=5s --timeout=3s --start-period=8s  --retries=2 \
            CMD mysqladmin ping -h localhost -u root -p${MYSQL_ROOT_PASSWORD} || exit 1
