Bootstrap: docker
From: lsstdesc/stack-sims:w_2018_26-sims_2_9_0

%setup
  echo ${SINGULARITY_ROOTFS}
  mkdir ${SINGULARITY_ROOTFS}/home

%post
  source scl_source enable devtoolset-6 &&\
  source /opt/lsst/software/stack/loadLSST.bash &&\
  setup lsst_apps &&\

%runscript
  cd ${SINGULARITY_ROOTFS}/home
  eups list
