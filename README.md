# Digital Design for FPGAs, with free tools
Learn to design synthesizable digital systems in FPGAs using ONLY free tools  #verilog #icestorm #lattice #Linux

[Wiki tutorial](https://github.com/Obijuan/open-fpga-verilog-tutorial/wiki)  

[Project IceStorm]http://www.clifford.at/icestorm/

Where are the Tools? How to install?
Installing prerequisites (this command is for Ubuntu 14.04):

sudo apt-get install build-essential clang bison flex libreadline-dev \
                     gawk tcl-dev libffi-dev git mercurial graphviz   \
                     xdot pkg-config python python3 libftdi-dev \
                     qt5-default python3-dev libboost-all-dev cmake libeigen3-dev
On Fedora 24 the following command installs all prerequisites:

sudo dnf install make automake gcc gcc-c++ kernel-devel clang bison \
                 flex readline-devel gawk tcl-devel libffi-devel git mercurial \
                 graphviz python-xdot pkgconfig python python3 libftdi-devel \
                 qt5-devel python3-devel boost-devel boost-python3-devel eigen3-devel
Note: All tools will be installed relative to /usr/local

## Installing the IceStorm Tools (icepack, icebox, iceprog, icetime, chip databases):

git clone https://github.com/YosysHQ/icestorm.git icestorm
cd icestorm
make -j$(nproc)
sudo make install

## Installing Arachne-PNR (place&route tool, predecessor to NextPNR):

git clone https://github.com/cseed/arachne-pnr.git arachne-pnr
cd arachne-pnr
make -j$(nproc)
sudo make install

## Installing NextPNR (place&route tool, Arachne-PNR replacement):

git clone https://github.com/YosysHQ/nextpnr nextpnr
cd nextpnr
cmake -DARCH=ice40 -DCMAKE_INSTALL_PREFIX=/usr/local .
make -j$(nproc)
sudo make install

## Installing Yosys (Verilog synthesis):

git clone https://github.com/YosysHQ/yosys.git yosys
cd yosys
make -j$(nproc)
sudo make install

Both place and route tools (Arachne-PNR & NextPNR) convert the IceStorm text chip databases into the respective PNR binary chip databases during build. Always rebuild the PNR tools after updating your IceStorm installation.

