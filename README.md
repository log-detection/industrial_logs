This repository provides the reproducibility materials for the paper:

**Industrial Log Analysis Revisited: A Task-Oriented Evaluation of Parsing and Anomaly Detection under Real-World Constraints**

## Overview

Log analysis in industrial software systems presents unique challenges that are often underrepresented in public benchmark datasets. Compared with widely used public repositories such as LogHub, industrial logs typically exhibit higher structural diversity, stronger context dependence, greater semantic ambiguity, and more severe privacy constraints. These characteristics make it difficult to directly reproduce empirical studies based on proprietary industrial datasets.

To address reproducibility concerns as much as possible, we have taken several concrete steps.

First, in collaboration with our industrial partners, we release a set of **representative anonymized log samples** that preserve key structural and semantic characteristics of the original industrial datasets. These samples are intentionally selected to reflect **higher complexity** and **greater divergence from public benchmarks such as LogHub**, thereby capturing essential properties of real-world industrial logs.

Second, we make publicly available the **complete implementation details of our experimental pipeline**, including:

- representative anonymized industrial log samples,
- implementations of log parsing methods,
- implementations of anomaly detection models,

We hope these resources can support future research on industrial log analysis and provide a practical basis for replication, comparison, and extension.
