# BUILD
FROM golang:alpine as builder

COPY web/dispatcher.go .
RUN go build dispatcher.go

# RUN
FROM alpine

EXPOSE 80
CMD ["/dispatcher"]

COPY --from=builder /go/dispatcher /
COPY web/static /static/
