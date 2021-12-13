FROM centos:latest
RUN yum update -y
RUN yum install epel-release -y
RUN yum install java-11-openjdk-devel -y
RUN yum install wget -y
RUN cd /usr/local/ && wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.56/bin/apache-tomcat-9.0.56.tar.gz
RUN cd /usr/local/ && tar -xvf  apache-tomcat-9.0.56.tar.gz
RUN cd /usr/local/ && mv apache-tomcat-9.0.56 tomcat9
RUN cd /usr/local/ && rm -rf apache-tomcat-9.0.56.tar.gz
RUN echo "export CATALINA_HOME="/usr/local/tomcat9"" >> ~/.bashrc && source ~/.bashrc
RUN cd /usr/local/tomcat9/webapps && wget  https://get.jenkins.io/war-stable/2.235.5/jenkins.war 

CMD ["run"]
ENTRYPOINT ["/usr/local/tomcat9/bin/catalina.sh"]
