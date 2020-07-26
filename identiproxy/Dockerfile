FROM nginx:1.7

COPY default.conf /etc/nginx/conf.d/default.conf
COPY entrypoint.sh /
CMD ["nginx", "-g", "daemon off;"]
ENTRYPOINT ["/entrypoint.sh"]

