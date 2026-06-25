# HUM-450 Impresso — Swiss Political Discourse Over Time

![Graph](Gazette.jpg)

This project analyzes the evolution of the Swiss political landscape using historical newspaper archives from the *Gazette de Lausanne*. We combine text mining, network analysis, and NLP to study how political actors, parties, and themes evolve across time.

Developed as part of the HUM-450 course, the project uses the Impresso historical newspaper database as its primary data source.

## Resources

- Dataset: https://drive.google.com/drive/folders/1MrYjVUJPSUubAc8UD3Xr5nPydXtFjPC4
- Meeting minutes: https://docs.google.com/document/d/1MZljVlTuPxJEN6x6_YJ1NsprmuwVyBtuHUd1bHjtjUI

## Research Question

> How does the Swiss political landscape evolve over time according to the *Gazette de Lausanne*?

We approach this question through:

- Named entity extraction
- Co-occurrence network analysis
- Sentiment analysis
- Temporal comparison across historical periods

## Data Sources

### Impresso

The project relies on the Impresso historical newspaper archive:

https://impresso-project.ch/

Articles from the *Gazette de Lausanne* were filtered according to:

- Time periods (1890–1910, 1945–1965, 1966–1980)
- Political parties and their abbreviations
- Article-type documents

### External Enrichment

- Elites Suisses (UNIL)
- Wikipedia

These sources are used to enrich extracted political figures with biographical metadata.

## Methodology

### Data Processing

For each time period, articles are extracted from Impresso and compiled into structured datasets containing:

- Article metadata
- Named entities
- Publication information
- Co-occurrence data

### Network Analysis

Political networks are constructed as weighted co-occurrence graphs:

- Nodes represent individuals
- Edges connect individuals mentioned in the same article
- Edge weights correspond to co-occurrence frequency

Graphs are exported in GEXF format and analyzed using Gephi.

### Sentiment Analysis

French-language NLP preprocessing includes:

- Tokenization
- Stopword removal
- Context-window extraction

Sentiment classification is performed using a CamemBERT-based model, producing:

- Sentiment scores
- Confidence scores
- Temporal sentiment trends by political party

### Temporal Analysis

Results are compared across three historical periods:

- 1890–1910
- 1945–1965
- 1966–1980

## Tech Stack

- Python
- pandas
- numpy
- networkx
- HuggingFace Transformers (CamemBERT)
- Gephi
- Poetry
- pre-commit

## Installation

```bash
git clone git@github.com:edouardkoehn/HUM-450.git
cd HUM-450

conda create -n HUM-450 python=3
conda activate HUM-450

pip install poetry
poetry install

poetry run pre-commit install
