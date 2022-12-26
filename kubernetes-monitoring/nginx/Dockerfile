FROM nginx:1.23.2
COPY index.html /usr/share/nginx/html
COPY nginx.conf /etc/nginx/
COPY conf.d /etc/nginx/conf.d
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]