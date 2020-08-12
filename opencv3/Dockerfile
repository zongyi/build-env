FROM debian

WORKDIR /opt

RUN apt-get update && \
    apt-get -y install apt-transport-https ca-certificates && \
    apt-get update && \
    apt-get -y install git curl zip unzip tar cmake build-essential
RUN git clone https://github.com/microsoft/vcpkg && \
    ./vcpkg/bootstrap-vcpkg.sh
RUN ./vcpkg/vcpkg install "opencv3[nonfree,contrib]"
