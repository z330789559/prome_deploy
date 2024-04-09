FROM docker.io/openjdk:8-jdk

USER root
ARG service=back-admin
ARG port=8080

ENV JAVA_ARGS="-Dfile.encoding=UTF8 -Duser.timezone=GMT+08"
ENV APP_NAME=${service}
ENV JAVA_OPTS="-Xms2048m -Xmx2048m  -XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath=//tmp/logs/${service}/dump.hprof"



WORKDIR /app
ADD ./application.yml application.yml 
ADD ./application-druid.yml application-druid.yml
ADD ./${service}.jar ${service}.jar
RUN echo "Asia/Shanghai" > /etc/timezone

EXPOSE ${port}

CMD java ${JAVA_ARGS} ${JAVA_OPTS} -verbose:gc     -jar ${APP_NAME}.jar

