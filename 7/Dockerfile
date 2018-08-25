FROM ryohji/protobuf:gcc-7

ADD cmake-3.12.1.tar.gz /tmp
RUN cd /tmp/cmake-3.12.1\
 && ./configure --prefix=/usr\
 && make install\
 && rm -r /tmp/cmake-3.12.1

RUN apt-get update\
 && apt-get remove python3-pip\
 && apt-get install --no-install-recommends libpython3.5 libpython3.5-dev\
 && apt-get install --no-install-recommends libarchive-dev libarchive13\
 && apt-get install --no-install-recommends zip unzip\
 && apt-get upgrade -y\
 && apt-get clean\
 && rm -rf /var/lib/apt/lists/*

RUN wget https://bootstrap.pypa.io/get-pip.py\
 && python3 get-pip.py\
 && pip3 install cython mako numpy pyyaml six
