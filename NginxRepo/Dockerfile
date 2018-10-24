FROM nginx:1.15.5

COPY nginx.conf /etc/nginx/nginx.conf
RUN chown -R nginx:nginx /var/log/nginx

RUN mkdir -p /repoman
RUN rm -f /var/www
RUN ln -s /repoman/www /var/www

EXPOSE 8080

VOLUME ["/var/log/nginx", "/repoman"]
