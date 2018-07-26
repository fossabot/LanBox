FROM mchus/lanbox-app


RUN set -ex; \
    mkdir -p /var/spool/cron/crontabs; \
    echo '*/15 * * * * php -f /var/www/html/cron.php' > /var/spool/cron/crontabs/www-data;

CMD ["busybox crond -f -l 0 -L /dev/stdout"]
