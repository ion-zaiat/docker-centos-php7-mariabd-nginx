FROM centos:7

MAINTAINER Giuseppe Gibilisco <g.gibilisco@sentrybay.com>

RUN yum -y --setopt=tsflags=nodocs update && \
    yum -y --setopt=tsflags=nodocs --nogpgcheck install epel-release && \
    yum -y --setopt=tsflags=nodocs --nogpgcheck install https://centos7.iuscommunity.org/ius-release.rpm && \
    yum -y --setopt=tsflags=nodocs --nogpgcheck install php72u-cli \
        php72u-common \
        php72u-fpm \
        php72u-bcmath \
        php72u-json \
        php72u-mbstring \
        php72u-opcache \
        php72u-pdo \
        php72u-mysqlnd \
        php72u-soap \
        php72u-xml \
        php72u-xdebug && \
        yum -y install gpg && \
        yum install php-pear-crypt-gpg && \
        yum clean all

RUN rm /etc/php-fpm.d/www.conf
ADD ./etc/php-fpm.d/pool.conf /etc/php-fpm.d/
RUN sed -i 's/127.0.0.1:9000/0.0.0.0:9000/g' /etc/php-fpm.d/pool.conf

WORKDIR "/var/www/html"

CMD ["php-fpm", "-F"]

EXPOSE 9000























