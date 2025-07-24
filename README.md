# 🧬 Mutation2Neoantigen: A Minimal TCGA Neoepitope Pipeline

This project shows a simplified approach to identify potential neoantigens from real cancer mutation data. It's designed for students and beginners exploring cancer immunotherapy, bioinformatics, or vaccine research.

By working with TCGA mutation data and Ensembl protein sequences, this pipeline generates short 9-amino-acid mutant peptides (neoepitopes) that could stimulate an immune response — a key idea behind personalized cancer vaccines.

---

## 📁 Project Contents

| File                                   | Description |
|----------------------------------------|-------------|
| `SCRIPT.ipynb`                         | Main pipeline notebook |
| `requirements.txt`                     | Python packages used |
| `*.maf` files                          | Real TCGA mutation files |
| `neoepitopes.csv`                      | Final output table of predicted neoantigens |

---

## 🚀 What the Pipeline Does

- 📥 Loads TCGA MAF files (mutation data)
- 🧬 Filters for missense mutations (protein-changing)
- 🔗 Fetches canonical protein sequences from Ensembl REST API
- 🧩 Builds mutant 9-mer peptides centered on each mutation
- 💾 Exports results to `neoepitopes.csv`

---

## 📋 Sample Output
- Gene    Mutation  Neoepitope
- CACNA1S p.L363F   LDEDFRGYM
- LMOD1   p.T55M    QRNQMEKQS
- RPL32   p.R44S    GIDNSVRRR
- CC2D2A  p.T1114M  TVCHMTTAE
- LNX1    p.E176K   LMTDKPGLD

Each row represents a potential cancer-specific peptide that might be recognized by the immune system.

---

## ▶️ How to Run

1. Clone this repo or download the files.
2. Install required packages:
   ```bash
   pip install -r requirements.txt
3. Open SCRIPT.ipynb in Jupyter Notebook.
4. Run all cells to generate the neoepitopes.csv file.

---

## ⚠️ Notes
- Only 4 MAF files were downloaded (even though 5 case IDs were queried) because not all TCGA cases have open-access mutation files.
- Some MAF files may include mutations from multiple tumor samples, which is why the final output may list more samples than MAFs.
---

## 🔭 Future Plans
- Integrate HLA typing from metadata
- Add MHC binding prediction tools like NetMHCpan or MHCflurry
- Rank peptides by expression or binding affinity
- Add visualization or web UI
---

## 📚 References
- TCGA via GDC Portal
- Ensembl REST API
- NIH: Cancer Vaccine Fact Sheet

Created with 💻 by @TaranKhan
