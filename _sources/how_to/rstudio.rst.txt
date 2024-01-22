R-Studio loading libraries 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We build R libraries for some packages in R v4.2.1, you can simply load this on your R-Studio/R on jubail. 

Launch Rstudio on HPC OOD GUI environment or you can load the R environment on your command line in jubail as follows.
Note:- If you install R on a different version, there will be some conflits. We recommend to stay in R v4.2.1

To load in jubail in CLI ( Command Line Interface )
.. code:: bash 

    module load gencore/1
    module load Miniconda3/4.7.10
    source activate /scratch/gencore/conda3/envs/RStudio

Seurat
--------

R toolkit for single cell genomics.

**b) 5.0.0**

.. code:: bash 

    .libPaths("/scratch/gencore/software/RStudio/Seurat/5.0.0")
    library("Seurat")

To verify the library path is set or not using 

.. code:: bash 

    .libPaths()

**b) 4.2.0**

.. code:: bash 

    .libPaths("/scratch/gencore/software/RStudio/Seurat/4.2.0")
    library("Seurat")

To verify the library path is set or not using 

.. code:: bash 

    .libPaths()

**c) 3.2.3**

.. code:: bash 

    .libPaths("/scratch/gencore/software/RStudio/Seurat/3.2.3")
    library("Seurat")

To verify the library path is set or not using 

.. code:: bash 

    .libPaths()

**d) 2.3.0**

.. code:: bash 

    .libPaths("/scratch/gencore/software/RStudio/Seurat/2.3.0")
    library("Seurat")

To verify the library path is set or not using

.. code:: bash 

    .libPaths()

Monocle
---------

R toolkit for single-cell RNA-Seq analysis.

**a) 2.26.0**

.. code:: bash 

    .libPaths("/scratch/gencore/software/RStudio/Monocle/2.26.0")
    library("monocle")

To verify the library path is set or not using 

.. code:: bash 

    .libPaths()

Dupradar
----------

R toolkit for duplication rates in RNA-Seq datasets.

**a) 1.28.0**

.. code:: bash 

    .libPaths("/scratch/gencore/software/RStudio/Dupradar/1.28.0")
    library("dupRadar")

To verify the library path is set or not using 

.. code:: bash 

    .libPaths()
