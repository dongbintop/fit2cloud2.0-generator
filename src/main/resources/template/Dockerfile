FROM registry.fit2cloud.com/public/fabric8-java-alpine-openjdk8-jre:latest

MAINTAINER FIT2CLOUD <support@fit2cloud.com>

RUN mkdir -p /opt/apps

ADD target/#{applicationName}-#{version}.jar /opt/apps

ENV JAVA_APP_JAR=/opt/apps/#{applicationName}-#{version}.jar

ENV AB_OFF=true

ENV JAVA_OPTIONS=-Dfile.encoding=utf-8

HEALTHCHECK --interval=15s --timeout=5s --retries=20 --start-period=30s CMD curl -f 127.0.0.1:#{projectPort}

CMD ["/deployments/run-java.sh"]
