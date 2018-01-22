FROM ryohji/protobuf:7

RUN apt-get update\
 && apt-get remove python-pip python3-pip\
 && apt-get install --no-install-recommends libarchive13 libjsoncpp1 libuv1\
 && apt-get install --no-install-recommends cmake cmake-data\
 && apt-get install --no-install-recommends zip unzip\
 && apt-get install --no-install-recommends libarchive-dev\
 && apt-get install --no-install-recommends libpython2.7 libpython2.7-dev\
 && apt-get install --no-install-recommends libpython3.5 libpython3.5-dev\
 && apt-get upgrade -y\
 && apt-get clean\
 && rm -rf /var/lib/apt/lists/*
RUN wget https://bootstrap.pypa.io/get-pip.py\
 && python get-pip.py\
 && python3 get-pip.py\
 && pip2 install cython==0.25 numpy\
 && pip3 install cython==0.25 numpy
