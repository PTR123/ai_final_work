# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an AI/Machine Learning course repository focused on teaching fundamental ML algorithms through from-scratch implementations. The pedagogical approach emphasizes understanding algorithms step-by-step with heavily commented, minimal-dependency Python code.

## Core Dataset

The **Watermelon Dataset (西瓜数据集)** is the canonical example used throughout:
- 6 categorical features: 色泽 (color), 根蒂 (root), 敲声 (sound), 纹理 (texture), 脐部 (navel), 触感 (touch)
- Binary label: 好瓜 (good/bad melon)
- Data format: Python dictionaries, not pandas/DataFrame

## Decision Tree Implementation Components

When implementing or extending decision tree algorithms:

1. **Entropy Calculation** (`calculate_entropy`): Uses `math.log2` only - no sklearn
2. **Information Gain** (`calculate_information_gain`): Computes feature quality via entropy reduction
3. **Best Feature Selection** (`find_best_feature`): Greedy selection by max information gain
4. **Tree Training** (`train_decision_tree`): Recursive ID3-style algorithm with two termination conditions:
   - Pure node (all samples same class)
   - No remaining features
5. **Prediction** (`predict`): Recursive tree traversal matching feature values

## Code Style for Teaching Materials

All implementations should follow these conventions:
- **Minimal dependencies**: Use only `math`, avoid numpy/sklearn/pandas for core algorithms
- **Line-by-line comments**: Every line must have a Chinese comment explaining its purpose
- **Simple data structures**: Prefer Python dicts/lists over specialized ML structures
- **Step-by-step progression**: Each concept in a separate cell with markdown explanation
- **Chinese terminology**: Use Chinese variable names and comments where appropriate (色泽, 根蒂, etc.)

## Jupyter Notebook Workflow

```bash
# Run notebook in browser
jupyter notebook DecisionTree.ipynb

# Execute notebook headless (for testing)
jupyter nbconvert --to notebook --execute DecisionTree.ipynb

# Convert to Python script
jupyter nbconvert --to script DecisionTree.ipynb
```

## Extension Topics (Future Work)

This repository may expand to cover:
- Information Gain Ratio (C4.5 algorithm)
- Gini Index (CART algorithm)
- Pruning strategies (pre-pruning, post-pruning)
- Continuous feature handling (threshold splitting)
- Missing value handling
- Multi-class classification
- Regression trees

## Prompt Engineering for ML Learning

The notebook was generated using specific prompt patterns. When extending:
- Request "代码要极其简单，每一行都加详细注释"
- Specify constraints like "只用 math.log2，不要用其他复杂库"
- Provide context about the target audience (beginners learning ML concepts)