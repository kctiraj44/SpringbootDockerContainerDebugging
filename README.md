FROM openjdk:8
EXPOSE 8080 8000
ADD target/spring-docker-demo.jar spring-docker-demo.jar
ADD entrypoint.sh entrypoint.sh
ENTRYPOINT ["sh","/entrypoint.sh"]

java -Xdebug -Xrunjdwp:transport=dt_socket,server=y,address=8000,suspend=n -jar spring-docker-demo.jar

find remote debug JVM in config and add the configurations
