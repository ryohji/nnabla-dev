FROM ryohji/protobuf:gcc-5

RUN echo "deb http://ftp.debian.org/debian jessie-backports main"\
 > /etc/apt/sources.list.d/jessie-backports.list\
 && apt-get update\
 && apt-get remove python-pip\
 && apt-get install --no-install-recommends libarchive13 libjsoncpp1 libuv1\
 && apt-get install --no-install-recommends cmake cmake-data\
 && apt-get install --no-install-recommends zip unzip\
 && apt-get install --no-install-recommends libarchive-dev\
 && apt-get install --no-install-recommends libpython2.7 libpython2.7-dev\
 && apt-get upgrade -y\
 && apt-get clean\
 && rm -rf /var/lib/apt/lists/* /etc/apt/sources.list.d/jessie-backports.list
RUN wget https://bootstrap.pypa.io/get-pip.py\
 && python get-pip.py\
 && pip2 install cython==0.25 numpy\
