FROM golang:alpine AS builder
WORKDIR /app

COPY main.go .

RUN go mod init main.go && go mod tidy && \
    CGO_ENABLED=0 go build -ldflags="-s -w" -o fullcycle

FROM scratch
COPY --from=builder /app/fullcycle .
CMD ["./fullcycle"]
