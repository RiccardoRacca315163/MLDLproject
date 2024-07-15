# Project Title:
Ego-centric Videos and Natural Language Queries

# Authors:
Leone Aurora,
Narese Michele,
Racca Riccardo


## Table of Contents
- [Abstract](#Abstract)
- [Introduction](#Introduction) 
- [Task](#Prerequisites) 
- [Dataset](#Dataset) 
- [Architectures](#Architectures)
- [WordEmbedding](#WordEmbedding)
- [SyntethicRepresentation](#syntethicRepresentation)
- [Evaluation&Comparison](#evaluation&comparison)
- [QApipeline](#QApipeline)
- [Ensemble](#Ensemble)
- [Disclaim](#Disclaim)
- [Results](#results) 
- [Contacts](#Contacts)


### Abstract
This report aims to tackle the task of action recognition and identification in egocentric videos, that is, identifying a timeframe where the answer to a natural language query can be seen within the provided video, and then exploiting this knowledge in order to build a textual answer. Different architectures are implemented and trained on various pre-extracted features of Ego4D dataset, whilst multiple metrics are used to compare the performance of different models with the benchmark, in order to obtain a robust model that is employable in the next step. Subsequently, a video question-answering pipeline is built by leveraging the results provided by the previous architectures and using them as input for a VLM (Video Language Model), to not only retrieve a time interval but also provide a textual answer. Finally, an ensemble method is introduced to obtain better predictions while exploiting the, partially wasted, computational effort needed to build and compare different models.

### Introduction
Videos taken from a human point of view have lately become more and more popular as they are employed in many different fields such as wearable computing, augmented reality and human-computer interaction. As a consequence, the urge of developing models, that are able to tackle this category of problems, led to the need of collecting large-scale data in order to better capture the nature of this task. For this reason, datasets such as EpicKitchens and Ego4D were created. Many tasks are related to egocentric video understanding such as action anticipation, cross-modal retrieval or action recognition (both fully and weakly supervised)

### Task
This paper focuses on the challenge of Ego4D NLQ benchmark, which is defined as a temporal segment prediction task where, given a video clip and a text query in natural language, the model is asked to predict the temporal segment where the answer is visible or deducible

### Dataset
The training process and the analysis are conducted on the NLQ Episodic Memory dataset which consists of a set of 1,659 clips with an average length of 8.2 minutes. They are already split into training, validation and test set.
Related statistics can be found in the: StatsForData.ipynb

### Architectures
The architectures that will be used and fine-tuned will be VSLNet and VSLBase. The reason why they were adopted is that VSLNet and VSLBase are specifically designed for the NLQ task. Specifically, to better understand the impact of the QGH module, it has been removed from VSLnet, following the construction of VSLBase architecture. Both models figure two feature extractors: one used for videos and one for text data to obtain word embedding. Shown in: Training.ipynb

### Word embedding
Two popular techniques in natural language processing (NLP) for word embeddings and contextual understanding of language are used, namely: Bert and GloVe. The analysis of their usage, the aim is to distinguish the subtle differences in results obtained using GloVe embeddings compared to BERT embeddings within the VSLNet architecture. Shown in: Training.ipynb

### Syntethic representation of videos
Since training models on video datasets is often impractical due to computational requirements, it’s imper- ative to use a ”synthetic representation” of the videos present in Ego4d dataset. For this reason, many video-language models have been pre-trained on the full dataset in order to extract features that serve as compact representations of the video itself.
This project utilizes features pre-extracted by Omnivore and EgoVLP. Shown in: Training.ipynb

### Evaluation and Comparison
Evaluation and comparison are fully reported in: Evaluation&Comparison.ipynb

### QA pipeline
The NLQ challenge aims at identifying a temporal interval where the answer of a NLQ is clearly visible. Many VLM models tend to struggle when dealing with long and unstructured videos, especially in terms of computational effort due to the large number of video tokens that are, for the majority, unrelated to the answer. Acknowledging these issues necessitated finding a way to overcome them by leveraging both models to create a unified pipeline in order to provide a unique model that, starting from a long and unstructured video and an input query, is able to produce a textual answer (along with the temporal interval associated if needed). Starting from a clip from the NLQ challenge in Ego4d where the (almost) correct video interval is retrieved by the best model obtained, the original video is taken and trimmed in correspondence with the predicted interval. The output segment is then fed to Video-LLaVa in order to retrieve the answer desired. Shown in: VideoQA.ipynb

### Ensemble
An "ensemble" method is proposed, where the results of different models are convexly combined to obtain a more accurate one, aiming to exploit the computational effort needed to train and evaluate the models in the selection phase. Everything is detailly shown in: Ensemble.ipynb

### Results
Directly delivered in: QAResults.pdf

### Disclaim



### Contacts
Leone Aurora, s334258@studenti.polito.it -
Narese Michele, s329892@studenti.polito.it -
Racca Riccardo, s315163@studenti.polito.it 
