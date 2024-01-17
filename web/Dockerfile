FROM golang:latest as build
WORKDIR /app
COPY dispatcher.go .

# Build
RUN go build dispatcher.go
FROM alpine:latest
RUN apk add --no-cache libc6-compat 

WORKDIR /app
COPY --from=build /app/* /app/
RUN mkdir -p /app/static
COPY ./static /app/static

#80 port for app
EXPOSE 80

#execute
CMD ["./dispatcher"]