FROM nginx
LABEL "Project"="GTIProject"
LABEL "Author"="GTI"

RUN rm -rf /etc/nginx/conf.d/default.conf
COPY gtinginxapp.conf /etc/nginx/conf.d/gtiapp.conf
