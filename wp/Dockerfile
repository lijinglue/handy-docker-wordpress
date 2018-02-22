FROM wordpress:latest
ADD wp-config /var/wp-config
RUN useradd -ms /bin/bash wpuser
RUN usermod -a -G staff wpuser
RUN usermod -a -G www-data wpuser
ADD https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar /usr/local/bin/wp
RUN chgrp staff /usr/local/bin/wp
RUN chmod u+x,g+rx /usr/local/bin/wp
RUN chmod g+rwx -R /var/www 
COPY docker-entrypoint.sh /usr/local/bin/
CMD ["docker-entrypoint.sh", "apache2-foreground"]

