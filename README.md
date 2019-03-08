# Text Analysis Basics for Sociology and Demography

This repo includes an overview of basic text analysis methods at the word, document, and global level. The goal is to introduce these methods with usable examples that can be easily applied with modification to demographic and sociological questions.

## Methods

Obviously the question you're interested and the data you have will drive your choice of methods. I present methods that I've used in the past. I like using R for topic modeling and keyword prevalence, while I prefer python for n-gram regression (because sklearn rocks). 

### R tidytext and STM

There are lots of good tidytext demos, including [this awesome textbook](https://www.tidytextmining.com), so I don't offer that. Instead, the first part of `text4demog.Rmd` works through tokenization only. The result of the code is a decidely un-tidy format. Too bad. 

There are also other places where you can learn to use STM, or structural topic models. Their [development page](https://www.structuraltopicmodel.com) includes links to lots of good stuff and their [easy-to-follow vingette](https://github.com/bstewart/stm/blob/master/inst/doc/stmVignette.pdf?raw=true).   

The code included here uses STM to look at the relationship between Craigslist rental discourse and rent. The code fires up a topic model on the included Craigslist data and works through some simple exploratory analysis, including (what I think is) an improved plot.   


### Python sklearn and gensim

On the python side of things, you get a jupyter notebook, `text4demog.ipynb` which does some keyword prevalence analysis, with plots to show how covariates vary with particular keywords. That's mostly exploratory. Then there's a bit working through some examples of simple machine learning on texts, looking for words associated with above-median White neighborhoods in the Craigslist data and in tweets marked as 'empowering'.

Python's `gensim` module offers lots of cool text analysis tools, including a very good LDA topic modeling implementation. In this example, I show how to fit `gensim`'s word embeddings implementation, `word2vec` to a set of data in memory. Very slight modifications will let you use this same workflow for data that won't fit in memory (another area where Python outshines R).


## Data

Two small datasets are included as examples. The first, `data/seattle_sample_demog.csv` is a sample of 5000 Craigslist listings for housing rentals posted in 2017 and 2018 in the Seattle area. The second, `data/responses_3_6.csv` is a dataset of tweets with racial content hand-coded by Amazon mturkers. Both examples are subsets of data collected by research teams I am a part of and include data that was either publicly available or anonymized. Contact ikennedy@uw.edu for more information on the data.
