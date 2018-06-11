BootStrap: docker
From: wangjia94/docker1

%labels
Maintainer Jia Wang
Version v1.0

%runscript
    echo "Welcome, this is Singularity container for FSO"
    echo "Rooooar!"
    echo "Arguments received: $*"
    exec echo "$@"

%environments
    NETCDF=/usr
    WRFIO_NCD_LARGE_FILE_SUPPORT=1
    LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH
    FSO_HOME=/
    PATH=.:$PATH
    NCARG_ROOT=/usr 
    ECFLOW_USER=ecflow 
    ECF_PORT=2500 
    ECF_HOME=/home/ecflow 
    LANG=en_US.UTF-8 
    DISPLAY=:0 
    PYTHONPATH=/usr/local/lib/python2.7/site-packages
    export NETCDF FSO_HOME WRFIO_NCD_LARGE_FILE_SUPPORT $LD_LIBRARY_PATH PATH NCARG_ROOT ECFLOW_USER ECF_PORT ECF_HOME LANG DISPLAY PYTHONPATH

%files
    WRFV3

%post
    mkdir -p /FSO3.4
    mkdir -p /gjx_working
    mkdir -p /gjx_static
    mkdir -p /gfs
    mkdir -p /little_r
    mkdir -p /WJ
    mkdir -p /radar


    ulimit -s unlimited
 #   wget https://pan.baidu.com/s/1CY1As9qEkIZ3fRgsdKLhmA
 #   tar -zxvf WRFV3.9.1.1.TAR.gz

     # Build WRF
     cd /WRFV3
     cp configure.wrf.gnu configure.wrf
     ./compile em_real


