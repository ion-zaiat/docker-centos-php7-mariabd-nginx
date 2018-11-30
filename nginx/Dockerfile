FROM centos:7
  
MAINTAINER Giuseppe Gibilisco <g.gibilisco@sentrybay.com>

RUN yum -y --setopt=tsflags=nodocs update && \
    yum -y --setopt=tsflags=nodocs --nogpgcheck install epel-release && \
    yum -y --setopt=tsflags=nodocs --nogpgcheck install nginx

ADD ./etc/nginx/nginx.conf /etc/nginx/nginx.conf
ADD ./etc/nginx/conf.d/default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80 443

CMD ["nginx", "-g daemon off;"]




