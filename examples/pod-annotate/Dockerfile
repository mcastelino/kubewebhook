FROM golang:1.10 AS builder

WORKDIR /go/src/pod-annotate

COPY . ./
RUN go get ./... && CGO_ENABLED=0 go build -o /go/bin/pod-annotate

FROM alpine:3.7
COPY --from=builder /go/bin/pod-annotate /pod-annotate
ENTRYPOINT ["/pod-annotate"]

