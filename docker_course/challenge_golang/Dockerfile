FROM golang:1.14 AS BUILDER

WORKDIR $GOPATH/src/main/hello/

COPY . .

RUN go build -ldflags "-s -w" -o /app

FROM scratch

COPY --from=builder /app .

ENTRYPOINT ["/app"]