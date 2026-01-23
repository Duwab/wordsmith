FROM golang AS build

WORKDIR /app

COPY dispatcher.go .
# COPY *.go .
# COPY . .

ARG CGO_ENABLED=0
RUN go build dispatcher.go


FROM scratch

WORKDIR /app

COPY --from=build /app/dispatcher .

#CMD ./dispatcher no parsing so root and cannot be sigint
CMD ["./dispatcher"]

EXPOSE 80
