SSH key login to Jubail HPC
^^^^^^^^^^^^^^^^^^^^^^^^^^^

This procedure how to login to Jubail HPC using ssh key based authentication. This means the password prompt never prompt once you hit the ssh login command.
This method is a secure way to connect to HPC by setting up private and public keys. For more details about SSH key authentication `link <https://www.ssh.com/academy/ssh/public-key-authentication>`__ .

This is tested on Mac/Linux based laptops.   

**Steps**

1) Launch the terminal app

2) Issue the command "ssh-keygen" on the command line. Then press enter for all the questions as per below.

.. code:: bash

    $ ssh-keygen
    
Below is the output of ssh-keygen of issuing by user named john.

.. code-block:: none

    $ ssh-keygen
      Generating public/private rsa key pair.
      Enter file in which to save the key (/Users/john/.ssh/id_rsa):
      Enter passphrase (empty for no passphrase):
      Enter same passphrase again:
      Your identification has been saved in /Users/john/.ssh/id_rsa
      Your public key has been saved in /Users/john/.ssh/id_rsa.pub
      The key fingerprint is:
      SHA256:q2nJMP4ozzd5jbX23Y2bjfuYQNdSjfFlVij5oOzQp8I john@ADUAED15308LPMX
      The key's randomart image is:
      +---[RSA 3072]----+
      |             ...*|
      |            + .*o|
      |         o . +. +|
      |        . + . .o |
      |       .So o. o .|
      |    o   E.+. . . |
      |   . + o.= ..    |
      |  ....Boo +  o O.|
      |   o+++o . .. X+=|
      +----[SHA256]-----+
 

3) Copy the ssh public key towards the Jubail HPC server using "ssh-copy-id" command, password needs to be enter once it is prompted.

.. code:: bash

    $ ssh-copy-id net-id@jubail.abudhabi.nyu.edu

Below is the output of copying the public key to jubail hpc server as user named john. 

.. code:: none

    $ ssh-copy-id john@jubail.abudhabi.nyu.edu
      /usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/Users/john/.ssh/id_rsa.pub"
      /usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
      /usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
      john@jubail.abudhabi.nyu.edu's password:

      Number of key(s) added:        1

      Now try logging into the machine, with:   "ssh 'john@jubail.abudhabi.nyu.edu'"
      and check to make sure that only the key(s) you wanted were added.
      

4) Login to jubail HPC, now you are able to login to Jubail using key based authentication without prompting any password.  

.. code:: bash

    $ ssh <net-id>@jubail.abudhabi.nyu.edu 

Below is the output of login command as user named john.

.. code:: bash

    $ ssh john@jubail.abudhabi.nyu.edu
      Access allowed by pam_access
      - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
      Welcome to Jubail!
   
      For documentation & examples: https://crc-docs.abudhabi.nyu.edu
      For support: nyuad.it.help@nyu.edu
      - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

5) This step is optional, if you wish to launch this ssh connection using a friendly name let's say just "jubail" you can refer to below steps.

* Create a file named config under .ssh directory on your home folder

.. code:: bash

    $ touch ~/.ssh/config

* Fill out the contents of config file as below. Replace the net-id with yours.
   You can use any friendly name, only thing to specify in the "Host" section. 

.. code:: bash

    Host jubail
        Hostname jubail.abudhabi.nyu.edu 
        User <net-id> 

* Launch a new terminal tab or windows and issue below command.    

.. code:: bash

    $ ssh jubail

Below is the output of login command with friendly name "jubail"

.. code:: bash

    $ ssh jubail
      Access allowed by pam_access
      - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
      Welcome to Jubail!

      For documentation & examples: https://crc-docs.abudhabi.nyu.edu
      For support: nyuad.it.help@nyu.edu
      - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

.. note:: If you want to setup ssh key based authentication on Windows laptop, kindly refer to this `link <https://www.mythic-beasts.com/support/topics/ssh-keys>`__

