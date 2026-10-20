# E. coli REL606 Whole Genome Variant Calling Analysis
End-to-end E. coli REL606 whole-genome variant calling pipeline integrating Galaxy Europe cloud compute (fastp, BWA-MEM, FreeBayes) with Google Colab for programmatic VCF parsing, quality filtering, and interactive Plotly visualization.

## 📌 Project Overview
This project demonstrates an end-to-end Whole Genome Sequencing (WGS) variant discovery workflow. Heavy sequence alignment and bayesian variant calling are executed on Galaxy Europe's cloud infrastructure, while downstream quality control, parsing, and data visualization are handled programmatically in Google Colab using Python.

## 🛠️ Pipeline Architecture
1. **Data Ingestion**: Paired-end Illumina WGS short reads (`SRR2584866`) fetched directly via NCBI SRA using `fasterq-dump`.
2. **Read QC & Trimming**: Quality filtering and adapter removal using `fastp`.
3. **Genome Alignment**: Sequence mapping against the *E. coli* REL606 reference genome (`CP000819.1`) using `BWA-MEM`.
4. **Variant Calling**: Bayesian germline SNP and Indel discovery using `FreeBayes`.
5. **Programmatic Downstream Analysis**: Automated VCF download via `BioBlend` API into Google Colab.
6. **Filtering & Reporting**: Quality score thresholding (QUAL >= 20) via `cyvcf2`, structured data manipulation in `pandas`, and interactive plot generation with `Plotly`.

## 📊 Key Output Metrics
- **Organism**: *Escherichia coli* B strain REL606
- **Reference Accession**: `CP000819.1`
- **SRA Dataset**: `SRR2584866`
- **Total High-Quality Variants Processed**: 818
  - **SNPs**: 701
  - **INDELs**: 117
- **Filtering Threshold**: $\text{QUAL} \ge 20$
- **Output Artifacts**: Filtered variant table (`ecoli_filtered_variants.csv`), interactive Quality (QUAL) and Read Depth (DP) distribution plots.

## 📂 Project Structure
```text
├── notebooks/
│   └── E. coli REL606 Whole-Genome Variant Calling & Analysis.ipynb # Executed Google Colab Notebook
├── data/
│   └── ecoli_filtered_variants.csv     # Filtered high-confidence variant table
└── README.md                           # Project documentation

🔗 Links & Resources
 * Public Galaxy Europe History: https://usegalaxy.eu/u/nihadaq/h/e-coli-rel606-whole-genome-variant-calling-analysis
 * GitHub Repository: https://github.com/nihadaq/E.-coli-REL606-Whole-Genome-Variant-Calling-Analysis
 * Connect on LinkedIn: https://www.linkedin.com/in/nihadaq?utm_source=share_via&utm_content=profile&utm_medium=member_android

💻 Tech Stack
Python | BioBlend API | cyvcf2 | pandas | Plotly | Galaxy Europe | BWA-MEM | FreeBayes | fastp
