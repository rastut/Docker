FROM hola:6.6
MAINTAINER Carles Lopez (carles.lopez@keradgames.com)

# Disable SELINUX
RUN sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config
#Install Ruby
RUN yum install -y gcc-c++\
 patch\
 readline\
 readline-devel\
 zlib\
 zlib-devel\
 libyaml-devel\
 libffi-devel\
 openssl-devel\
 make\
 bzip2\
 autoconf\
 automake\
 libtool\
 bison\
 iconv-devel
RUN curl -sSL https://rvm.io/mpapis.asc | gpg2 --import -
RUN yum install -y which tar source
RUN curl -L get.rvm.io | bash -s stable
RUN source /etc/profile.d/rvm.sh
RUN /bin/bash -l -c "rvm install 2.1.2"
RUN /bin/bash -l -c "rvm use 2.1.2 --default"
