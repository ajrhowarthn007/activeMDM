FROM nginx:1.25.3-alpine3.18

RUN apk add inotify-tools
RUN mkdir -p /var/local/step
COPY site.conf /etc/nginx/conf.d/
COPY certwatch.sh /
COPY entrypoint.sh /

# Certificate watcher and nginx
ENTRYPOINT ["/entrypoint.sh"]
CMD ["nginx", "-g", "daemon off;"]
