FROM httpd
COPY httpd.conf /usr/local/apache2/conf/
COPY homework.html /app/homework.html
WORKDIR /app
RUN groupadd --gid 1001 web && useradd --uid 1001 --gid web --shell /bin/bash --create-home web
RUN chmod -R 777 /usr/local/apache2/logs/
USER 1001
