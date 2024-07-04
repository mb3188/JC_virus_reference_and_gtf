# JC_virus_reference_and_gtf

Single-cell Transcripts Mapping
Masked genome reference GRCh38 and the corresponding gene transfer format (GTF) annotation file for the gene reference were downloaded from Ensembl. We then combined the downloaded GRCh38 reference with JC virus sequences and transposable elements (TE) sequences to create custom reference and annotation files for alignment.

Briefly, JC virus sequences were divided into three separate regions corresponding to Agno (101-316 bp), VP2 and VP3 overlapping genes (350-1384 bp), and VP1 gene (1385-2357 bp). These were added to the FASTQ and GTF files. For primary cells, we prepared a reference file that included small (273 bp) and large T antigen (1821 bp) sequences. Small and large T antigen sequences were not present in our reference when aligning JC transformed cell line reads, as those sequences have a high similarity to SV40 virus antigens, which were used for transformation.

To include TEs in our analysis, we downloaded 427 consensus TE FASTQ sequences from Repbase, representing LINE, SINE, and LTR TE families that are sufficiently distinct in terms of their repeats to allow for unique read mapping. These TE sequences, as well as the annotation GTF file that we created, were merged with the above files for the final reference and annotation files.

The final custom reference was then built, and the reads were mapped to human and viral genes, and TE subfamilies using the Chromium 10x workflow and the Chromium 10x Cell Ranger Single-Cell Software Suite. Only unique alignments were considered and counted for the differential expression of TE analysis. The number of differences is defined as the number of differences in TE subfamilies.

To estimate RNA velocities for our single-cell data, we used velocyto run10x from the Velocyto package on the Chromium 10x Cell Ranger output files as suggested by the Velocyto workflow.
