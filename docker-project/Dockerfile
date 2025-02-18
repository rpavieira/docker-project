FROM golang:alpine AS builder
WORKDIR /app
COPY main.go .
COPY go.mod .
COPY Dockerfile .
RUN go build -o fullcycle

FROM scratch
COPY --from=builder /app/fullcycle .
CMD ["./fullcycle"]