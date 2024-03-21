Transfer files using  CGSB SFTP service
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This procedure explains how to transfer files between NYUAD to external collaberators.

There are two ways you can transfer files to CGSB file transfer server

To request an account, please fill out this `form <https://docs.google.com/forms/d/e/1FAIpQLSeQ9A2yF2s0iFzVpCYr_aYneD-l4x_Y5iEMiGPxNIhaO9eOAA/viewform>`__

    

**1) Using Command Line** ( Internal )
   

Launch terminal app from your Linux/Mac laptop.


.. code:: bash

    $ rsync -av --progress -e 'ssh -p 4410'  <net-id>@cgsb-sftp.abudhabi.nyu.edu:<destination-path> <local-path>

Below is an example, here i would like to share a directory named **datadir** from jubail to SFTP site on path **/data/<username>/upload** 

.. code:: bash

    $ rsync -av --progress -e 'ssh -p 4410' <username>@cgsb-sftp.abudhabi.nyu.edu:/data/<username>/upload/ <localpath-on-your-laptop>



**2) Using Filezilla** 
   


If the data resides in Jubail, then you need to login to `Jubail Web Interface <https://ood.hpc.abudhabi.nyu.edu>`__  . Then launch **Filezilla** GUI application from the **Interactive Apps** menu.     
If you have any doubts navigating to Jubail Web Interface, kindly refer to `NYUAD CRC page <https://crc-docs.abudhabi.nyu.edu/hpc/ood/index.html>`__ 

To retrieve the data locally then you need to download `Filezilla <https://filezilla-project.org/download.php?type=client>`__ software on your laptop. 

Below information will share with you once you request for an sftp account.

.. code-block:: none

    Host: sftp://cgsb-sftp.abudhabi.nyu.edu
    User: <username>
    Pass: <Specify the password shared with you>
    Port: 4410

 

.. figure::  /how_to/img/filezilla_copy.png
   :align: center

   *Figure: Transfer window between source and destination*

If you are unable to transfer data to the SFTP site, please write us nyuad.cgsb.cb@nyu.edu 
