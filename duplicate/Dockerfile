FROM wordpress:6.6 as start_wp_build

EXPOSE 80

VOLUME /var/html/www

RUN apt-get update -y && apt-get install -y \
    mariadb-client unzip

RUN mkdir /backup    
COPY ./duplicate-entrypoint.sh /usr/local/bin/duplicate-entrypoint.sh
COPY ./restore-duplicate.sh /usr/local/bin/restore-duplicate.sh
COPY ./wait-for-it.sh /usr/local/bin/wait-for-it.sh

#ENTRYPOINT ["duplicate-entrypoint.sh", "--overwrite"]
CMD ["apache2-foreground"]
