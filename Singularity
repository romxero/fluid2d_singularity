Bootstrap: docker
From: debian:buster-slim

%labels
Author "Randall Cab White - rcwhite@stanford.edu"


#########
#%setup
#########

#Downlaod packages
%post
  apt-get -ym update
  apt-get -ym install  libnetcdf-mpi-13 libnetcdf-mpi-dev libnetcdf-pnetcdf-13 libnetcdf-pnetcdf-dev  python-netcdf4 python3-netcdf4  \
  libnetcdff-dev libnetcdff-doc libnetcdff6 git \
  curl wget python-pip python3-pip
##git section

	git clone https://github.com/pvthinker/Fluid2d.git
	cd Fluid2d
	pip install -r requirements.txt
	python setup.py build_ext --inplace
	make 
	make 

%environment
  export IMAGE_NAME="Fluid2D"
  export PYTHONPATH=/Fluid2d/core:$PYTHONPATH

  
  
