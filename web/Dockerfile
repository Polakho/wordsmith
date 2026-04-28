FROM golang:1.26.2-alpine3.23
WORKDIR /app
COPY ./dispatcher.go .
COPY ./static .
RUN go build dispatcher.go

FROM scratch
WORKDIR /app
COPY --from=0 /app/dispatcher .
COPY ./static ./static
CMD ["./dispatcher"]