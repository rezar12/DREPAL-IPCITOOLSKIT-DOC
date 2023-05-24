
Left Panel
==========

Use of disk ressources
-----------------------
* **Donut diagram of free and used space**

This diagram gives you an overview of the available disk space on the server for your analyses, consult it after each analysis to establish efficient resource management.

.. image:: Images/usagefree.jpg
  :width: 280
  :alt: Ressource Disk

Operations menu
----------------

In the menu you will find all possible operations (see table of available operations), from importing files to emptying the analysis directory.

.. image:: Images/operation.png
  :width: 280
  :alt: Operations menu

.. Note::
  DREPAL-IPCINGSTOOLSKIT is made up of autumn pipelines but to be executed sequentially, i.e. certain operations are conditioned by the result of those which precede them.

.. list-table:: Title
   :widths: 25  75
   :header-rows: 1

   * - Operations,
     - Description,
   * - Row 1, column 1
     -
   * - Row 2, column 1
     - Row 2, column 2


.. list-table:: Operations and Descriptions
   :widths: 25 75
   :header-rows: 1
   * - Operations
     - Sequence Import
     - Quality Management
     - References Indexing
     - Substraction of the Host
     - Pathogen Extraction
     - K DDS (Double Digital Subtraction)
     - Variants Calling 
     - Mutation Matrix (SNPs)
     - Variants Annotations
     - Directory Management
   * - Description
     - In this section import raw sequences and references (host and pathogen.
     - In this section, view the quality of the reads and cut them if necessary.
     - Indexing host and pathogen references.
     - Remove the host's share of the reads.
     - Kept the corresponding share of pathogens in each reads.
     - It is optional to visualise the host, pathogen and other parts contained in each read.
     - This is the part of the analysis that consists of finding the mutations by using a number of technologies.
     - The Mutation Matrix (for SNPs) allows us to have an overview of the SNP type mutations for all reads in a spreadsheet facilitating a number of downstream          statistical analyses.
     - Used to assign functional information to mutations via Snpeff and SnpSift.
     - This section allows for the dumping of what appears to be the scan directory to save disk resources once the scan is complete or in the event of an error.
     
