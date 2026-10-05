## Protist parasites and their impact on labile dissolved organic matter and bacterial processing

This repository contains QIIME 2 compatible files, metadata, R code, and all other input files needed for analysis and figure generation for the following manuscript:

**Protist parasite infection alters phytoplankton-derived metabolites and restructures natural bacterial communities**<br/>
*Sean R. Anderson, Philip F. Place, Natalie R. Cohen, Kelsey L. Poulson-Ellestad, and Elizabeth L. Harvey,  (2026)*<br/>

Preprint: *link will be added when available*

Final manuscript: *link will be added upon publication*

### 1. Study description 
Protist parasites are widespread in marine microbial communities, but their effects on the composition and subsequent microbial processing of phytoplankton-derived dissolved organic matter (DOM) remain poorly understood. In this study, we used the Syndiniales parasite *Amoebophrya* sp. and its dinoflagellate host *Scrippsiella acuminata* to examine how intracellular infection alters exometabolite composition and influences natural coastal bacterial communities. We first followed host-parasite dynamics over a 4-day infection experiment containing infected, host-only, and spore-only treatments. Extracellular metabolites were characterized using untargeted LC-MS metabolomics, allowing us to identify metabolite features enriched or depleted during infection. We then performed a separate bacterial-DOM incubation experiment using fresh filtrates from infected cultures, host-only cultures, and f/2 media controls. Coastal bacterial communities were exposed to these DOM sources for 48 h and sampled at 6, 24, and 48 h. Bacterial community composition was characterized using 16S rRNA gene metabarcoding, and metatranscriptomes collected after 48 h were used to examine community-wide taxonomic and functional responses. Together, these experiments link intracellular infection with labile DOM and bacterial functional responses, providing an important step towards resolving plankton parasitism and its role in carbon cycling.

### 2. Untargeted metabolomics
* Extracellular metabolites concentrated via solid-phase extraction 
* LC-MS performed on a Vanquish UHPLC coupled to an Orbitrap Exploris mass spectrometer
* Raw MS1/MS2 conversion with msConvert
* Feature detection and alignment with [MZmine](https://mzmine.github.io/)
* Data curation, normalization, and multivariate analyses in R
* Differential metabolite analysis with `DESeq2`
* Molecular formula prediction and compound-class annotation using [SIRIUS](https://v6.docs.sirius-ms.io/) and CANOPUS

### 3. 16S metabarcoding
* Natural bacteria targeted via incubation experiments using 515F-Y/926R primer pair (V4-V5 region)
* Primer removal with Cutadapt
* Sequence processing in [QIIME 2](https://qiime2.org/)
* Amplicon sequence variants (ASVs) inferred with paired-end DADA2
* Taxonomic assignment with a Naïve Bayes classifier trained against SILVA v138.2
* Removal of chloroplast, mitochondrial, phylum-unassigned, and singleton ASVs
* Community analyses in R using packages including `phyloseq`, `vegan`, and `tidyverse`

### 4. Metatranscriptomics
* Quality trimming with Trimmomatic, rRNA removal with RiboDetector, and coassembly across samples with MEGAHIT
* Read mapping and abundance estimates using Salmon
* Taxonomic assignment of assembled contigs with Kaiju v1.10.1
* Open reading frame prediction using Prodigal
* Protein clustering in MMseqs2
* Functional annotation with eggNOG-mapper
* Differential expression analysis with `DESeq2` in R

### 5. Links to associated data
* Raw sequence data for this project are available in NCBI SRA under BioProject [PRJNA1492030](https://www.ncbi.nlm.nih.gov/bioproject/1492030)
* Project metadata and associated datasets are found on [BCO-DMO](https://www.bco-dmo.org/project/953588)
* Raw LC-MS data is on [MetaboLights](https://www.ebi.ac.uk/metabolights/MTBLS11219)









