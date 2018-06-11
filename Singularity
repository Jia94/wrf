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
    wget -c --referer=https://pan.baidu.com/s/1CY1As9qEkIZ3fRgsdKLhmA -O WRFV3.9.1.1.TAR.gz "https://gzcu01.baidupcs.com/file/11b19933a3b1fee2d91b8d19c0893958?bkt=p3-0000c7eff89c40c0c84a3225402d09bd8e7d&fid=86948151-250528-1078317426520899&time=1528727641&sign=FDTAXGERLQBHSK-DCb740ccc5511e5e8fedcff06b081203-hNyHBox4DNvGrZT0BYxZn8B0loE%3D&to=86&size=41432716&sta_dx=41432716&sta_cs=7&sta_ft=gz&sta_ct=4&sta_mt=4&fm2=MH%2CYangquan%2CAnywhere%2C%2Cbeijing%2Ccnc&vuk=3526194532&iv=0&newver=1&newfm=1&secfm=1&flow_ver=3&pkey=0000c7eff89c40c0c84a3225402d09bd8e7d&sl=76480590&expires=8h&rt=sh&r=981932075&mlogid=3755852412089879582&vbdid=4004425025&fin=WRFV3.9.1.1.TAR.gz&fn=WRFV3.9.1.1.TAR.gz&rtype=1&dp-logid=3755852412089879582&dp-callid=0.1.1&hps=1&tsl=80&csl=80&csign=Qf7D59Lq6%2B1nmGuPaW1Xy75d9ws%3D&so=0&ut=6&uter=4&serv=0&uc=4236781674&ic=3317565971&ti=54c943154d862903d589344e08c962e29e569d829293b0f2&by=themis"
    tar -zxvf WRFV3.9.1.1.TAR.gz

     # Build WRF
     cd /WRFV3
     cp configure.wrf.gnu configure.wrf
     ./compile em_real


