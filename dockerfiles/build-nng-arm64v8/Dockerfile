# jeikabu/debian-build-nng:arm64v8-buster
# Build NNG ARM64
# Volumes:
# /usr/src = build output
# Example:
# mkdir -p /tmp/binary-output
# docker run --rm -t -v /tmp/binary-output:/usr/src <image id>

FROM jeikabu/debian-build:arm64v8-buster

ARG NNG_BRANCH=v1.2.4

RUN git clone https://github.com/nanomsg/nng.git \
    && cd nng && git checkout $NNG_BRANCH

CMD cd /usr/src \
    && cmake -G "Unix Makefiles" -DBUILD_SHARED_LIBS=ON -DCMAKE_BUILD_TYPE=Release -DNNG_TESTS=OFF -DNNG_TOOLS=OFF /nng \
    && make
