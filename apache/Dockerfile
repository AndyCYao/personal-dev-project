FROM debian:jessie
# COPY ./public-html/ /usr/local/apache2/htdocs/
# ADD ./public-html /usr/local/public-html/
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "-y", "apache2", "vim"]

ADD website1.conf /etc/apache2/sites-available/
ADD website2.conf /etc/apache2/sites-available/

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]