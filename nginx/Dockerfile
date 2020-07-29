FROM debian:jessie

RUN apt-get update && apt-get install -y \
    nginx

# Add config files
ADD nginx.conf /etc/nginx/
ADD laravel.conf /etc/nginx/sites-available/
ADD upstream.conf /etc/nginx/conf.d/

RUN ln -s /etc/nginx/sites-available/laravel.conf /etc/nginx/sites-enabled/laravel
RUN rm /etc/nginx/sites-enabled/default
RUN rm /etc/nginx/sites-available/default
RUN usermod -u 1000 www-data

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
