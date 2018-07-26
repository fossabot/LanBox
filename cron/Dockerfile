FROM mchus/lanbox-app

RUN set -ex; \
    mkdir -p /var/spool/cron/crontabs; \
    echo '*/15 * * * * php -f /var/www/html/cron.php' > /var/spool/cron/crontabs/www-data;
COPY        cron.sh /
RUN         chmod +x /cron.sh
ENTRYPOINT  ["/cron.sh"]
