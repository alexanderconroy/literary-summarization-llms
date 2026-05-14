# literary-summarization-llms

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alexanderconroy/literary-summarization-llms/blob/main/literary_summarization_llms.ipynb)

Code and analysis notebook accompanying the paper:

**Cultural Memory, Close Reading and Automation: Experiments with Literary Summarization through LLMs**  
Alexander Conroy, Kirstine Nielsen Degn, Matthew Wilkens, Daniel Hershcovich, Ali Al-Laith and Jens Bjerring-Hansen.

## Overview

This repository contains the pipeline used to generate and evaluate automated summaries of canonical and forgotten Danish and Norwegian novels from the nineteenth century. Three large language models are tested across four summarization strategies, and the resulting summaries are evaluated across nine categories. The notebook includes additional analyses beyond those reported in the paper.

## Models

- GPT-5.2 (OpenAI)
- GPT-5-mini (OpenAI)
- Kimi K2 (Moonshot AI, via Together AI / Fireworks AI)

## Summarization strategies

- **Full text** — the entire novel is passed in a single call
- **Hierarchical merging** — the text is chunked, each chunk summarized independently, and the chunk summaries are then summarized into a single final summary
- **Incremental updating** (referred to as *sequential* in the code) — a running summary is updated chunk by chunk and polished at the end
- **Metadata only** — no source text is provided; the model relies solely on bibliographical information (author, title, subtitle, publication year)

## Corpus

Ten Danish and Norwegian novels from the nineteenth century, comprising canonical works and forgotten works from the so-called great unread. 

- J.P. Jacobsen — *Fru Marie Grubbe* (1876)
- J.P. Jacobsen — *Niels Lyhne* (1880)
- Herman Bang — *Tine* (1889)
- Knut Hamsun — *Sult* (1890)
- Kr. Winterhjelm — *Naturalisterne* (1886)
- Vigo Lund — *Præsten* (1896)
- Drude Krog Janson — *Mira* (1897)
- A.T. — *Den Vanvittiges Børn eller Skurken paa Nørrebro* (1870)
- P.B. le Fevre — *Diana eller Haabløs Kjærlighed* (1872)
- Aniken — *Pavo* (1881)

The novels are available via the MeMo corpus on HuggingFace: [MiMe-MeMo/Corpus-v1.1](https://huggingface.co/datasets/MiMe-MeMo/Corpus-v1.1)

## Annotation

Summaries were evaluated by three domain expert annotators across nine categories: Fluency, Coherence, Relevance, Factuality, Time, Place, Characters, Plot, and Themes. Inter-annotator agreement was calculated using Krippendorff's alpha (ordinal). The annotation files are included in `data/annotations/`.

## Setup

API keys for OpenAI, Together AI, and Fireworks AI are required to run the pipeline. File paths should be updated to match your own Google Drive structure.

## Citation

If you use this code or data, please cite:

> Conroy, Alexander, Kirstine Nielsen Degn, Matthew Wilkens, Daniel Hershcovich, Ali Al-Laith and Jens Bjerring-Hansen: "Cultural Memory, Close Reading and Automation: Experiments with Literary Summarization through LLMs." Forthcoming.

