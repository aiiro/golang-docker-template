FROM golang:1.19-alpine3.16

RUN apk update --update \
    && apk --no-cache add g++ gcc git build-base make curl

ARG AIR_VER=v1.40.4
ARG DELVE_VER=v1.20.1

RUN curl -sSfL https://raw.githubusercontent.com/cosmtrek/air/master/install.sh | sh -s -- -b $(go env GOPATH)/bin ${AIR_VER} \
    && go install github.com/go-delve/delve/cmd/dlv@${DELVE_VER}

COPY ./src /var/app

WORKDIR /var/app

RUN go mod download

CMD ["sh", "-c", "main"]
