FROM golang as compile

WORKDIR /app

COPY *.go /app

RUN go build -ldflags "-s -w" main.go

FROM scratch

WORKDIR /app

COPY --from=compile /app/main /app/main

CMD [ "/app/main" ]