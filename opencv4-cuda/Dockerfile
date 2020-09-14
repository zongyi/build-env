FROM nvidia/cuda:10.1-devel

WORKDIR /opt

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && \
    apt-get -y install apt-transport-https ca-certificates && \
    apt-get update && \
    apt-get -y install git curl zip unzip tar cmake build-essential libeigen3-dev libopenblas-dev liblapack-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/microsoft/vcpkg && \
    ./vcpkg/bootstrap-vcpkg.sh

RUN ./vcpkg/vcpkg install "opencv4[nonfree,contrib,cuda,openmp,tbb]" && \
    rm -rf ./vcpkg/buildtrees
