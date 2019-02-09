FROM ubuntu:14.04

#### Java8
RUN apt-get update -y \
&&  apt-get install software-properties-common -y \
&&  apt-add-repository ppa:webupd8team/java -y \
&&  apt-get update -y \

####automatically agreeing on oracle license agreement [for installing java]
&&  echo debconf shared/accepted-oracle-license-v1-1 select true | sudo debconf-set-selections \
&&  echo debconf shared/accepted-oracle-license-v1-1 seen true | sudo debconf-set-selections \

#### java et supervisor
&&  apt-get install -y oracle-java8-installer \
    supervisor


#### Spark 2.2.3 
RUN wget http://apache.mirror.triple-it.nl/spark/spark-2.2.3/spark-2.2.3-bin-hadoop2.7.tgz \
&&  tar -xzf spark-2.2.3-bin-hadoop2.7.tgz \
&&  mv spark-2.2.3-bin-hadoop2.7 /opt/spark

##### conf files
COPY master.conf /opt/conf/master.conf
COPY slave.conf /opt/conf/slave.conf


#######exposing port 8080 for spark master UI
EXPOSE 8080
EXPOSE 8020
EXPOSE 9000
