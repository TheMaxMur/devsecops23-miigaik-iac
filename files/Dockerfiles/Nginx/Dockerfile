FROM registry.gitlab.devsecops.maxmur.info/devsecops/iac/nginx_modsecurity:dora

RUN rm -rf /usr/local/openresty/nginx/conf/conf.d/*

COPY ./data/nginx/app.conf /usr/local/openresty/nginx/conf/conf.d/default.conf
COPY ./data/nginx/options-ssl-nginx.conf /options-ssl-nginx.conf
COPY ./data/nginx/ssl-dhparams.pem /ssl-dhparams.pem

USER 0

RUN chown -R 1001:1001 /usr/local/openresty/ && \
    chown 1001:1001 /options-ssl-nginx.conf && \
    chown 1001:1001 /ssl-dhparams.pem

USER 1001

EXPOSE 80/tcp

CMD ["/usr/local/openresty/bin/openresty", "-g", "daemon off;"]
