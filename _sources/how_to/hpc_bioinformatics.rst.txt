
HPC Bioinfomatics Software Stack
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

How we add packages in jubail 
------------------------------

We added packages in below methods. 

* Installed via easybuild ( eg:- module load samtools/1.9 )
* Installed via conda environment ( eg:- source activate /scratch/gencore/conda3/envs/repeatmasker4.1.5 )
* Installed via compiling from source ( eg:- Using the tar.gz of the package )
* Installed via singularity in jubail ( this is still experimental )
* Installed via Docker on our annotation server. 


Loading package using conda 
----------------------------

This section explains how to load modules under gencore/2. 

To load gencore2 modules 

.. code:: bash

    $ module load all 
    $ module load gencore/2 



1) Specify the first two letter of the software, and hit tab twice and you may able to see the options of software.     
    In the below example, I searched for samtools package, I entered first two letter and hit tab button twice 

.. code:: bash

    $ module load sa
      salmon/    samtools/  savage/

2)  Good, now I can see there is a module for samtools under gencore/2. If you find the package and then to check if you require any specific version of samtools, 
    again issue tab button twice, you are able to see the versions. 

.. code:: bash

    $ module load samtools/
      samtools/1.3.1  samtools/1.9

3)  Great, now I can choose samtools module with version 1.3.1

.. code:: bash

    $ module load samtools/1.3.1
       
4)  To check the loaded modules in your current shell

.. code:: bash

    $ module list

Loading package using "source activate <package-path>"
-------------------------------------------------------

This section explains how to load packages under conda.
In the below example, using Miniconda module, you are enabling the repeatmasker 4.1.5 verison as a conda environment on your path.

.. code:: bash
    
    $ module load gencore/1
    $ module load Miniconda3/4.7.10
    $ source activate /scratch/gencore/conda3/envs/repeatmasker4.1.5


Loading package from sources
--------------------------------------------------

This section explains how to load packages source path location. 
Compiled packages are available under below path.

.. code:: bash

   $ /scratch/gencore/software/

To load the specified package path, for eg:- maker version 2, you may issue below command in your command line.

.. code:: bash

    $ export PATH='/scratch/gencore/software/maker2':$PATH

To request a package 
--------------------

If you unable to find a package, you may proceed with sending an email to nyuad.cgsb.cb@nyu.edu by mentioning below pointers.

* Software version
* Github or Software download link
* If required databases to be downloaded, specify the exact link, names etc... 
