FROM nginx:1.19.1-alpine

# Add config files
ADD nginx.conf    /etc/nginx/
ADD laravel.conf  /etc/nginx/conf.d/
ADD upstream.conf /etc/nginx/conf.d/

RUN usermod -u 1000 www-data

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
