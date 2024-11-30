FROM httpd:2.4

COPY ./containers/httpd/httpd.vhost.conf /usr/local/apache2/conf/extra/httpd.vhost.conf

RUN sed -i \
    -e '/#LoadModule deflate_module/s/^#//g' \
    -e '/#LoadModule proxy_module/s/^#//g' \
    -e '/#LoadModule proxy_fcgi_module/s/^#//g' \
    -e '/#LoadModule rewrite_module/s/^#//g' \
    -e '/#Include conf/extra/httpd-autoindex.conf/s/^#//g' \
    /usr/local/apache2/conf/httpd.conf

RUN echo "Include /usr/local/apache2/conf/extra/httpd.vhost.conf" >> /usr/local/apache2/conf/httpd.conf
