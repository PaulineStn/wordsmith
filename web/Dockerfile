FROM golang:alpine AS build

WORKDIR /src
COPY dispatcher.go .
RUN go build -o dispatcher dispatcher.go

FROM alpine:latest

WORKDIR /app
COPY --from=build /src/dispatcher .
COPY static ./static

CMD ["./dispatcher"]