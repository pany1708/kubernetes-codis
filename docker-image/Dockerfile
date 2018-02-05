FROM golang:1.8
MAINTAINER jikun.zhang <jikun.zhang@edaibu.net>
ENV GOPATH /gopath
ENV CODIS  ${GOPATH}/src/github.com/CodisLabs/codis
ENV PATH   ${GOPATH}/bin:${PATH}:${CODIS}/bin
COPY . ${CODIS}
RUN apt-get update && \
    apt-get install -y autoconf && \
    make -C ${CODIS} distclean && \
    make -C ${CODIS} build-all && \
    apt-get clean && apt-get autoclean
COPY config/redis.conf /gopath/src/github.com/CodisLabs/codis/config/redis.conf
WORKDIR /codis
