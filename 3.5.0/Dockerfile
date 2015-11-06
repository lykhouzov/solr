FROM centos:7
MAINTAINER Aleksandr Lykhouzov <lykhouzov@gmail.com>

# Install
RUN yum -y update && yum install -y wget java \
&& yum clean all \
&& cd /opt/ \
&& wget https://archive.apache.org/dist/lucene/solr/3.5.0/apache-solr-3.5.0.tgz \
&& tar zxvf apache-solr-3.5.0.tgz \
&& mv apache-solr-3.5.0 solr_01 \
&& rm -f apache-solr-3.5.0.tgz

COPY ./conf/* /opt/solr_01/example/solr/conf/

EXPOSE 8080 8983
WORKDIR /opt/solr_01/example
CMD ["java","-Djetty.home=/opt/solr_01/example","-jar","/opt/solr_01/example/start.jar"]
