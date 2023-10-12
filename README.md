# Exploring Your Data


## Introduction

In this lesson you'll learn about performing an EDA task, using all the statistical and visual EDA skills you have learned so far. 

## Objectives

You will be able to:

* Examine the descriptive statistics of our data set
* Create visualizations to better understand the distributions of variables in a dataset


## Exploratory Data Analysis

Exploratory Data Analysis, or **_EDA_**, is a crucial part of any Data Science project.  Before you can go off building models on a dataset, you need to be familiar with the actual data it contains -- otherwise, you'll have no intuition about how to interpret the results of these models, or even if you can trust them at all!

This lesson will outline the basic steps that should be taken -- and questions that should be answered during EDA. 

## Understanding the Distribution of the Dataset

One of the foundational pieces of an EDA investigation is to understand the underlying distribution of the data.  Often, some of the most interesting/important business insights come not from machine learning models, but simply from exploring the distribution of the dataset! If your company or organization has not yet mastered reporting on descriptive analytics, the insights gained here can be invaluable to company strategy -- think questions such as "who is my most profitable customer segment?" or "is there a seasonality to our customer churn rate?".  These are important questions to any business, and they don't require machine learning models to answer them -- just some basic visualizations, and the ability to ask good questions.

Getting a feel for the distribution of a dataset is done in a few different ways. Generally, you'll make use of high-level descriptive statistics, followed by visualizations. During the EDA process, it is quite common to uncover interesting things in the data that spur further questions for the investigation.  

> "The most exciting phrase to hear in science, the one that heralds new discoveries, is not 'Eureka!' (I found it!) but 'That's funny...'"
>
>                                            - Isaac Asimov


Recall that Pandas can easily provide descriptive statistics of a DataFrame by using the DataFrame class's built-in `.describe()` method.  The resulting output is a table containing information such as the count, mean, median, min, max, and quartile values for every column in the DataFrame.  This is especially handy for answering questions such as "how much variance can I expect in column {X}?"

### Visualizing Distributions - Histograms

The easiest way to understand the distribution of a dataset is to visualize it! Recall that since `pandas` uses the `matplotlib` library, you can easily create histograms showing the distribution of each column by using the DataFrame's built-in `.hist()` method.  

<img src='https://curriculum-content.s3.amazonaws.com/data-science/images/sample_hist.png'>

### Visualizing Distributions - Kernel Density Estimation (KDE) Plots

Another great way of quickly visualizing the distribution of a column is to construct a **_KDE Plot_**. This is often overlaid on a histogram to create a line that visualizes an approximate probability density of the variable. 

<img src='https://curriculum-content.s3.amazonaws.com/data-science/images/sample_kde.png'>


### Using Joint Plots

A more advanced visualization tool you can make use of is the **_Joint Plot_**.  This allows you to visualize a scatterplot, the distributions of two different columns, a [KDE plot](https://seaborn.pydata.org/generated/seaborn.kdeplot.html), and even a simple regression line all on the same visualization. In practice, this is incredibly handy for doing this like checking the linearity assumption between predictors and a target variable during a regression analysis. 

Since joint plots are more advanced than a basic visualization like a histogram or scatterplot, you'll need to make use of the **_seaborn_** library to create them. The syntax for creating a joint plot is:

```python
# sns is the standard alias for seaborn
sns.jointplot(x= <column>, y= <column>, data=<dataset>, kind='reg')

```

<img src='https://curriculum-content.s3.amazonaws.com/data-science/images/sample_jointplot.png'>

For full details on how to create joint plots with seaborn, see the [seaborn documentation on joint plots](https://seaborn.pydata.org/generated/seaborn.jointplot.html)!

## Interpreting Your EDA Results

It is worth noting that the goal of EDA is not pretty visualizations -- it's _insight into your data_!  Don't fall into the trap of thinking that EDA means building a couple of quick visualizations and then moving onto modeling -- you should actively try to generate questions and see if you can answer them by exploring the dataset.  Visualizations are great, but only because they make it easy to quickly interpret our data.  Use them as a tool, not a goal, during the EDA process!

## Summary

In this lesson, you reviewed descriptive statistics and data visualizations -- two critical components of EDA. Specifically, you reviewed the `.describe()` method for obtaining the descriptive statistics of a DataFrame. You then saw how you can use data visualizations like histograms, KDE plots, and joint plots to gain some insight into your data!
