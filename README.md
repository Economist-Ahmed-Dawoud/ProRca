# Causal RCA: A Causal Pathway Approach for Complex Operational Environments

## Overview

**Causal RCA** is a framework for performing root cause pathway analysis in complex operational environments such as healthcare systems, retail supply chains, and warehouse automation. Unlike traditional methods that rely on correlation-based anomaly detection or feature-importance measures, this framework leverages structural causal modeling (SCM) to uncover multi-hop causal chains and rank them based on their likelihood of triggering observed anomalies.

This project builds on the [DoWhy](https://github.com/py-why/dowhy) causal inference library and extends its capabilities with:
- **Conditional Anomaly Scoring:** Quantifies how unexpected a node’s observation is relative to its predicted distribution.
- **Path Discovery & Ranking:** Performs backward traversals in the causal graph to discover multi-hop pathways and ranks them using aggregated anomaly scores.
- **Advanced Visualizations:** Uses Graphviz to generate clear, high-resolution visual representations of causal pathways, with customizable gradient backgrounds to indicate path importance.
- **Anomaly Detection Integration:** Leverages ADTK for anomaly detection in time series data.

The methodology is inspired by the paper:

> **Beyond Traditional Problem-Solving: A Causal Pathway Approach for Complex Operational Environments**  
> *Ahmed Dawoud & Shravan Talupula, January 31, 2025*  
>  
> **Abstract:**  
> Identifying and mitigating anomalies in modern operational environments is a high-stakes challenge. Traditional methods often rely on correlation-based anomaly detection or feature-importance measures, which frequently fail to uncover true causal pathways. In this paper, we introduce a novel methodology built on the DoWhy causal inference library for root cause pathway analysis. Our framework extends to multi-hop causal chains, ranking them by aggregated anomaly scores, and providing decision-makers with actionable insights on the most probable root causes. Examples from warehouse operations demonstrate how multi-factor disruptions can be diagnosed more effectively than with conventional approaches.

## Features

- **SCM Builder:** Build a structural causal model using `ScmBuilder`, which constructs causal graphs from given nodes and edges.
- **Root Cause Analysis:** Use `CausalRootCauseAnalyzer` to compute conditional anomaly scores, discover multi-hop causal pathways, and rank them.
- **Anomaly Detection:** Detect anomalies in operational data using the `AnomalyDetector` class with ADTK.
- **Visualization:** Visualize causal pathways and related metrics using `CausalResultsVisualizer`, featuring customizable gradients and layouts.

## Project Structure

- **`scm_builder.py`**  
  Contains the `ScmBuilder` class for creating and fitting a Structural Causal Model (SCM).

- **`causal_root_cause_analyzer.py`**  
  Implements `CausalRootCauseAnalyzer`, which calculates node-level anomaly scores, discovers causal paths, and ranks them.

- **`anomaly_detector.py`**  
  Provides the `AnomalyDetector` class that uses ADTK to detect anomalies in time series data and visualize them.

- **`visualization.py`**  
  Contains the `CausalResultsVisualizer` class with methods for visualizing the causal pathways. For example, the `plot_root_cause_paths` method creates a Graphviz diagram with a customizable green-to-yellow gradient background and removes duplicate arrows for clarity.

- **`README.md`**  
  This file.

## Dependencies

- Python 3.7+
- [DoWhy](https://github.com/py-why/dowhy)
- [NetworkX](https://networkx.org/)
- [Graphviz](https://graphviz.org/) (and its Python bindings)
- [IPython](https://ipython.org/)
- [Matplotlib](https://matplotlib.org/)
- [Seaborn](https://seaborn.pydata.org/)
- [ADTK](https://github.com/arundo/adtk)

## Installation

Clone the repository and install the required packages:

```bash
git clone https://github.com/yourusername/causal-rca.git
cd causal-rca
pip install -r requirements.txt
