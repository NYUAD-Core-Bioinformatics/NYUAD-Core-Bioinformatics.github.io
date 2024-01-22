Anvio
------

Anvi’o is a comprehensive platform that brings together many aspects of today’s cutting-edge computational strategies of data-enabled microbiology,
including genomics, metagenomics, metatranscriptomics, pangenomics, metapangenomics, phylogenomics, and microbial population genetics in an integrated
and easy-to-usefashion through extensive interactive visualization capabilities.

Anvio can be install using conda as follows and this is based on version 7.1
Reference:- https://anvio.org/

.. code:: bash

    $ conda create -p /scratch/gencore/conda3/envs/anvio-7  python=3.6 -y
    $ source  activate /scratch/gencore/conda3/envs/anvio-7
    $ conda install -y -c bioconda "sqlite>=3.31.1"
    $ conda install -y -c bioconda prodigal
    $ conda install -y -c bioconda mcl
    $ conda install -y -c bioconda muscle=3.8.1551
    $ conda install -y -c bioconda hmmer
    $ conda install -y -c bioconda diamond
    $ conda install -y -c bioconda blast
    $ conda install -y -c bioconda megahit
    $ conda install -y -c bioconda spades
    $ conda install -y -c bioconda bowtie2 tbb=2019.8
    $ conda install -y -c bioconda bwa
    $ conda install -y -c bioconda samtools=1.9
    $ conda install -y -c bioconda centrifuge
    $ conda install -y -c bioconda trimal
    $ conda install -y -c bioconda iqtree
    $ conda install -y -c bioconda trnascan-se
    $ conda install -y -c bioconda r-base
    $ conda install -y -c bioconda r-stringi
    $ conda install -y -c bioconda r-tidyverse
    $ conda install -y -c bioconda r-magrittr
    $ conda install -y -c bioconda r-optparse
    $ conda install -y -c bioconda bioconductor-qvalue
    $ conda install -y -c bioconda fasttree
    $ conda install -y -c bioconda vmatch
    $ conda install -y -c bioconda fastani

Then download anvio package as follows:- 

.. code:: bash

    $ curl -L https://github.com/merenlab/anvio/releases/download/v7.1/anvio-7.1.tar.gz   
    $ pip install anvio-7.1.tar.gz

