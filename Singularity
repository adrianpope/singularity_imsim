Bootstrap: docker
From: lsstdesc/stack-sims:w_2018_26-sims_2_9_0

%setup
   echo ${SINGULARITY_ROOTFS}
   mkdir ${SINGULARITY_ROOTFS}/DC2

%post
   set +e
   source scl_source enable devtoolset-6
   set -e
   source /opt/lsst/software/stack/loadLSST.bash
   setup lsst_apps
   cd /DC2
   git clone https://github.com/lsst/sims_GalSimInterface.git
   git clone https://github.com/LSSTDESC/imSim.git
   set +e
   setup -r sims_GalSimInterface -j
   set -e
   setup -r imSim -j
   cd sims_GalSimInterface
   scons
   cd ../imSim
   scons

%runscript
   cd /DC2/imSim
   py.test
