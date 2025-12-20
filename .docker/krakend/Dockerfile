FROM docker.io/library/golang:tip-alpine3.21 AS reflex

RUN go install github.com/cespare/reflex@latest


FROM docker.io/library/krakend:2.11.0

COPY --from=reflex /go/bin/reflex /usr/bin/reflex

ADD entrypoint.sh /

WORKDIR /etc/krakend

ENTRYPOINT [ "/entrypoint.sh" ]
