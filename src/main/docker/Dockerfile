FROM openjdk:12.0.1-jdk-oraclelinux7

RUN groupadd -g 1000 tomcat && \
  useradd -r -u 1000 -g tomcat tomcat

HEALTHCHECK --start-period=15s --interval=15s --timeout=10s --retries=20 CMD curl -A "Docker-HealthCheck/1.0" -f http://127.0.0.1:9000/actuator/health || exit 1

ADD kafdrop.sh /
ADD kafdrop*tar.gz /

RUN chmod +x /kafdrop.sh

RUN chown -R tomcat:tomcat /kafdrop*

USER tomcat:tomcat

ENTRYPOINT ["/kafdrop.sh"]
