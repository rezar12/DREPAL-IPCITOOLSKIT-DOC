Installation
=============

.. _Download:

Download and Installation of Outbuildings
------------------------------------------
System requirements
~~~~~~~~~~~~~~~~~~~~

Operating system: Ubuntu 20.04.5 LTS and update version (especially all Linux versions based on the Debian distribution).
System architecture: Linux- 64-bit x86.
Minimum ~ 2.5 GB disk space to download and install.The memory resources required for analyses using DREPAL-IPCINGSTOOLSKIT may vary depending on the size and complexity of the sequencing data being processed. For small sequencing datasets (size in MB), a minimum of 16-32 GB RAM is recommended. However, as datasets increase in size, or when performing memory-intensive operations, it may be necessary to allocate more memory. The amount of memory required for specific analyses in DREPAL-IPCINGSTOOLSKIT is often influenced by factors such as the number of samples, read depth and genome size.For our analyses, we used a server equipped with the following resources. These included 2TB of disk space, which enabled us to store and manage large volumes of sequencing data efficiently. In terms of memory, we allocated 64GB of RAM, which enabled us to process memory-intensive operations and meet the various computational requirements of the analysis modules. The server was equipped with an Intel Xeon(R) 4208 processor, 16 cores at 2.16 GHz each.  

Setup process
~~~~~~~~~~~~~~

.. note::

   if git is not installed then follow the procedure in the following : `documentation
   <https://github.com/git-guides/install-git>`_.

or install git on Ubuntu

.. code-block:: console

   sudo apt-get install git-all

To use DREPAL-IPCINGSTOOLKIT, first install it using git for clone repository:

.. code-block:: console

   git clone git@github.com:stanlasso/DREPAL-IPCINGSTOOLKIT.git
   

.. note::

   if you have a version of ``"Anaconda"`` or ``"Miniconda"`` install ignore the step of installation of Miniconda passed directly to that on the creation of the virtual environment.
   

**Install miniconda**

- Install as root
.. code-block:: console

   sudo -su
   
- Download Miniconda
.. code-block:: console

   wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh


- Execute the Miniconda script to install it
.. code-block:: console

   bash Miniconda3-latest-Linux-x86_64.sh
   
once the execution is finished, **close the terminal** then reopen it, *switch to root mode* once more and *activate the basic environment*.

.. code-block:: console

   sudo su

- Entered in the repository clone

.. code-block:: console

   cd DREPAL-IPCINGSTOOLKIT


- Creates an environment for bioinformatics analysis 

.. code-block:: console

   conda env create -f environment.yml
   

- Deactivate conda env

.. code-block:: console

   conda deactivate
   
**Creates an environment for hosting front-end solutions**


* Install virtualenv 
  
.. code-block:: console

   apt install python3-virtualenv
   
.. warning::
   use the command above if your version of ``"python3"`` is higher than **3.8** if it is lower than **3.8** use the command below. 
   to check the version of Python use the command : 
   ``"python3 --version"``.
   

* If your Python < 3.8 : 
  
.. code-block:: console

   apt install virtualenv
  

* Create env with virtualenv : 

.. code-block:: console

   virtualenv myenv

* Activate myenv : 
 
.. code-block:: console

   source myenv/bin/activate

* Install all dependencies : 

.. code-block:: console

   pip install -r requirements.txt
   
   
.. note::
   if you get dependency errors such as ``"ERROR: could not find a version that satisfies the requirement packagename==x.x.x"``, use nano or a text editor to        delete the line containing the package name in *requirements.txt*, then run the above command again. Once the installation of the packages is finished, check     that the missing packages (removed from the requirements.txt) have been installed, as they depend on other packages with ``"pip freeze"``; if they have not been   installed, use the command ``"pip install packagename"``.


**Creates all missing directories**

.. code-block:: console

   bash makedir.sh

*use the tree command to check that you have a file structure similar to the following:*

.. code-block:: console

    APP/data/
    ├── Annoted
    │   ├── AnnotatedFILEbyFILE
    │   │   └── singlefilerepport
    │   └── report
    ├── Bam
    │   └── Mapped
    │       ├── BamFreebayes
    │       └── BamGATK
    ├── chromosome
    ├── combined
    │   ├── 3d7_hb3.combined.final.vcf.gz
    │   └── 3d7_hb3.combined.final.vcf.gz.tbi
    ├── Datafastq
    │   ├── Fastqc
    │   ├── KDSD
    │   ├── ResQC
    │   └── unmapped
    ├── freebayesfile
    │   ├── Filterring
    │   │   └── mergefile
    │   ├── mergevcffile
    │   ├── metrics
    │   ├── txtfile
    │   └── vcffile
    ├── gatkfile
    │   ├── Filterring
    │   │   ├── generation.sh
    │   │   ├── MATRICE
    │   │   ├── MatriceSNPS
    │   │   ├── matrix2.sh
    │   │   └── mergefile
    │   ├── mergevcfile
    │   ├── metrics
    │   ├── recal
    │   ├── textfile
    │   └── vcffile
    ├── intercep
    ├── Reference
    ├── Sam
    ├── variants.bcftools
    │   ├── Filterring
    │   │   ├── filteredType
    │   │   ├── generation.sh
    │   │   ├── MATRICE
    │   │   ├── MatriceSNPS
    │   │   ├── matrix2.sh
    │   │   └── mergefile
    │   ├── mergevcffile
    │   └── metrics
    └── variants.varscan
        └── Filterring
            ├── generation.sh
            └── matrix2Var.sh



**Activated the conda environment**

.. code-block:: console

   conda activate NewENV



Starting the streamlit server
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Streamlit is a Python framework that simplifies the deployment of web applications. It is used to host the front end of DREPAL-IPCINGSTOOLSKIT.

Use the following command to start the server :

.. code-block:: console

   streamlit run APP/app.py


.. _Browser:

In your web browser
-------------------

Open your browser and paste the link below in the search bar.

.. code-block:: console

   http://localhost:8501
   
.. note::
**If you want to use the app with several people on your local network, you can continue with the following configuration**

* example of a schema for deploying DREPAL-IPCINGSTOOLSKIT on a local network :

.. image:: Images/Group_10.png

