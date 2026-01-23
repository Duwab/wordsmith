FROM golang AS build

WORKDIR /app

COPY dispatcher.go .
# COPY *.go .
# COPY . .

ARG CGO_ENABLED=0
RUN --mount=type=cache,target=/root/.cache/go-build go build dispatcher.go


FROM scratch

WORKDIR /app

COPY --from=build /app/dispatcher .

#CMD ./dispatcher no parsing so root and cannot be sigint
CMD ["./dispatcher"]

EXPOSE 80
