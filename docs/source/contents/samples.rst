Example datasets
================

The input data for these pipelines typically consist of either 2 FASTQ files for paired-end reads or a BAM file containing already aligned reads. 

Whole genome sequencing sample
------------------------------

The whole genome sequencing sample is the NA12878 dataset, this dataset is typically used in similar benchmarks and papers. This dataset consists of 1.5 billion paired-end reads of 100 basepairs in length. This translates into a 50x coverage. Execute the following commands to download and preprocess the data:

.. code-block:: bash
	:linenos:

	wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/ERR194/ERR194147/ERR194147_1.fastq.gz
	wget ftp://ftp.sra.ebi.ac.uk/vol1/fastq/ERR194/ERR194147/ERR194147_2.fastq.gz
	export HADOOP_HEAPSIZE=32768
	hadoop jar HalvadeUploaderWithLibs.jar -1 ERR194147_1.fastq.gz -2 ERR194147_2.fastq.gz \
	-O /user/ddecap/halvade/wgsin/ -t 16


RNA-seq sample
--------------

The RNA-seq example dataset is found in the *encode project* under the *SK-MEL-5* experiment. The *ENCSR201WVA* dataset provides both paired FASTQ files and aligned BAM files. In this example we will download a single replicate of the *ENCBS524EJL* bio sample available in paired FASTQ files. To download and preprocess the FASTQ files run these commands in the terminal:

.. code-block:: bash
	:linenos:

	wget https://www.encodeproject.org/files/ENCFF005NLJ/@@download/ENCFF005NLJ.fastq.gz
	wget https://www.encodeproject.org/files/ENCFF635CQM/@@download/ENCFF635CQM.fastq.gz
	export HADOOP_HEAPSIZE=32768
	hadoop jar HalvadeUploaderWithLibs.jar -1 ENCFF005NLJ.fastq.gz -2 ENCFF635CQM.fastq.gz \
	-O /user/ddecap/halvade/rnain/ -t 16
