FROM golang:1.13
MAINTAINER MJ

ENV GOPROXY=https://goproxy.io
ENV PATH="$PATH:/builder/protoc-3.10.1-linux-x86_64/bin"

WORKDIR /builder
COPY protoc-3.10.1-linux-x86_64/ ./protoc-3.10.1-linux-x86_64
RUN go get -u github.com/golang/protobuf/protoc-gen-go

ENTRYPOINT ["protoc"]
