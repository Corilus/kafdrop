FROM openjdk:12.0.1-jdk-oraclelinux7

RUN groupadd -g 1000 tomcat && \
  useradd -r -u 1000 -g tomcat tomcat

ADD kafdrop.sh /
ADD kafdrop*tar.gz /

RUN chmod +x /kafdrop.sh

RUN chown -R tomcat:tomcat /kafdrop*

USER tomcat:tomcat

ENTRYPOINT ["/kafdrop.sh"]
