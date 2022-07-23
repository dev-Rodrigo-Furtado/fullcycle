FROM golang:1.18.4 AS builder

WORKDIR /home/app/fullcycle

COPY ./fullcycle.go .

RUN go mod init example/fullcycle && go build


FROM scratch

WORKDIR /home/app/fullcycle

COPY --from=builder /home/app/fullcycle/fullcycle .

CMD ["./fullcycle"]