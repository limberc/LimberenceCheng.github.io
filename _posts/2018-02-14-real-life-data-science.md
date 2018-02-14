---
layout: post
title: Real life data science
date: 2018-1-28 19:39:09
description: This article covered the common pitfalls and protections from them in data analysis. 
img: data-science.jpg
tags: [Notes]
---
## Introduction

You ran an AB test. Data collection pulls and mergers all went perfectly. There was no missing data. The sample was easily generalizable to the population you're interested in. Tests were robust and highly significant. And actual conclusions were obvious from the results of your test. Has this ever happened to you? 

Of course not. Instead, your experiments are with observational data on a sample that isn't representative of the population that you're interested in. You have missing data and errors in data collection. Through a complex merging. The results of your test are borderline and the conclusions are not clear. 

This article covered the common pitfalls and protections from them in data analysis. 

## Core content

I would like to cover these following two sections in this article.

1.  **How design can protect you in your recourse for when design is out of your control. **
2. **When it's appropriate to throw in the towel and say that your data just can't answer the questions that you'd like to ask.**

Mostly, this post were introduced by following steps:

1. The data pull is clean. In this lesson, we discuss the ideal setting where creating the analytic data set goes perfectly. Since this never happens, we give some strategies for managing the creation of analytic data sets. The first is creating summary tables with means, medians, other quantiles and standard deviations. The second is looking at diagnostics from regression output. The third is a strange little fact called Benford's law. The final suggestion is to perform sampling based data quality queries.
2. The experiment is carefully designed, principles. In this lesson, we cover experimental design and what happens when we have observational data. We also discuss causality and randomization's role in uncovering it. Then we move on to discuss confounding, a central problem of observational studies and adjustment, the first line of defense for confounding.
3. The experiment is carefully designed, things to do. OK now that we know some of the concepts we can talk about things to do. First, we discuss A/B testing, the adjustment for confounding. We also discuss methods for combating sampling bias.
4. The results of analyses are clear. In this lesson, we cover issues when the results of analyses aren't easy to understand, especially focusing on hypothesis tests. First, we broadly discuss the need to consider more than hypothesis tests. Then we consider issues and strategies with testing and statistical results. Next, we discuss multiple comparisons and their role in hypothesis testing. Then we suggest comparing results of unknown phenomena with that of known. Finally, we discuss negative control analyses.
5. The decision is obvious. There are many reasons why decisions are not obvious. First, the data can be very equivocal about the hypotheses. We discuss power as it relates to this issues. Secondly, even in the presence of significant results, one may not have measured the right quantities.
6. The analysis product is awesome. In this module we discuss the final report. Here we make two recommendations. The first is enforcing reproducible of analysis documents. We suggest tools for doing this. Secondly, we suggest version controlling the software and give recommended solutions.

Throughout, we focus on managerial topics. That is, high level conceptual issues, or practical recommendations that can be made to data scientists.

## The Ideal data science experiments and the real-life data science experiments

1. **Clearly defined hypotheses of interest, specified a priori**

Experimental design is at your disposal so you have a lot of control over what you do prior to collecting data. So for example, you might be able to conduct an AB test and do randomization across a treatment of interest. Or if you have some nuisance variables that you're not interested in, you might be able to stratify across those. 

2. **Experimental design available(Things like Randomization, Blocking, Random Sampling)**


1. **Data directly able to interrogate hypotheses**
2. **Dataset creation/merging goes smoothly**
3. **No missing data or dropout**
4. **Analysis is robust without need for advanced modelling**
5. **Conclusions are clear that parsimonious of knowledge is gained via the experiments.**
6. **The decision is obvious being given the data and communicated clearly with a nice report or out going data product. **



However, in the real life, the data is needed to both inform the hypotheses and interrogate the hypotheses. Often multiple comparisons are an issue because you've tried several different hypotheses or you're looking at multiple things at once.  Often your access to experimental design is limited or non-existent. The data is often completely observational. So the population being studied isn't the population that you're interested in. That's often a problem, your sample isn't representative of the sample you'd like to generalize to. The data don't have the exact measurements that you need to evaluate the hypothesis. This is a surprisingly common problem. You'd like to study caloric intake, but all you have is questionnaires asking people how many calories they ate last week, which they can't usually remember well.  The data set is problematic, merging is problematic with multiple matches or no matches. Data entry errors, the data pool doesn't go the way that you want, so often the case that just the reality of building the analytic data set is a challenging process. You have missing data and because of the observational nature of your experiment, advanced modelling winds up being required. And then because you need advanced modelling, advanced computing is needed to fit the model, which raises issues with robustness and bugs. 

Then, you're all done with this process, and the conclusions wind up being indeterminate. And the decision is not substantially and further informed by the data and the models that you've fit. So, that's what happens maybe, maybe in some of the worst case scenarios, but that's more like what happened tends to happen in real life. 

So here, we would like to talk about how you can, some ideas for how you can check for errant data and other tools to make data analysis in real life a little bit more manageable.