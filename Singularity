BootStrap: docker
From: ubuntu:16.04

# Based on https://git.scicore.unibas.ch/escobar/singularity-examples/blob/381d3ca4d5a34e4debf6d342c46f7fbbaf47aa73/singularity_conda.def
# sciCore Singularity exercise, University of Basel, 06.03.2018

%post
    # install some system deps
    apt-get -y update
    apt-get -y install locales curl bzip2
    locale-gen en_US.UTF-8
    apt-get clean

    # download and install miniconda2
    curl -sSL -O https://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86_64.sh
    bash Miniconda2-latest-Linux-x86_64.sh -p /opt/miniconda2 -b
    rm -fr Miniconda2-latest-Linux-x86_64.sh

    # use conda to install some bioinfo tools
    conda install --yes -c bioconda samtools==1.7
    conda install --yes -c bioconda bwa=0.7.8
    conda install --yes -c bioconda aragorn=1.2.38
    conda install --yes -c bioconda lapack=3.6.0
#    conda install --yes -c bioconda bioconductor-chimera

%environment
    export LANG=en_US.UTF-8
    export LANGUAGE=en_US:en
    export LC_ALL=en_US.UTF-8
    export PATH=/opt/miniconda2/bin:$PATH

%apphelp samtools
    "samtools version 1.7"

%apprun samtools
    /opt/miniconda2/bin/samtools

%apphelp bwa
    "BWA version 0.7.8"

%apprun bwa
    /opt/miniconda2/bin/bwa

%apphelp aragorn
    "aragorn version 1.2.38"

%apprun aragorn
    /opt/miniconda2/bin/aragorn

%apphelp lapack
    "LAPACK version 3.6.0"

%apprun lapack
    /opt/miniconda2/bin/lapack

# %apphelp bioconductor-chimera
#    "bioconductor-chimera version 1.20.0"
#
# %apprun bioconductor-chimera
#    /opt/miniconda2/bin/bioconductor-chimera





