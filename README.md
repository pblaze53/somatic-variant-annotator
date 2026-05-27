# Somatic Variant Annotator

A Python tool for annotating and classifying somatic cancer variants from VCF files, with automated ACMG/AMP evidence-level classification and interactive HTML report generation.

## Features

- VCF parsing with `cyvcf2`
- ClinVar querying via NCBI E-utilities API
- ACMG/AMP somatic classification (1A/1B/2/3A evidence levels)
- Therapy recommendations based on variant-drug evidence
- Interactive HTML report with color-coded classifications

## Example output

[View example HTML report](results/variant_report.html)

The report includes:
- Summary cards: total variants, pathogenic count, actionable count
- Color-coded evidence levels (1A = FDA-approved, red → 3A = case reports, orange)
- Therapy recommendations per variant
- Allele frequency and sequencing depth

## Supported variant classifications

| Level | Definition |
|-------|------------|
| 1A | FDA-approved biomarker |
| 1B | Professional guideline biomarker |
| 2 | Clinical evidence (well-powered studies) |
| 3A | Case reports / small series |
| VUS | Variant of uncertain significance |

## Usage

```bash
git clone https://github.com/pblaze53/somatic-variant-annotator.git
cd somatic-variant-annotator
conda activate glioma-meth
jupyter notebook notebooks/01_variant_annotator.ipynb
```

## Input format

Standard VCF with AF and DP INFO fields:
#CHROM  POS     ID  REF ALT QUAL    FILTER  INFO
chr7    55259515    .   T   G   .   PASS    DP=150;AF=0.35

## Dependencies

- Python 3.11
- cyvcf2, pandas, requests, jinja2

## Author

**Balazs Murnyak, PhD** — Molecular Biologist and Genomics Scientist  
University of Utah  
[LinkedIn](https://www.linkedin.com/in/balazs-murnyak-56a45a100/) | [Google Scholar](https://scholar.google.com/citations?user=dFfVIEAAAAJ)