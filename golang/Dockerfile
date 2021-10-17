FROM golang:1.16-alpine AS builder

WORKDIR /app

COPY go.mod ./
COPY go.sum ./

RUN go mod download

COPY *.go ./

RUN CGO_ENABLED=0 go build -ldflags '-extldflags "-static"' -o /hello-world

# FROM alpine:3.13
FROM scratch

COPY --from=builder /hello-world /

CMD [ "/hello-world" ]
