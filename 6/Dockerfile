FROM ryohji/protobuf:gcc-6

ADD cmake-3.12.1.tar.gz /tmp
RUN cd /tmp/cmake-3.12.1\
 && ./configure --prefix=/usr\
 && make install\
 && rm -r /tmp/cmake-3.12.1

RUN echo "deb http://ftp.debian.org/debian jessie-backports main"\
 > /etc/apt/sources.list.d/jessie-backports.list\
 && apt-get update\
 && apt-get remove python-pip\
 && apt-get install --no-install-recommends libpython2.7 libpython2.7-dev\
 && apt-get install --no-install-recommends libarchive-dev libarchive13\
 && apt-get install --no-install-recommends zip unzip\
 && apt-get upgrade -y\
 && apt-get clean\
 && rm -rf /var/lib/apt/lists/* /etc/apt/sources.list.d/jessie-backports.list

RUN wget https://bootstrap.pypa.io/get-pip.py\
 && python get-pip.py\
 && pip2 install cython mako numpy pyyaml
