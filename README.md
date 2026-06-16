# Drought-Responsive miRNA Identification in Wheat — Computational Workflow & Supplementary Data

This repository documents the complete in silico workflow, tool versions, parameter
settings, and supplementary data files associated with the manuscript:
'In Silico Identification and Functional Annotation of Drought-Responsive miRNAs in Wheat'
(submitted to Scientific Reports).

## Workflow Summary

1. EST and Reference miRNA Retrieval: NCBI dbEST (keywords: wheat, drought, stress),
   48,632 ESTs retrieved; filtered with CD-HIT-EST v4.8.1 (90% identity cutoff).
   Reference miRNAs from miRBase release 22.1.

2. Homology-Based Screening: BLASTn v2.12.0; word size 7; E-value <= 0.01;
   max 3 mismatches; length 18-24 nt. Validated with TamiRPred (SVM-based).

3. Protein-Coding Filter: BLASTx v2.12.0 against NCBI nr database; E-value <= 1e-5.

4. Secondary Structure Prediction: RNAfold (ViennaRNA v2.5.1), default parameters.
   Criteria: MFE < -25 kcal/mol; MFEI >= 0.85; GC content 30-70%; max 4 mismatches.

5. Target Gene Prediction: psRNATarget (2023 release) and MirTarget (Achakzai et al., 2018).
   Consensus targets: complementarity score <= 2, duplex free energy <= -20 kcal/mol.

6. Functional Annotation: AgriGO v2.0 (GO, FDR < 0.05); KEGG Mapper (corrected P < 0.05).

7. Network Analysis: Cytoscape v3.8.0 (miRNA-target network); STRING v11.5 (PPI, confidence >= 0.4).

## Supplementary Files (deposited on Figshare, DOI: see manuscript)

- Additional_file_1.csv - List of 110 identified miRNAs with sequence, length,
  classification (conserved/novel), miRNA family, pre-miRNA coordinate, MFE, MFEI, AU content.
- Additional_file_2.csv - Structural validation data for each miRNA.
- Additional_file_3.csv - Consensus miRNA-target gene predictions (505 pairs).
- Additional_file_4.pdf - GO Biological Process enrichment analysis (top 10 terms).
- Additional_file_5.pdf - KEGG pathway enrichment analysis (top 10 pathways).
- Additional_file_6.pdf - Hub miRNA-target interaction network (top 6 hub miRNAs).
- Additional_file_7.pdf - Schematic overview of the complete computational workflow.
