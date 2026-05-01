# ConceptProbing_TrustNLP2026

This repository contains the datasets released with the paper:

**What are They Thinking? Delineation, Probing and Tracking of Concepts in LLMs**  

These datasets are designed to support research on detecting high-level abstract concepts in the embeddings of large language models using linear probes.

The paper studies four concepts:

- **Ambition**
- **Investigation**
- **Democracy**
- **Envy**

## Overview

This repository contains two main types of datasets:

1. **Concept probe datasets**  
   Binary labeled datasets used to train and evaluate concept probes. Each example is labeled according to whether the target concept is present or absent.

2. **Story datasets**  
   Longer context datasets used to study how a concept waxes and wanes across an expanding context. Each story contains sentences where the target concept is present only at specific points, allowing probes to be evaluated over longer contexts.

The repository also includes the example templates used to generate the concept probe datasets.

## Repository structure

```
  concept_probe_datasets/
    ambition.csv
    democracy.csv
    envy.csv
    investigation.csv
    templates.txt

  story_datasets/
    amb_strength.csv
    dem_strength.csv
    env_strength.csv
    inv_strength.csv

```

## Files

### Concept probe datasets

The `concept_probe_datasets/` folder contains the binary datasets used for training and testing concept probes.

| File | Description |
|---|---|
| `ambition.csv` | Examples where ambition is present or absent |
| `investigation.csv` | Examples where investigation is present or absent |
| `democracy.csv` | Examples where democracy is present or absent |
| `envy.csv` | Examples where envy is present or absent |
| `templates.txt` | Example templates used to generate the concept probe datasets |

The concept probe datasets are intended for training binary classifiers on LLM embeddings. In the paper, these classifiers are linear probes trained to detect whether a target concept is encoded in a model's embeddings.

### Story datasets

The `story_datasets/` folder contains longer-context datasets used to study concept tracking across expanding input contexts.

| File | Description |
|---|---|
| `amb_strength.csv` | Stories used to evaluate waxing and waning of ambition |
| `inv_strength.csv` | Stories used to evaluate waxing and waning of investigation |
| `dem_strength.csv` | Stories used to evaluate waxing and waning of democracy |
| `env_strength.csv` | Stories used to evaluate waxing and waning of envy |

These datasets are used to evaluate whether probes can track changes in concept presence as more words are added to the input context.

## Intended use

These datasets can be used to:

- train linear probes for detecting abstract concepts in LLM embeddings;
- evaluate whether an LLM internally represents concepts such as ambition, investigation, democracy, or envy;
- compare concept representations across models, layers, and embedding choices;
- study how concept presence changes as more context is added to an input sequence;
- support research on LLM interpretability, monitoring, and explainability.

## Dataset creation summary

The concept probe datasets were created using example templates derived from text passages. For each target concept, positive and negative examples were generated to match the structure of these templates while varying whether the target concept was present or absent.

The generated examples were then labeled for concept presence or absence. These binary datasets were used to train and evaluate concept probes.

The story datasets were created separately for the waxing-and-waning experiments. They contain longer stories in which the target concept appears only at specific points, allowing probe outputs to be tracked across an expanding context.

## Citation (NEEDS TO BE CHANGED ONCE PAPER IS PUBLISHED)

If you use these datasets, please cite the associated paper:

```
@inproceedings{
anonymous2026what,
title={What are They Thinking? Delineation, Probing and Tracking of Concepts in {LLM}s},
author={Anonymous},
booktitle={The 6th Workshop on Trustworthy NLP},
year={2026},
url={https://openreview.net/forum?id=5YAWtv1JdR}
}
```

## License

This dataset is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0).

See the `LICENSE` file for details.

If you use this dataset, please cite the associated paper above.

## Contact

For questions about the datasets or paper, please contact:

**Name:** Mohamed Abdelwahab

**Email:** mo.abdelwahab@mail.utoronto.ca
