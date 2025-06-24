# Build Stage
FROM golang:1.20-alpine AS build
WORKDIR /app
COPY . .
RUN go build -o main .

# Run Stage
FROM alpine
WORKDIR /app
COPY --from=build /app/main .
EXPOSE 8001
CMD ["./main"]
