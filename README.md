# Project Title:
Ego-centric Videos and Natural Language Queries

# Authors:
Leone Aurora,
Narese Michele,
Racca Riccardo


## Table of Contents
- [Disclaim](#Disclaim1)
- [Disclaim](#Disclaim2)
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



### Contacts
Leone Aurora, s334258@studenti.polito.it -
Narese Michele, s329892@studenti.polito.it -
Racca Riccardo, s315163@studenti.polito.it 
