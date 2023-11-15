# Tackling Tech Debt with Transformers

Welcome to Tackling Tech Debt With Transformers! 🚀 Here, we're all about using fine-tuned transformer models to help open source repositories keep their technical debt in check.

## Features

- **Feature 1**: Diff Extraction
- **Feature 2**: Tech Debt Classifier
- **Feature 3**: Tech Debt Label Generator

## Overview

### What is Technical Debt?
"Implied cost of future reworking required when choosing an easy but limited solution instead of a better approach that could take more time." Wikipedia.
Common application: Think of taking a shortcut when you are pushed for time. Later, you have to come back and rework code to "repay" the debt.

### What Data Can We Use?
The Technical Debt Dataset!
* 78K commits from 33 Java projects
* Annotations from SZZ Algorithm for technical debt
* Labels from SonarQube for code smells

Read more from their paper: [The Technical Debt Dataset](https://dl.acm.org/doi/abs/10.1145/3345629.3345630)
and their repo: [Technical Debt Dataset](https://github.com/clowee/The-Technical-Debt-Dataset)

Lenarduzzi, Valentina, Nyyti Saarimäki, and Davide Taibi. "The technical debt dataset." Proceedings of the fifteenth international conference on predictive models and data analytics in software engineering. 2019.

We use this dataset to create our own two datasets:
* [Classification Dataset](https://huggingface.co/datasets/davidgaofc/techdebt)
* [Label Generation Dataset](https://huggingface.co/datasets/davidgaofc/techdebt_label)

### What Models Will We Train?
We will be fine-tuning a small [CodeBERTa model](https://huggingface.co/huggingface/CodeBERTa-small-v1) for classification
and a small [codeT5 model](https://huggingface.co/Salesforce/codet5-small) for label generation.

This results in two models:
* [Tech Debt Classifier](https://huggingface.co/davidgaofc/TechDebtClassifier)
* [Tech Debt Label Generator](https://huggingface.co/davidgaofc/TechDebtLabeler)

## Interactive Demo
Visit this [Huggingface space](https://huggingface.co/spaces/davidgaofc/TechDebtPipeline) created by me!
You can see how the models work together!

## Critical Analysis
* Impact: Now you can analyze the commits in any repo!
  * You can see which commits might have tech debt!
    * 95.4% accuracy on test set
    * 0.949 F1 score on test set
  * You can see what kind of tech debt it might be!
* Next steps: 
  * We can improve the model by using better/more data.
  * Label generation needs to be evaluated more.

## Video Recording
[YouTube Video Overview of this Project](https://youtu.be/zzC-xD28D3c)

## More Resources
* [Technical Debt Classification in Issue Trackers using Natural Language Processing based on Transformers](https://ieeexplore.ieee.org/abstract/document/10207085)
* [Learn how to fine-tune your own model with Huggingface](https://huggingface.co/docs/transformers/training)
* [Specifically for classification - still Huggingface](https://huggingface.co/docs/transformers/v4.17.0/en/tasks/sequence_classification)


