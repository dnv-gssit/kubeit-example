FROM nginx:stable-alpine

COPY ./index.html /usr/share/nginx/html/index.html
COPY ./nginx.conf /etc/nginx/conf.d/default.conf

RUN cat /usr/share/nginx/html/index.html
