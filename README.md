# Enron Email Network Analysis

Data mining and network analysis of the Enron email dataset to detect anomalous communication patterns and potential fraudulent behavior.

## Overview

This project analyzes the Enron email corpus (517,401 emails) using graph-based network analysis and statistical methods to identify suspicious communication patterns that may indicate fraud or compliance violations.

## Problem Statement

The Enron scandal demonstrates how analyzing internal communications could have helped uncover wrongdoing earlier. This project applies data mining techniques to:
- Detect anomalous email communication patterns
- Identify potentially fraudulent behavior through network analysis
- Demonstrate practical applications for fraud detection in organizations

## Methodology

### 1. Data Collection & Processing
- **Dataset**: Enron Email Dataset from CMU (~517K emails)
- **Extraction**: Parse sender/receiver information from raw email files
- **Network Construction**: Build directed graph with email addresses as nodes and communication frequency as edge weights

### 2. Network Analysis
- Calculate **in-degree centrality** (emails received)
- Calculate **out-degree centrality** (emails sent)
- Identify top communicators and communication patterns

### 3. Anomaly Detection
- Compute statistical thresholds (mean + 2×std deviation)
- Flag accounts with abnormally high in-degree or out-degree
- Identify potential spam behavior or targeted communication

## Key Findings

- **Network Size**: 440 nodes, 495 edges (sample of 1,000 emails)
- **Anomalous Receivers**: 4 accounts flagged (threshold: 44 emails)
- **Anomalous Senders**: 15 accounts flagged (threshold: 16 emails)
- Top receiver: `john.arnold@enron.com` (410 emails)
- Top sender: `joey.taylor@enron.com` (73 emails)

## Technical Stack

- **Language**: Python 3.x
- **Libraries**: 
  - NetworkX (graph analysis)
  - Pandas (data manipulation)
  - NumPy (statistical analysis)
  - Matplotlib (visualization)
  - Regular expressions (email parsing)

## Project Structure

```
.
├── CaseStudy4.ipynb          # Main analysis notebook
├── maildir.zip               # Full Enron dataset (937 MB)
├── maildir_reduced.zip       # Reduced dataset (228 MB)
└── README.md
```

## Usage

1. **Extract dataset**:
```python
import zipfile
with zipfile.ZipFile('maildir_reduced.zip', 'r') as zip_ref:
    zip_ref.extractall('maildir_reduced')
```

2. **Run analysis**: Open `CaseStudy4.ipynb` in Jupyter Notebook

3. **View results**: Network graphs and anomaly detection outputs

## Results Visualization

- Communication network graph (top 30 edges)
- In-degree/out-degree distribution
- Anomalous node identification

## Applications

- **Fraud Detection**: Identify unusual communication patterns
- **Compliance Monitoring**: Flag potential policy violations
- **Organizational Analysis**: Understand communication hierarchies
- **Security**: Detect spam or malicious activity

## Dataset

- **Source**: [CMU Enron Email Dataset](https://www.cs.cmu.edu/~./enron/)
- **Size**: 517,401 emails from 150 users
- **Period**: Enron Corporation emails (1998-2002)


