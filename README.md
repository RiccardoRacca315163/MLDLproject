# Project Title:
Ego-centric Videos and Natural Language Queries

# Authors:
Leone Aurora,
Narese Michele,
Racca Riccardo


## Table of Contents
- [Disclaim](#Disclaim1)
- [Dataset](#Dataset) 
- [Architectures](#Architectures)
- [Evaluation&Comparison](#evaluation&comparison)
- [Ensemble](#Ensemble)
- [Results](#results) 
- [Contacts](#Contacts)

### Disclaim 1
All outputs that are not necessary for understanding the code have been removed for readability purposes, to optimize space, and to improve rendering on GitHub. If you want to see the complete Colab with all outputs, it is available here: (link). Especially for video QA, it is recommended to view it by opening the Google Colab with the given link, or to refer to the QA results table

### Disclaim 2
The models implemented can be found in the following GitHub repository: https://github.com/Auroraleone/episodic-memory_Auro

### Dataset
The training process and the analysis are conducted on the NLQ Episodic Memory dataset which consists of a set of 1,659 clips with an average length of 8.2 minutes. They are already split into training, validation and test set.
Related statistics can be found in the: StatsForData.ipynb

### Architectures
The architectures that will be used and fine-tuned will be VSLNet and VSLBase. The reason why they were adopted is that VSLNet and VSLBase are specifically designed for the NLQ task. Specifically, to better understand the impact of the QGH module, it has been removed from VSLnet, following the construction of VSLBase architecture. Both models figure two feature extractors: one used for videos and one for text data to obtain word embedding. Shown in: Training.ipynb


### Evaluation and Comparison
Evaluation and comparison are fully reported in: Evaluation&Comparison.ipynb


### Ensemble
An "ensemble" method is proposed, where the results of different models are convexly combined to obtain a more accurate one, aiming to exploit the computational effort needed to train and evaluate the models in the selection phase. Everything is detailly shown in: Ensemble.ipynb

### Results
Directly delivered in: QAResults.pdf



### Contacts
Leone Aurora, s334258@studenti.polito.it 
Narese Michele, s329892@studenti.polito.it 
Racca Riccardo, s315163@studenti.polito.it 
