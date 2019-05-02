BootStrap: shub
From: shub://willgpaik/centos7_aci:latest

%setup

%files

%environment

%runscript

%post
  yum -y install cmake \
    subversion \
    libcurl-devel \
    netcdf-devel \
    gdal-devel \
    pcre-devel \
    fftw3-devel \
    lapack-devel \
    openblas-devel

  mkdir -p /opt/sw/
  cd /opt/sw
  git clone https://github.com/GenericMappingTools/gmt.git
  wget -nc ftp://ftp.star.nesdis.noaa.gov/pub/sod/lsa/gmt/gshhg-gmt-2.3.7.tar.gz
  wget -nc ftp://ftp.star.nesdis.noaa.gov/pub/sod/lsa/gmt/dcw-gmt-1.1.4.tar.gz
  tar -xf gshhg-gmt-2.3.7.tar.gz
  tar -xf dcw-gmt-1.1.4.tar.gz
  
  cd gmt
  mkdir build
  cd build
  cmake .. -DGSHHG_ROOT=../../gshhg-gmt-2.3.7 \
    -DDCW_ROOT=../../dcw-gmt-1.1.4
    
  make && make install
  
  cd /opt/sw
  rm *.tar.gz
  
