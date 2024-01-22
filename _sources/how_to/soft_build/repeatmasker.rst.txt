Repeatmasker
------------

RepeatMasker is a program that screens DNA sequences for interspersed repeats and low complexity DNA sequences.
This installation procedure is based on v4.1.5

Reference:- https://www.repeatmasker.org/RepeatMasker/

Download repeatmasker version 4.1.5 from this `link <https://www.repeatmasker.org/RepeatMasker/RepeatMasker-4.1.5.tar.gz>`__

Copy the downloaded file to the install location and extract in jubail.

.. code:: bash

    $ cp RepeatMasker-4.1.5.tar.gz /scratch/gencore/softwares/
    $ cd /scratch/gencore/softwares/
    $ tar -xvf RepeatMasker-4.1.5.tar.gz
    $ mv RepeatMasker RepeatMasker-4.1.5

Then we would need to install the prerequisites for building this package. We can accomplish this by using the anaconda. 

.. code:: bash

    $ module load gencore/1
    $ module load Miniconda3/4.7.10
    $ conda create -p /scratch/gencore/conda3/envs/repeatmasker4.1.5 -c conda-forge -c bioconda hmmer rmblast trf bioawk -y
    $ source activate /scratch/gencore/conda3/envs/repeatmasker4.1.5

Place the RepBase RepeatMasker Edition ( final version 10/26/2018 )  in the install directory and extract the contents.

.. code:: bash

    $ cp /scratch/Reference_Genomes/Public/RepeatMasker/RepBaseRepeatMaskerEdition-20181026.tar.gz /scratch/gencore/softwares/RepeatMasker-4.1.5/
    $ cd /scratch/gencore/softwares/RepeatMasker-4.1.5/
    $ tar -xvf RepBaseRepeatMaskerEdition-20181026.tar.gz

Download the Dfam 3.7 Library from this `link <https://www.dfam.org/releases/Dfam_3.7/families/Dfam.h5.gz>`__ and extract the contents to the Libraries directory.

.. code:: bash

    $ cp /scratch/Reference_Genomes/Public/RepeatMasker/Dfam.h5.gz /scratch/gencore/softwares/RepeatMasker-4.1.5/
    $ gunzip Dfam.h5.gz
    $ mv Dfam.h5 Libraries/

Run the Configure script as follows:-

.. code:: bash

    $ perl ./configure -libdir /scratch/gencore/software/RepeatMasker-4.1.5/Libraries -trf_prgm /scratch/gencore/conda3/envs/repeatmasker4.1.5/bin/trf 
    -rmblast_dir /scratch/gencore/conda3/envs/repeatmasker4.1.5/bin/ -hmmer_dir /scratch/gencore/conda3/envs/repeatmasker4.1.5/bin 
    -abblast_dir /scratch/gencore/conda3/envs/repeatmasker4.1.5/bin -crossmatch_dir /scratch/gencore/conda3/envs/repeatmasker4.1.5/bin 
    -default_search_engine rmblast

Great, you may see below message once the setup is done.

.. code:: bash

    Building FASTA version of RepeatMasker.lib ......................................................................
    Building RMBlast frozen libraries..
    The program is installed with a the following repeat libraries:
    File: /scratch/gencore/software/RepeatMasker-4.1.5/Libraries/RepeatMaskerLib.h5
    FamDB Generator: famdb.py v0.4.2
    FamDB Format Version: 0.5
    FamDB Creation Date: 2023-01-08 10:42:05.645898

    Database: Dfam withRBRM
    Version: 3.7
    Date: 2023-01-11

To load the modules, follow below procedure.

Launch a new session in jubail.

.. code:: bash

    $ module load gencore/1
    $ module load Miniconda3/4.7.10
    $ source activate /scratch/gencore/conda3/envs/repeatmasker4.1.5
    $ export PATH='/scratch/gencore/software/RepeatMasker-4.1.5:/scratch/gencore/software/RepeatMasker-4.1.5/util':$PATH

