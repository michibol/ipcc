# From Scientific Bedrock to Policy Relevance  
## Data Sources and Methods

This repository provides detailed methodological documentation supporting the paper  
**“From Scientific Bedrock to Policy Relevance: The Evolving Roles of the IPCC Working Groups.”**

Due to the use of proprietary data sources, this repository **substitutes and extends the Methods section of the paper**, ensuring transparency and replicability to the extent permitted by data access restrictions.

The repository also includes code to reproduce all figures using **aggregated and derived data**.

---

## Overview of Data Sources

The analysis combines multiple data sources to track references and citations to IPCC Assessment and Special Reports across science, policy, international negotiations, and media.

| Domain | Data Source | Access | Code |
|------|------------|--------|--------|
| Scientific publications | [DimensionsAI](https://app.dimensions.ai), [Web of Science]( https://clarivate.com/academia-government/scientific-and-academic-research/research-discovery-and-referencing/web-of-science/) | Proprietary | [code](https://colab.research.google.com/drive/1nxOLu-D-5OQiyMwsBYq39drFkv1pJamZ?usp=sharing) |
| Parliamentary speeches | [European Parliament](https://www.europarl.europa.eu/plenary/en/debates-video.html), [U.S. Congress](https://www.congress.gov) | Public | [code](https://colab.research.google.com/drive/1GMesfiCT3SOLM_mf4LutbvqN2vU-kWLR?usp=sharing) |
| Policy documents | [Overton](https://www.overton.io/) | Proprietary | [code](https://colab.research.google.com/drive/18yvHlaartOyHBbhkR1NJFxgGa9T4JeYt?usp=sharing) |
| UNFCCC documents | [UNFCCC website](https://unfccc.int/documents) | Public |. |
| Media coverage | [Factiva](https://global.factiva.com/) | Proprietary |. |

---

## Figure 1 – Scientific Publications

### IPCC Citations in Scientific Papers

Data on citations to IPCC Assessment and Special Reports in scientific papers are retrieved using **DimensionsAI – Altmetrics**, through DOI-based queries.

- One observation corresponds to a scientific paper citing at least one IPCC report.
- Coverage includes both **Assessment Reports (AR5, AR6)** and **Special Reports** published between 2013 and 2022.

#### IPCC Reports Included

**Assessment Reports**

- AR5  
  - Working Group I (2013): `10.1017/cbo9781107415324`  
  - Working Group II (2014): `10.1017/cbo9781107415386`  
  - Working Group III (2014): `10.1017/cbo9781107415416`  

- AR6  
  - Working Group I (2021): `10.1017/9781009157896`  
  - Working Group II (2022): `10.1017/9781009325844`  
  - Working Group III (2022): `10.1017/9781009157926`  

**Special Reports**

- SR1.5 (2018): `10.1017/9781009157940`  
- SR Ocean (2019): `10.1017/9781009157964`  
- SR Land (2022): `10.1017/9781009157988`  

### Normalization of Scientific Output

To account for trends in overall scientific production, we retrieve the yearly total number of climate-related scientific papers through **Web of Science**, using the keywords:

- `Climate Change AND Global Warming`

Following Vasileiadou et al. (2011), we compute a **normalized share of IPCC-citing papers**, defined as the ratio between:

- the number of scientific papers citing IPCC reports (obtained as described above), and  
- the total number of climate-related scientific publications in a given year.

---

## Figure 2 – Parliamentary Speeches and Policy Documents

### Parliamentary Speeches (Top Panel)

References to IPCC outputs in parliamentary debates are identified through a keyword-based search of:

- European Parliament plenary speeches and debates  
- U.S. Congressional speech records

**Keywords**

- `IPCC`
- `Intergovernmental Panel on Climate Change`

One observation corresponds to a parliamentary speech citing the IPCC at least once.

---

### Policy Documents (Bottom Panels)

Citations to IPCC reports in policy documents are retrieved using **Overton**.

#### Topical Filtering

To focus on climate and environmental policymaking, documents are filtered by subject, including:

- Environmental and Climate policy
- Energy policy
- Migration policy
- Health policy

The full list of sub-fields covered, within each domain, is provided [`here`](overton_topics.md).
Only documents within these domains citing IPCC Assessment or Special Reports, published between 2013 and 2022 (whose full list of DOIs is provided above)
are retrieved, through DOI and title-based queries.
One observation corresponds to a policy document citing at least one IPCC report.


#### Institutional Coverage

Policy documents are collected from:

- **EU Member States** (national governments and parliaments)
- **EU-level institutions**
- **U.S. State-level institutions**
- **U.S. Federal institutions**

The full list of institutions covered, within each category, is provided [`here`](overton_institutions.md).

---

## Figure 3 – UNFCCC Documentation

References to IPCC outputs within UNFCCC documentation are identified using a novel textual dataset constructed by manually downloading documents from the UNFCCC website.
Out of all documents available on the website -  over 56000 at the time of collection (February–April 2024) - a selection is operated based on the following criteria:
  - Relevance to climate policy topics 
  - Relevance of document type
  - English language 
  - PDF format
More details on the topics covered and document types is available HERE.
The final dataset counts over 9000 documents. 

Textual content is extracted and IPCC references are identified using keyword-based searches distinguishing:
- overall IPCC references,
- Working Group I, II, and III references.

---

## Figure 4 – Media Coverage

Media relevance of the IPCC is measured using **Factiva**.

- Coverage period: 2013–2024
- Regions: Europe and United States
- Queries are unconstrained by language or source

Separate keyword sets are used to identify references to:
- IPCC overall
- Working Group I
- Working Group II
- Working Group III

One observation corresponds to a media document matching any keyword permutation.

---

## Reproducibility and Code

Due to licensing restrictions, raw proprietary data cannot be shared.

However, this repository provides:

- aggregated and derived datasets sufficient to reproduce all figures;
- fully documented code for data processing and visualization.

Relevant scripts include:

- `collab.py` – code to reproduce all figures from aggregated data  
  *(links will be added upon final release)*

---

## Data Availability Statement

Access to proprietary data sources (DimensionsAI, Overton, Factiva, Web of Science) is subject to third-party licensing agreements.

Researchers with access to these services can reproduce the full data collection following the procedures documented in this repository.

---

## Contact

For questions regarding data construction or replication:

- Valentina Bosetti  
- Michela Boldrini  
- Marco De Benedectis  
- Alice Zambolin
