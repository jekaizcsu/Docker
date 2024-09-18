FROM ubuntu:latest
RUN mkdir -p /var/lib/nginx/body && usermod -aG www-data www-data && apt-get update -y && apt-get install -y nginx && chown -R www-data:www-data /var/lib/nginx && touch /var/log/nginx/error.log
RUN chown -R www-data:www-data /var/log/nginx && chmod -R g+rwx /var/log/nginx
RUN chown -R www-data:www-data /run && chmod -R g+w /run
COPY nginx.conf /etc/nginx/nginx.conf
RUN chown -R www-data:www-data /etc/nginx && chmod -R g+rwx /etc/nginx
COPY index.html /var/www/html/index.html
RUN chown www-data:www-data /var/www/html/index.html && chmod g+rwx /var/www/html/index.html
###EXPOSE 80
USER www-data
CMD ["nginx", "-g", "daemon off;"]
