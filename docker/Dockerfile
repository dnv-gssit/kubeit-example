FROM nginx

COPY ./nginx.conf /etc/nginx/conf.d/default.conf
COPY ./index.html /usr/share/nginx/html/index.html

RUN cat /usr/share/nginx/html/index.html
