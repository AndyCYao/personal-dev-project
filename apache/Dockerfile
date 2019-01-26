FROM debian:jessie
# COPY ./public-html/ /usr/local/apache2/htdocs/
# ADD ./public-html /usr/local/public-html/
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "-y", "apache2", "vim"]

ADD website1.ml.conf /etc/apache2/sites-available/
ADD website2.ml.conf /etc/apache2/sites-available/

ADD website1.ml/ /var/www/website1.ml/
ADD website2.ml/ /var/www/website2.ml/
RUN chmod -R 755 /var/www
RUN a2ensite website1.ml.conf
RUN a2ensite website2.ml.conf
# RUN service apache2 restart
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
