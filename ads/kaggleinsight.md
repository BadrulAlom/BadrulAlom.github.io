---
layout: default
title: Kaggle Data Science Insight
---

## Cutting through Kaggle Jargon

The [Kaggle discussion forums](https://www.kaggle.com/discussion) are often a place of data science knowledge gained from experience. Rather than letting such knowledge gather dust on the discussion boards I thought I'd capture them into one handy page.

### Steps for tackling a Kaggle competition
- Explore the data, which includes basic outlier analysis.

- Force myself to write error analysis code before I start building a model. (This is hard to stay true to, but worth the effort.). For example, if the contest is binary prediction, I might graph a histogram of predicted probabilities for the positive an negative classes and plot a calibration curve. (Of course, you need to do out-of-fold predictions against your training data to do this.) You could also plot your log-loss versus each categorical variable or binned continuous variable, etc.

If you find that a certain feature value is an outlier compared to the rest of the data set, you could then, e.g., consider whether you might want to separate them out an train two different models. Or perhaps there is some feature engineering or transformation that might help.

	
### Some notable reads
http://blog.kaggle.com/2016/11/17/painter-by-numbers-competition-1st-place-winners-interview-nejc-ilenic/
