FROM debian AS build
RUN apt-get update
RUN apt-get install maven -y

WORKDIR /src
COPY . .

# Voici la commande qui permet d'invoquer maven pour compiler le programme :
RUN mvn verify

FROM amazoncorretto:8-alpine3.23-jre

# FROM debian
# RUN apt-get update
# RUN apt-get install default-jre -y

WORKDIR /app

COPY --from=build /src/target .

#CMD ["java", "-Xmx8m", "-Xms8m", "-jar", "words.jar"]
CMD exec java -Xmx8m -Xms8m -jar words.jar
