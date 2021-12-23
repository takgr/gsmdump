# gsmdump
Multi channel scalable feeder to gr-gsm

Software required:
Gnuradio 3.8 or later, csdr, gr-pipe, gr-gsm 

Installation commands on Ubuntu 20.04

sudo apt-get update
sudo apt-get upgrade
sudo apt install uhd-host
sudo apt install python3-scapy
sudo apt-get install python3-mysqldb python3-decouple net-tools
sudo apt-get install -y  gnuradio gnuradio-dev git cmake autoconf libtool pkg-config g++ gcc make libc6 libc6-dev libcppunit-dev swig doxygen liblog4cpp5v5 liblog4cpp5-dev  gr-osmosdr libosmocore libosmocore-dev
sudo apt install liborc-0.4-dev
echo 'export PYTHONPATH=/usr/local/lib/python3/dist-packages/:$PYTHONPATH' >> ~/.bashrc
export PYTHONPATH=/usr/local/lib/python3/dist-packages/:$PYTHONPATH

sudo sysctl kernel.shmmni=32000
sudo sysctl -w net.core.wmem_max=2500000

git clone https://github.com/Oros42/IMSI-catcher.git


git clone https://git.osmocom.org/gr-gsm
cd gr-gsm/
mkdir build
cd build/
cmake ../
make -j4
sudo make install
sudo ldconfig


git clone -b master https://github.com/jketterl/csdr.git
cd csdr
mkdir build
cd build
cmake ..
make
sudo make install
sudo ldconfig
cd



git clone git://github.com/jolivain/gr-pipe.git
mkdir gr-pipe/build
cd gr-pipe/build
cmake ..
make
sudo make install
cd

