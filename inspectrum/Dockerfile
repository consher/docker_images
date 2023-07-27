FROM ubuntu

RUN apt-get update -y
RUN apt-get install -y \
    git \
    qtbase5-dev \
    libfftw3-dev \
    cmake \
    pkg-config \
    libliquid-dev
RUN git clone https://github.com/miek/inspectrum.git
WORKDIR /inspectrum/
RUN mkdir build
WORKDIR /inspectrum/build
RUN apt-get install -y build-essential
RUN cmake ..
RUN make -j4
RUN make install
WORKDIR /radio_data
COPY . .
CMD /bin/bash