# Amazon-review-classification

In collaboration with Gediminas Sadaunykas

Done as a part of Big Data Module

We used Amazon Fine Food Reviews dataset which contains 568,454 food reviews that Amazon.com users left between October 1999 and October 2012. We decided to select this dataset because it offers a wide range of venues that cuould be explored: from building product recommendation models to sentiment analysis. This dataset has been widely used by professionals and aspiring data scientists, making it largely compelling. The vast length of the dataset, makes it a viable 'playground' for big data model building.

We have decided to solve text classification task. We will try to predict whether review was helpful or unhelpful to other buyers on Amazon, and what words are distinctive for helpful and unhelpful reviews. In order to do so, we have created a new metric called 'Helpfulness_perct' which is a percentage of helpfulness of the review, derived from HelpfulnessNumerator (number of people who voted the review to be helpful) and HelpfulnessDenominator (number of people who 'reviewed' the review). Helpfulness_perct was converted into two binary classes:  1 for  helpful reviews (reviews with Helpfulness_perct>=75%) 0 for unhelpful reviews (reviews with Helpfulness_perct<=25%). 

First, data was preprocessed via data type initialization, outlier treatment, balancing (due to 87% of classes being labeled positive). Then two data analysis pipelines, were implemented. One on single training/validation (80%/20%) split, and single combination of parameters, other on 10-fold cross validation , with parameter grid, consisting of 27 possible parameter combinations. Models were evaluated, using ROC-AUC, precision, recall, f1 scores. Finally, most significant words were found. They were defined by the total sum of IDF.TF values, adjusted for stopwords and common words.

