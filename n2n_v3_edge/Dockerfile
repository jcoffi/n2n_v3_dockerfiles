FROM alpine:latest AS build-env

MAINTAINER <doraismydora@gmail.com>

RUN apk update && apk upgrade
RUN apk add build-base openssl-dev zstd-dev git cmake linux-headers

WORKDIR /root

RUN cd /root && \
git clone --depth 1 --branch 3.1.1 https://github.com/ntop/n2n.git && \
cd n2n && mkdir build && cd build && \
cmake .. "-DN2N_OPTION_USE_OPENSSL=ON" "-DN2N_OPTION_USE_ZSTD=ON" && \
cmake --build . && \
cmake --install .

FROM alpine:latest
RUN apk update && apk upgrade --no-cache && apk add openssl zstd-libs --no-cache
COPY --from=build-env /usr/local/sbin/supernode /usr/sbin/
COPY --from=build-env /usr/local/sbin/edge /usr/sbin/
COPY --from=build-env /root/n2n/packages/etc/n2n /etc/n2n
COPY ./start /usr/sbin/start_edge
CMD /usr/sbin/start_edge
