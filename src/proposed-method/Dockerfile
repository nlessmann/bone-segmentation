FROM ubuntu:18.04

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update --fix-missing && \
    apt-get install -y cmake g++ libinsighttoolkit4-dev libgdcm*

COPY src/ /bonesegm/src/
WORKDIR /bonesegm/src/
RUN cmake . && \
    make && \
    mkdir ../bin && \
    cp SegmentBoneFromCT ../bin/SegmentBoneFromCT

WORKDIR /bonesegm/bin
ENTRYPOINT ["./SegmentBoneFromCT"]
