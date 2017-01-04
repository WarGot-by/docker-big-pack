FROM debian:jessie

MAINTAINER Heorhi Paulenka <wargot@gmail.com>

RUN apt-get update && apt-get install -y \
    nginx

#ADD nginx.conf /etc/nginx/
#ADD symfony.conf /etc/nginx/sites-available/
#ADD ${SITES_AVAILABLE_PATH}/* /etc/nginx/sites-available1/
#ADD ${SITES_AVAILABLE_PATH} /etc/nginx/sites-available2/
#ADD ${SITES_AVAILABLE_PATH}* /etc/nginx/sites-available3/

RUN cp /home/docker/sites-available/* /etc/nginx/sites-available4/
RUN ln -s /etc/nginx/sites-available/ /etc/nginx/sites-enabled/
RUN rm /etc/nginx/sites-enabled/default

RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

RUN usermod -u 1000 www-data

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
