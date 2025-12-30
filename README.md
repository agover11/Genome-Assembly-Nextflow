***Alteromonas macleodii Genome Assembly***

**Description:**
This project presents the genome assembly and analysis of Alteromonas macleodii using a hybrid approach of Nanopore long reads and Illumina short reads. The workflow includes assembly, polishing, feature annotation, and quality assessment.

**Methods:**
1. Data Input
Nanopore long reads and Illumina short reads provided as CSV files, organized into Nextflow channels (longread_ch and shortread_ch).
2. Quality Control
Short reads: FastQC v0.12.0
Long reads: Filtlong v0.3.0 (--min_length 500, --keep_percent 90)
3. Assembly & Polishing
Flye v2.9.6 for long-read assembly
Bowtie2 v2.5.4 and SAMtools v1.22.1 for short-read alignment
Pilon v1.24 for polishing (--threads ${task.cpus})
4. Annotation & Quality Assessment
Prokka v1.14.6 for genome feature annotation
BUSCO v6.0.0 for completeness assessment
QUAST v5.3.0 to evaluate assembly quality
5. Visualization
PyCirclize in Jupyter Notebook for genomic feature plots
6. Execution Environment
Nextflow pipelines run on BU Shared Computing Cluster (SCC) using Conda environments


