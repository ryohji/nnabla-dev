FROM ryohji/protobuf:gcc-7

RUN apt-get update\
 && apt-get remove python-pip python3-pip\
 && apt-get install --no-install-recommends libpython2.7 libpython2.7-dev\
 && apt-get install --no-install-recommends libpython3.5 libpython3.5-dev\
 && apt-get install --no-install-recommends libarchive-dev libarchive13\
 && apt-get install --no-install-recommends zip unzip\
 && apt-get upgrade -y\
 && apt-get clean\
 && rm -rf /var/lib/apt/lists/*

RUN wget https://bootstrap.pypa.io/get-pip.py\
 && python get-pip.py\
 && python3 get-pip.py\
 && pip2 install mako pyyaml\
 && pip3 install cython numpy six

ADD cmake-3.12.1.tar.gz /tmp
RUN cd /tmp/cmake-3.12.1\
 && ./configure --prefix=/usr\
 && make install\
 && rm -r /tmp/cmake-3.12.1
