# MAIR: A Massive Benchmark for Evaluating Instructed Retrieval

[![Generic badge](https://img.shields.io/badge/arXiv-2410.10127-red.svg)](https://arxiv.org/abs/2410.10127)
[![LICENSE](https://img.shields.io/badge/license-Apache-blue.svg?style=flat)](https://www.apache.org/licenses/LICENSE-2.0)

We introduce MAIR (Massive Instructed Retrieval Benchmark), a heterogeneous benchmark designed for evaluating instructed information retrieval (IR). MAIR includes 126 retrieval tasks across 6 domains, collected from existing datasets, with each query annotated with detailed retrieval instructions. Compared to other IR benchmarks, MAIR extends the evaluation scope to broader IR applications, including those in RAG, code retrieval, agent-based retrieval, biomedical, legal IR, and more. It also enhances evaluation efficiency through careful data sampling and diversification.

- Paper: [MAIR: A Massive Benchmark for Evaluating Instructed Information Retrieval](https://arxiv.org/abs/2410.10127)
- Data Examples: [MAIR-Example.pdf](https://github.com/sunnweiwei/MAIR/blob/main/assets/MAIR-Example.pdf)

## News
- **[2024.10.14]** Our paper is accepted by EMNLP 2024 Main conference.

## Data
| Data | Link |
| ---- | ---- |
| Queries   | https://huggingface.co/datasets/MAIR-Bench/MAIR-Queries |
| Docs | https://huggingface.co/datasets/MAIR-Bench/MAIR-Docs |

### Queries Data
```python
from datasets import load_dataset
data = load_dataset('MAIR-Bench/MAIR-Queries', 'TASK_NAME')
# e.g., load_dataset('MAIR-Bench/MAIR-Queries', 'CliniDS_2016') to load CliniDS_2016
```
Each row contains four fields:
- `qid`: The query ID.
- `instruction`: The task instruction associated with the query.
- `query`: The content of the query.
- `labels`: A list of relevant documents. Each contains:
- - `id`: The ID of a positive document.
- - `score`: The relevance score of the document (usually 1, but can be higher for multi-graded datasets).
 
### Docs Data
```python
docs = load_dataset('MAIR-Bench/MAIR-Docs', 'TASK_NAME')
# e.g., load_dataset('MAIR-Bench/MAIR-Docs', 'CliniDS_2016') to load docs for CliniDS_2016
```
Each row contains:
- `id`: The ID of the document.
- `doc`: The content of the document.

<details>
<summary>List of 6 domains and 126 tasks.</summary>
  
### Web
- **Table:** WebTableSearch, SParC, SParC-SQL, Spider, Spider-SQL
- **Negation:** ExcluIR, Core17, News21, Robust04, NevIR
- **Entity:** AY2, WnCw, WnWi
- **Tweet:** Microblog_2011, Microblog_2012, Microblog_2013, Microblog_2014
- **Data:** ACORDAR, NTCIR
- **Dialog:** WoW, TopiOCQA, ProCIS-Dialog, ProCIS-Turn, CAsT_2019, CAsT_2020, CAsT_2021, CAsT_2022
- **Fact:** Fever, QuanTemp
- **Meeting:** MISeD
- **Argument:** ArguAna, Touche
- **Doc:** Core_2017, DD_2015, DD_2016, DD_2017, FairRanking_2021, FairRanking_2022, NeuCLIR-Tech_2023, NeuCLIR_2022, NeuCLIR_2023, ToT_2023, ToT_2024, InstructIR
- **Rec:** CPCD, PointRec
- **Query:** CQADupStack, Quora
- **News:** ChroniclingAmericaQA
- **Slot:** TREx, zsRE
- **QA:** ELI5, IFEval
- **Product:** ProductSearch_2023

### Medical
- **Article:** PrecisionMedicine-Article_2019, PrecisionMedicine-Article_2020, CliniDS_2014, CliniDS_2015, CliniDS_2016
- **Entity:** Genomics-AdHoc_2007
- **Trial:** PrecisionMedicine_2017, PrecisionMedicine_2018, PrecisionMedicine_2019, ClinicalTrials_2021, ClinicalTrials_2022, ClinicalTrials_2023
- **Protein:** CARE
- **Doc:** Genomics-AdHoc_2004, Genomics-AdHoc_2005, Genomics-AdHoc_2006
- **QA:** NFCorpus, Trec-Covid, Monant

### Code
- **Agent:** RepoBench, SWE-Bench-Lite
- **Tool:** FoodAPI, HuggingfaceAPI, PytorchAPI, SpotifyAPI, TMDB, TensorAPI, ToolBench, WeatherAPI
- **Code:** APPS, CodeSearchNet, HumanEval-X, LeetCode, MBPP
- **Doc:** Conala, TLDR
- **Diff:** CodeEditSearch

### Legal
- **Summary:** BillSum
- **Case:** AILA2019-Case, GerDaLIR, LeCaRDv2
- **Statute:** AILA2019-Statutes, BSARD, LegalQuAD, REGIR-EU2UK, REGIR-UK2EU
- **Email:** TREC-Legal_2011
- **Contract:** CUAD


### Finance
- **Dialog:** ConvFinQA
- **QA:** Apple, FinQA, FinanceBench, HC3Finance, TAT-DQA, Trade-the-event, FiQA


### Academic
- **Article:** LitSearch, FairRanking_2020
- **Ref:** ProofWiki_Reference, Stacks_Reference, Stein_Reference, Trench_Reference, TAD, TAS2, SciDocs
- **Proof:** ProofWiki_Proof, Stacks_Proof, Stein_Proof, Trench_Proof
- **Fact:** SciFact
- **QA:** Competition-Math, StackMathQA
  
</details>

## Cite
```
@inproceedings{Sun2024MAIR,
  title={MAIR: A Massive Benchmark for Evaluating Instructed Information Retrieval},
  author={Weiwei Sun and Zhengliang Shi and Jiulong Wu and Lingyong Yan and Xinyu Ma and Yiding Liu and Min Cao and Dawei Yin and Zhaochun Ren},
  booktitle={EMNLP},
  year={2024},
}
```
