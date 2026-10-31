# Where Foundation0 can make progress in the life sciences

A survey made on 31 October 2026, when bi0 was set up. It gathers the life-science leads from Foundation0's scouting
of 18 and 19 October 2026 ([life sciences](https://github.com/Foundation-0/f0/blob/main/deep-fields/scouting/life-sciences.md),
[second pass](https://github.com/Foundation-0/f0/blob/main/deep-fields/scouting/2026-10-19.md)) and of 31 October
2026 ([tissue electrical properties](https://github.com/Foundation-0/f0/blob/main/deep-fields/scouting/tissue-electrical.md)).
Every number below comes from those reports, where each has its source. Re-check a number before you build on it.

Foundation0's habit is the same in every field: pick a question whose answer anyone can check, let AI agents do the
search and the careful code, and publish what re-runs the result. In the life sciences the openings so far are of
two kinds:

- **checks of the data, tables and archives that others build on**, at a scale nobody funds;
- **public measurements that are collected but not analysed** the way they could be.

Each entry gives the open question, why it fits, how a result is checked, and the status or a first step.

## Checks of what others rely on

### 1. Tissue dielectric tables (started: [tissue-dielectrics](https://github.com/Foundation-0/tissue-dielectrics))

**Question.** Do the public tables of tissue conductivity and permittivity agree with each other, their sources and
simple physics? The tables come from IT'IS, Sasaki et al. (2014) and NICT, and nearly all body simulations use them.

**Fit.** Deterministic recomputation from files that download in seconds; an agent can check every tissue.

**Checking.** Anyone re-runs the audit; a transcription is checked against the paper's table.

**Done so far.** A pilot found a transcription error in the IT'IS V5.0 alternative set (bladder given the aorta's
parameters), a bladder outlier in Gabriel's 1996 data, and an inconsistent water entry. Nothing has been reported yet.

### 2. Datasets that papers say were deposited but are not released (started: [overdue-data](https://github.com/Foundation-0/overdue-data))

**Question.** Which datasets cited in papers are still private more than 18 months later?

**Done so far.** A ProteomeXchange and GEO pilot; see the project.

### 3. Literature integrity at PubMed Central scale

**Question.** Which published nucleotide reagents (primers, siRNAs) do not match their stated targets? Which reported
statistics are arithmetically impossible?

**Fit.** The largest screen of wrong reagents covered about 11,700 papers, because every hit was checked by hand.
About 8 million article versions are in an open S3 bucket. Agents remove the hand-checking bottleneck.

**Checking.** Anyone can re-run BLAST or redo the arithmetic.

**First step.** Pull 5,000 open-access oncology papers, extract sequences and their claimed targets, BLAST them, and
recompute p-values from test statistics. Every hit is a question for the authors (PubPeer), and a person signs before
anything is posted.

### 4. Quality control of public sequence data with Logan

**Question.** Which runs in NCBI's sequence archive are not what their labels say: the wrong cell line, a
contaminant, or the wrong sex or species?

**Fit.** Logan has assembled all 38 million runs, and each run's assembly downloads on its own. The audits of
cell-line contamination and mislabelling predate it.

**Checking.** Marker k-mers anyone can recount from the public run (HPV18 for HeLa), then SNP fingerprints against
Cellosaurus or CCLE.

**First step.** The 18 October scout found HPV18 in a HeLa run and none in MCF-7 runs, with scripts in
[f0's logan-qc](https://github.com/Foundation-0/f0/tree/main/deep-fields/scouting/logan-qc). Next, screen a few
hundred runs labelled as one cell line.

## Public measurements not yet analysed

### 5. NHANES bioimpedance spectra (started: [nhanes-bioimpedance](https://github.com/Foundation-0/nhanes-bioimpedance))

**Question.** What do the full 50-frequency spectra of about 13,000 NHANES 1999–2004 participants show beyond
50 kHz phase angle, the measure the published papers use?

**Done so far.** All 13,276 spectra refitted; CDC's Cole parameters reproduced. Next: mortality linkage with a
held-out survey cycle, and DXA.

### 6. Unpublished clinical-trial results

**Question.** Do the results that sponsors posted on ClinicalTrials.gov, but never published in a journal, change
published meta-analyses?

**Fit.** 80,551 studies have posted results. About half of them were never published, and only about 11–12% of
systematic reviews in two specialties searched the registry.

**Checking.** The sponsor-posted tables are public; a re-pooled meta-analysis is recomputable.

**First step.** Pick one drug class, pull every registry result, find the published meta-analyses, and pool again.

### 7. Head-model conductivity against in vivo recordings

**Question.** Which conductivity defaults best predict the voltages measured inside the human brain during
transcranial stimulation?

**Fit.** Tools disagree on the skull-to-brain conductivity ratio by about a factor of three. Public intracranial
recordings (CRCNS tes-1: 14 patients, 1,846 electrodes, with MRI and segmentations) can score them.

**Checking.** Error against measured voltages, per subject.

**Status.** Partly done: Puonti et al. (2020) compared pipelines on these data and found that segmentation matters.
A conductivity-only scoreboard, with segmentation held fixed, is open.

## Biology at archive scale

### 8. Alternative genetic codes in metagenome-assembled genomes

**Question.** Which lineages read a stop codon as an amino acid, or reassign a codon, among the 1.16 million MAGs in
SPIRE and the unannotated eukaryote assemblies?

**Fit.** Screens so far covered about 250,000 isolate genomes. A fourth phylum reading UGA as tryptophan turned up in
gut MAGs only in December 2025.

**Checking.** Three independent signals: codon usage at conserved positions, loss of the matching release factor, and
a tRNA with the matching anticodon.

**First step.** Run Codetta on a few thousand SPIRE MAGs from one biome.

### 9. Structured RNAs waiting for Rfam

**Question.** Which published structured-RNA candidates from metagenomes hold up and belong in Rfam?

**Checking.** Statistically significant covariation of paired bases (R-scape).

**Note.** Slower than the other leads.

### 10. Dark protein families, by genomic context

**Question.** What do protein families of unknown function do, judged by operon context and co-occurrence?

**Fit.** Structure clustering is crowded; function from context is not. The LBNL Fitness Browser has phenotypes for
11,779 genes of unknown function.

**Line.** No toxin or virulence families. DOE's BERIL project is starting on this, so check overlap first.

## Smaller leads

- **The skin values behind the 6–300 GHz exposure limits** come from porcine skin measured in vitro. Recompute them
  from NICT's dermis data and compare with in vivo human skin models.
- **In vivo vs ex vivo tissue properties:** no per-tissue table of correction ratios exists.
- **Tumour vs normal tissue contrast:** test whether water content explains the published dielectric contrast.
- **Undescribed species in herbarium images** (GBIF has 78.5 million specimen records with images). Agents can only
  flag candidates; describing a species needs a taxonomist.

## Crowded, or set aside

- **Crowded:** new RNA viruses, obelisks, antimicrobial peptides and PET-degrading enzymes mined from Logan or the
  SRA; reclassifying ClinVar variants of uncertain significance; FAERS signals; deep-learning MR electrical properties
  tomography.
- **Set aside on 19 October 2026:** re-running single-factor NHANES associations and Mendelian randomization papers.
  Each means telling named authors their result does not reproduce, and needs specialists. The NHANES bioimpedance
  project is different: it checks CDC's own fitted variables and asks a new question of the raw spectra.
