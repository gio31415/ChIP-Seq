# ChIP-Seq
The ChIP-Seq software provides methods for the analysis of ChIP-seq data and other types of mass genome annotation data. The most common analysis tasks include positional correlation analysis, peak detection, and genome partitioning into signal-rich and signal-depleted regions.
Giovanna Ambrosini EPFL SV/ISREC GR-BUCHER

DESCRIPTION OF THE TOOLS
----------------------------------------------------------------------------
We propose a set of useful tools performing common ChIP-Seq data analysis tasks,
including positional correlation analysis, peak detection, and genome partitioning
into signal-rich and signal-poor regions.

These tools exist as stand-alone programs and perform the following tasks:

        1. Positional correlation (chipcor),
        2. Tag centering (chipcenter),
        3. Signal peaks detection (chippeak),
        4. Identification of signal-enriched regions (chippart),
        5. Feature extraction tool.

The programs use their own compact format for ChIP-Seq data representation called SGA (Simplified Genome Annotation).
SGA is a single-line-oriented and tab-delimited format with the following five obligatory fields:

        1. Sequence name (Char String),
        2. Feature (Char String),
        3. Sequence Position (Integer),
        4. Strand (+/- or 0),
        5. Tag Counts (Integer).

Any number of additional fields may be added containing application-specific information.
SGA files represent genome-wide tag count distributions for one ore more features.
The 'feature' field (identified by field 2) is used to identify the molecular species targeted by antibody
of a ChIP-seq experiment.
Sequences are identified by NCBI/RefSeq chromosome ids, which are assembly specific in order to prevent mixing of different assemblies.
Tag counts represent the number of tag reads that have been mapped to a specific position in the genome.
Input features may be ChIP-Seq tag positions, peaks found by ChIP-peak, or any type of genome annotation that can be mapped to a single base on a chromosome.

An example of SGA-formatted file is shown here below:

        NC_000001.9     H3K4me3 4794    +       1
        NC_000001.9     H3K4me3 6090    +       1
        NC_000001.9     H3K4me3 6099    +       1
        NC_000001.9     H3K4me3 6655    +       1
        NC_000001.9     H3K4me3 18453   -       1
        ...

Chip-Seq programs require SGA intput files to be sorted by sequence name, position, and strand.


WEB SITE
----------------------------------------------------------------------------
ChIP-Seq has a web interface which is freely available at:

   http://ccg.vital-it.ch/chipseq/


PROGRAM INSTALLATION
============================================================================

Untar the file containing the source code (e.g. chip-seq.3.1-0.tar.gz).

For code compilation a suitable makefile is provided.

To create the executable files, type:

make

To delete the excutable files and all the object files from the directory, type:

make clean

To install the man pages you should have root permissions and type:

make man
