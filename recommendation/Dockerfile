FROM golang:1.22.2-alpine3.19 as builder
WORKDIR /build
COPY . .
RUN go build -o myapp

# Stage 2: Final stage
FROM alpine:3.19
WORKDIR /app
COPY . .
COPY --from=builder /build/myapp .
EXPOSE 8080
CMD ["./myapp"]

