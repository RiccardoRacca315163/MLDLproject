# Project Title:
Ego-centric Videos and Natural Language Queries

# Authors:
Leone Aurora,
Narese Michele,
Racca Riccardo


## Table of Contents
- [Disclaim 1](#Disclaim1)
- [Disclaim 2](#Disclaim2)
- [Dataset](#Dataset) 
- [Architectures](#Architectures)
- [Evaluation & Comparison](#evaluation&comparison)
- [Ensemble](#Ensemble)
- [Results](#results) 
- [Contacts](#Contacts)

### Disclaim 1
All outputs that are not necessary for understanding the code have been removed for readability purposes, to optimize space, and to improve rendering on GitHub. If you want to see the complete Colab with all outputs, it is available here: https://colab.research.google.com/drive/1XxMJic6YQY6c4x80FzJWw7JasdRDxW44#scrollTo=cpWsqiln5ZFg . Especially for video QA, it is recommended to view it by opening the Google Colab with the given link, or to refer to the QA results table

### Disclaim 2
The models implemented can be found in the following GitHub repository: https://github.com/Auroraleone/episodic-memory_Auro

### Dataset
The training process and the analysis are conducted on the NLQ Episodic Memory dataset which consists of a set of 1,659 clips with an average length of 8.2 minutes. They are already split into training, validation and test set.
Related statistics can be found in the: StatsForData.ipynb

### Architectures
The architectures that will be used and fine-tuned will be VSLNet and VSLBase. For the actual implementation code please see disclaimer 2 above


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
