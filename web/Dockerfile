FROM golang

WORKDIR /app

COPY dispatcher.go .
# COPY *.go .
# COPY . .

RUN go build dispatcher.go

#CMD ./dispatcher no parsing so root and cannot be sigint
CMD ["./dispatcher"]

EXPOSE 80
