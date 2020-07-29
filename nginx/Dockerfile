FROM nginx:1.19.1-alpine

# Add config files
ADD nginx.conf    /etc/nginx/
ADD laravel.conf  /etc/nginx/conf.d/
ADD upstream.conf /etc/nginx/conf.d/

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
