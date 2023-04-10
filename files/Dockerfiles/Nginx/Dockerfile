FROM nginx:1.23.1-alpine

COPY ./data/nginx/app.conf /etc/nginx/conf.d/default.conf
COPY ./data/nginx/nginx.conf /etc/nginx/nginx.conf

RUN chown -R nginx:nginx /var/cache/nginx && \
    chown -R nginx:nginx /var/log/nginx && \
    chown -R nginx:nginx /etc/nginx/

USER nginx

EXPOSE 80/tcp

CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
