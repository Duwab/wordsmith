FROM golang

WORKDIR /app

COPY dispatcher.go .
# COPY *.go .
# COPY . .

RUN go build dispatcher.go

CMD ["./dispatcher"]

# Le répertoire appelé static doit être dans le répertoire courant lors du lancement du serveur.
