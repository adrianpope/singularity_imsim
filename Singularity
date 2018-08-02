Bootstrap: docker
From: lsstdesc/stack-sims:w_2018_26-sims_2_9_0

%post
   set +e
   source scl_source enable devtoolset-6
   set -e
   source /opt/lsst/software/stack/loadLSST.bash
   setup lsst_sims
   umask 0000
   mkdir /DC2
   cd /DC2
   git clone https://github.com/lsst/sims_GalSimInterface.git
   git clone https://github.com/LSSTDESC/imSim.git
   setup -r sims_GalSimInterface -j
   setup -r imSim -j
   cd sims_GalSimInterface
   set +e
   scons
   set -e
   cd ../imSim
   scons
   #py.test

%runscript
   
