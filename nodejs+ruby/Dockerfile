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
#RUN rvm install 2.1.2 && rvm use 2.1.2 --default
RUN /bin/bash -l -c "rvm install 2.1.2"
RUN /bin/bash -l -c "rvm use 2.1.2 --default"
#Install Node.js
#RUN yum -y groupinstall "Development Tools"
RUN yum install -y screen wget
WORKDIR /usr/local/ 
RUN wget http://nodejs.org/dist/v0.12.2/node-v0.12.2.tar.gz && tar -zxvf node-v0.12.2.tar.gz
WORKDIR /usr/local/node-v0.12.2
RUN ./configure && make && make install
#RUN yum -y groupremove 'Development Tools'
#RUN yum -y remove make automake gcc-c++
RUN rm -rfv /usr/local/node-v0.12.2 /usr/local/node-v0.12.2.tar.gz
