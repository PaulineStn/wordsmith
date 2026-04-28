FROM maven:3-eclipse-temurin-11-alpine AS build

WORKDIR /src

COPY pom.xml .

RUN mvn dependency:go-offline

COPY src ./src

RUN mvn verify

FROM eclipse-temurin:11-jre-alpine

WORKDIR /app
COPY --from=build /src/target/dependency ./dependency
COPY --from=build /src/target/words.jar .

CMD ["java", "-Xmx8m", "-Xms8m", "-jar", "words.jar"]