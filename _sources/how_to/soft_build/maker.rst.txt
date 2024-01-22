Maker
-----

MAKER is a portable and easily configurable genome annotation pipeline.
Its purpose is to allow smaller eukaryotic and prokaryotic genome projects to independently annotate their genomes and to create genome databases.

This is based on Maker version 3.01.04
Reference:- https://www.yandell-lab.org/software/maker.html

Prerequisites

.. code:: bash

    blast - 2.13.0
    snap - 2013_11_29
    exonerate - 2.4.0
    genblasta - 1.0.4
    RepeatMasker - 4.1.2.p1
    snoscan - 1.0 
    trnascan-se - 2.0.9
    interproscan - 5.55_88.0

.. code:: bash

    $ module load gencore
    $ module load Miniconda3/4.7.10
    $ conda create -p /scratch/gencore/conda3/envs/maker3 -c conda-forge perl=5.26.2
    $ source activate /scratch/gencore/conda3/envs/maker3
    $ wget http://weatherby.genetics.utah.edu/maker_downloads/D2BE/7CA3/067C/DC399810E1834576C76C4203FC4A/maker-3.01.04.tgz

Extract the file and switch to build directory which is ../maker/src/ and execute "perl Build.PL" to check the list of dependencies.

.. code:: bash

    $ tar -xvf maker-3.01.04.tgz
    $ cd maker/src/
    $ perl Build.PL

Below commands solves perl dependencies

.. code:: bash

    $ conda install -c bioconda   perl-io-all perl-inline-c
    $ conda install -c bioconda perl-forks perl-want perl-bit-vector perl-bit-vector perl-dbd-sqlite perl-perl-unsafe-signals perl-dbd-pg
    $ conda install -c bioconda   perl-bioperl-core

Below commands solves external softwares like blast, snap, exonerate etc..

.. code:: bash

    $ conda install -c bioconda snap exonerate blast
    $ conda install -c bioconda snoscan trnascan-se interproscan
    $ conda install -c bioconda repeatmasker

Note:- if conda for repeatmasker fails, try below 

.. code:: bash

    $ ./Build installexes 
    $ conda install -c bioconda genblasta
    $ conda install -c bioconda blast-legacy 

Preparing the environment, you may see below message. 

.. code:: bash

    $ perl Build.PL
    ==============================================================================
    STATUS MAKER v2.31.11
    ==============================================================================
    PERL Dependencies:	VERIFIED
    External Programs:	VERIFIED
    External C Libraries:	VERIFIED
    MPI SUPPORT:		DISABLED
    MWAS Web Interface:	DISABLED
    MAKER PACKAGE:		CONFIGURATION OK

To build the installation proceed below 

.. code:: bash

    $ ./Build install
    Building MAKER
    Installing MAKER...
    Building MAKER
    Installing /scratch/gencore/software/maker2/src/../perl/lib/MAKER/ConfigData.pm
    Installing /scratch/gencore/software/maker2/src/../perl/lib/Parallel/Application/MPI.pm
    Installing /scratch/gencore/software/maker2/src/../perl/man/MAKER::ConfigData.3
    Installing /scratch/gencore/software/maker2/src/../bin/map_data_ids
    Installing /scratch/gencore/software/maker2/src/../bin/maker_map_ids
    Installing /scratch/gencore/software/maker2/src/../bin/fasta_tool
    Installing /scratch/gencore/software/maker2/src/../bin/iprscan2gff3
    Installing /scratch/gencore/software/maker2/src/../bin/genemark_gtf2gff3
    Installing /scratch/gencore/software/maker2/src/../bin/maker_functional_gff
    Installing /scratch/gencore/software/maker2/src/../bin/chado2gff3
    Installing /scratch/gencore/software/maker2/src/../bin/tophat2gff3
    Instruction to run maker2 as normal user
    ===

To load the maker package.

.. code:: bash


  $  module load gencore
  $  module load Miniconda3/4.7.10
  $  source activate /scratch/gencore/conda3/envs/maker3
  $  export PATH="/scratch/gencore/.eb/2.0/software/augustus/3.4.0/bin:$PATH"
  $  export PATH="/scratch/gencore/software/gmes_linux_64:$PATH"
  $  export PATH="/scratch/gencore/software/ab-blast:$PATH"
  $  export PATH="/scratch/gencore/software/genemark_prokaryotic:$PATH"
  $  export PATH="/scratch/gencore/software/maker3/bin:$PATH"
  $  maker -h

Database location for Maker

.. code:: bash

    $ /scratch/Reference_Genomes/Public/maker2_datasets/