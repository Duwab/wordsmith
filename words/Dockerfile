FROM debian
RUN apt-get update
RUN apt-get install maven -y

WORKDIR /src
COPY . .

# Voici la commande qui permet d'invoquer maven pour compiler le programme :
RUN mvn verify

# Le résultat est un fichier appelé words.jar placé dans le répertoire target.
# Le serveur se lance ensuite avec la commande suivante :
WORKDIR target

#CMD ["java", "-Xmx8m", "-Xms8m", "-jar", "words.jar"]
CMD exec java -Xmx8m -Xms8m -jar words.jar
