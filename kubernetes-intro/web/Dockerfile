FROM nginx:1.17.6-alpine

RUN addgroup -g 1001 docker
RUN adduser -u 1001 -G docker -s /bin/sh -D docker
RUN chown docker /var/cache/nginx
RUN chown docker /var/run

COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

USER docker

WORKDIR /app

EXPOSE 8000

CMD nginx -g 'daemon off;'