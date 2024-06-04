FROM maven:3.8.7-eclipse-temurin-19 as build
WORKDIR /app
COPY pom.xml .
COPY src/ src/
RUN mvn package -DskipTests

FROM eclipse-temurin:21.0.2_13-jre-alpine
COPY --from=build /app/target/voting-0.0.1-SNAPSHOT.jar /app/target/voting-0.0.1-SNAPSHOT.jar
EXPOSE 8080
WORKDIR /app/target
CMD ["java","-jar","voting-0.0.1-SNAPSHOT.jar"]


