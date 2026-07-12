# From Scientific Bedrock to Policy Relevance  
## Data Sources and Methods

This repository provides detailed methodological documentation supporting the paper  
**“From Scientific Bedrock to Policy Relevance: The Evolving Roles of the IPCC Working Groups.”** by Valentina Bosetti, Michela Boldrini, Marco De Benedictis, Alice Zambolin.

Due to the use of proprietary data sources, this repository **substitutes and extends the Methods section of the paper**, ensuring transparency and replicability to the extent permitted by data access restrictions.

The repository also includes code to reproduce all figures using **aggregated and derived data**.

---

## Overview of Data Sources

The analysis combines multiple data sources to track references and citations to IPCC Assessment and Special Reports across science, policy, international negotiations, and media.

| Domain | Data Source | Access | Code |
|------|------------|--------|--------|
| Scientific publications | [DimensionsAI](https://app.dimensions.ai), [Web of Science]( https://clarivate.com/academia-government/scientific-and-academic-research/research-discovery-and-referencing/web-of-science/) | Proprietary | [code](https://colab.research.google.com/drive/1ZxMK9drRj1KVShQ8Eoy2kTGQzMcbSRP2?usp=sharing) |
| Policy documents | [Overton](https://www.overton.io/) | Proprietary | [code](https://colab.research.google.com/drive/1p63dkz2RGEW058jtry3InyZx_MVMRLyc?usp=sharing) |
| UNFCCC documents | [UNFCCC website](https://unfccc.int/documents) | Public | [code](https://colab.research.google.com/drive/1BmV8RswdUGNqAAClEL0_Vm2Yt2EIM35c?usp=sharing) |
| Media coverage | [Factiva](https://global.factiva.com/) | Proprietary | [code](https://colab.research.google.com/drive/1TPAS1Zl5lLkcsUt0Y-BG7XfQ7iCKnSBc?usp=sharing)|
| Supplementary Materials |
| Parliamentary debates | [European Parliament](https://www.europarl.europa.eu/plenary/en/home.html), [U.S. Congress](https://www.congress.gov) | Public | [code](https://colab.research.google.com/drive/1GMesfiCT3SOLM_mf4LutbvqN2vU-kWLR?usp=sharing) |
---

## Figure 1 – Scientific Publications

Data on citations to IPCC Assessment and Special Reports in scientific papers are retrieved using **DimensionsAI – Altmetrics**, through DOI-based queries.

- One observation corresponds to a scientific paper citing one of the IPCC reports considered.
- Coverage includes the **Assessment Reports (AR5, AR6)** and **Special Reports** published between 2011 and 2025.

#### IPCC Reports Included

**Assessment Reports**

- AR5  
  - Working Group I (2013): `10.1017/cbo9781107415324`  
  - Working Group II (2014): `10.1017/cbo9781107415379` (Part A), `10.1017/cbo9781107415386` (Part B)
  - Working Group III (2014): `10.1017/cbo9781107415416`  

- AR6  
  - Working Group I (2021): `10.1017/9781009157896`  
  - Working Group II (2022): `10.1017/9781009325844`  
  - Working Group III (2022): `10.1017/9781009157926`  

**Special Reports**

- SRREN (2011): `10.1017/CBO9781139151153`  
- SR1.5 (2018): `10.1017/9781009157940`  
- SR Ocean (2019): `10.1017/9781009157964`  
- SR Land (2022): `10.1017/9781009157988`

The same data is used to produce Figure A1 in the Supplementary Materials, with the addition of the AR4 Report - contribution of Working Group III (2007): `10.1017/CBO9780511546013`.  


#### IPCC relevance in scientific publications

To account for trends in overall scientific production, we retrieve the yearly total number of climate-related scientific papers through a `Climate Change` topic search on **Web of Science**.
Following Vasileiadou et al. (2011), we compute a normalized measure of IPCC relevance, defined as the ratio between:

- the number of scientific papers citing IPCC reports (obtained as described above), and  
- the total number of climate-related scientific publications in a given year.



## Figure 2 – Policy Documents

Citations to IPCC reports in policy documents are retrieved using **Overton**.

#### Topical Filtering

To focus on climate and environmental policymaking, documents are filtered by subject, including:

- Environmental and Climate policy
- Energy policy
- Migration policy
- Health policy

The full list of sub-fields covered within each domain is provided [`here`](overton_topics.md).
Only documents within these domains citing IPCC Assessment or Special Reports, published between 2011 and 2022 (whose full list of DOIs is provided above)
are retrieved title-based queries.
One observation corresponds to a policy document citing one of the IPCC reports.

#### Institutional Coverage

Policy documents are collected from:

- **EU Nations** (national governments and parliaments)
- **EU Bodies** (EU-level supranational institutions) 
- **US States**
- **US Federal institutions**

The full list of institutions covered, within each category, is provided [`here`](overton_institutions.md).
Within regions, data are then aggregated to produce the graphical representations.
The same data is used to produce Figure A3 in the Supplementary Materials.


#### IPCC relevance in policy documents

To allow for a direct comparison of IPCC reports' relative importance across geographies and institutional settings, despite marked differences in volumes, we compute a normalized measure of IPCC relevance, defined as the ratio between:

- the yearly total number of policy documents citing IPCC reports (obtained as described above), and  
- the overall number of policy documents produced in the domains of interest in a given year.
  
---



## Figure 3 – UNFCCC Documentation

References to IPCC outputs within UNFCCC documentation are identified using a novel textual dataset constructed by manually downloading documents from the UNFCCC website.
Out of all documents available on the website -  over 56000 at the time of collection (February–April 2024) - a selection is made based on the following criteria:
  - Relevance to climate policy topics 
  - Relevance of document type
  - English language 
  - PDF format

More details on the topics covered and document types are available [`here`](unfccc.md).

The final dataset counts over 9000 documents (for more detailed info on the dataset's construction, please check [here](https://github.com/mdb2000/UNFCCC-Human-mobility)).
From the final dataset, the textual content of documents is extracted, and the frequency and distribution of citations to the IPCC are assessed through a keyword-based search. 
References to IPCC outputs in UNFCCC documents were identified through a keyword-based search using the following permutations.

| Category | Keywords / Search Strings |
|---------|---------------------------|
| **Working Group I** | `(IPCC AND Working Group I/1)` OR `(IPCC AND WGI/1)` OR `(Intergovernmental Panel on Climate Change AND Working Group I/1)` OR `(Intergovernmental Panel on Climate Change AND WGI/1)` |
| **Working Group II** | `(IPCC AND Working Group II/2)` OR `(IPCC AND WGII/2)` OR `(Intergovernmental Panel on Climate Change AND Working Group II/2)` OR `(Intergovernmental Panel on Climate Change AND WGII/2)` |
| **Working Group III** | `(IPCC AND Working Group III/3)` OR `(IPCC AND WGIII/3)` OR `(Intergovernmental Panel on Climate Change AND Working Group III/3)` OR `(Intergovernmental Panel on Climate Change AND WGIII/3)` |

One observation corresponds to a document matching any of the permutations.
The same data is used to produce Figure A4 in the Supplementary Materials.


---

## Figure 4 – Media

Media relevance of the IPCC is measured using **Factiva**.
We obtain the count of references to each individual Working Group output and the IPCC through a keywords-based search.
- Coverage period: 2013–2024
- Regions: European Union Countries, United States
- Source Type: we restrict the search to media outlets only (we exclude: Business Sources, Business to Consumer Services (B2C), Dow Jones Sources, European Union Sources, Government and Politics, Legal Sources, Nongovernmental organizations (NGO), Official Government Sources, Research Reports, Sports, Think Tanks).
- Queries are unconstrained by language.

One observation corresponds to a media document matching any keyword permutation.
The full list of keyword permutations used is available [`here`](factiva.md). 
The same data is used to produce Figure A5 in the Supplementary Materials.

#### IPCC relevance in the media

To ease comparisons, we compute a normalized measure of IPCC relevance in the media for each region, defined as the ratio between:

- the yearly count of general references to the IPCC in the news (obtained as described above), and
- the total volume of news covering topics related to climate change and global warmingin a given year.



---
## Supplementary Materials
---

## Figure A2 – Parliamentary Debates 

References to IPCC outputs in parliamentary debates are identified through a keyword-based search of:

- European Parliament plenary [minutes](https://www.europarl.europa.eu/plenary/en/minutes.html), [debates and video](https://www.europarl.europa.eu/plenary/en/debates-video.html) recordings
- U.S. Congressional speech records 

**Keywords**

- `IPCC`
- `Intergovernmental Panel on Climate Change`

One observation corresponds to a record mentioning the IPCC at least once.

---

## Reproducibility and Code

Due to licensing restrictions, raw proprietary data cannot be shared.

However, this repository provides:

- Aggregated and derived datasets sufficient to reproduce all figures;
- Fully documented code for data processing and visualization.

---

## Data Availability Statement

Access to proprietary data sources (DimensionsAI, Overton, Factiva, Web of Science) is subject to third-party licensing agreements.
Researchers with access to these services can reproduce the full data collection following the procedures documented in this repository.

---

## Contact

For questions regarding data construction or replication, contact [Michela Boldrini](mailto:michela.boldrini@cmcc.it).
