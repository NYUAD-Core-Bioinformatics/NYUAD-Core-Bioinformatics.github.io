Dearchival of Data 
^^^^^^^^^^^^^^^^^^^

This procedure explains how to request for dearchive data from gencore archive node on jubail.  

* Send an email to nyuad.cgsb.cb@nyu.edu 
* Mention the jira ticket number.
* Specify the type of data you would require for eg:- raw data, qc fastq, raw counts etc..
* Specify the sample names, if possible. 

Based on the request, we will start dearchive the data from the archive node as follows:- 

Once login to jubail login node, and will issue the de-archive as follows.

To check the size of the de-archive directory.

.. code:: bash

    $dmfdu -d </archive/gencore/XXXX/XXXX/XXX>

To issue the de-archive command.

.. code:: bash 

    $ dmfget -d </archive/gencore/XXXX/XXXX/XXX>

To check the real time status of the dearchive process.

.. code:: bash 

    $ watch -n2 dmfmonitor -d </archive/gencore/XXXX/XXXX/XXX>


.. Tip:: How to understand the archive status:

     * released exists archived ->> unreadable state
     * exists archived ->> readable state

To check the state of dearchive directory.
If you need to check the status of file, remove the "-d" flag

.. code:: bash 

    $ dmfls -d </archive/gencore/XXXX/XXXX/XXX> | grep -c released 

Note:- if the above value is "0", then the de-archive is completed. 


De-archive CGSB shared path
----------------------------

This shared space is only visible to the end user and cgsb core team. 
Below is the path of cgsb dearchive shared space.

.. code:: bash

    $ /scratch/share/cgsb

Create a net-id named directory. ( for eg:- if abc123 named user is the requester )

.. code:: bash

    $ mkdir /scratch/share/cgsb/abc123

Transfer the data to the shared space

.. code:: bash

    $ rsync -avP </archive/gencore/XXXX/XXXX/XXX> /scratch/share/cgsb/abc123

.. warning:: 
     * Once the data copied to the cgsb shared location, the ownership will change from gencore to respective users.
     * The copied files will consume space from the requested user quota.
     * Once the files copied in this location will be available for 2 weeks. Hence kindly remove the directory once you copied the files.
     * Once the storage quota reaches beyond your permitted value, you are unable to login to jubail node. In that case reach out to jubail support team.
     
    
