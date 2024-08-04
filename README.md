# NSL-KDD Dataset: Analyzing Network Packets for Intrusion Detection

## Introduction
Most Intrusion Detection Systems (IDS) while detecting attacks also flags benign traffic as malicious. This poses a number of challenges:
- 'Operational Overhead' It requires resources to process and classify the flagged traffic 
- 'Alert Fatigue'(this goes for both human analysts and machine learning models exposed to too many false positives)

A common challenge with supervised learning is finding high-quality labeled data for training and testing models. While labeled pictures of cats are easy to obtain, labeled data from data breaches are much harder to come by. Options for labeled datasets for network traffic are somewhat limited, making the KDD dataset popular, especially for training and exploration. However, this also means that models trained on these datasets share similar characteristics.

Various models for IDS's using machine learning and deep learning neural networks have been proposed and implemented for research purposes by Sapre Et al. in [2] and Mijalkovic et al. in [3]  (the industry seems a bit closed regarding which datasets and models are implemented in products). The conclusuion is generally that the models reflect composition of the traffic and models are good at picking up DoS attacks and port scanning which happens a lot and less good at detecting foothold attempts and privilege escalation attacks .    

## Scope
Establish an overview of various machine learning models for analysis of networking traffic and investigate the relation between false positives and false negatives using confusion matrices. 
A baseline model will be adapted or established based a survey of various machine learning classifiers using following steps:
- Data Preparation
- Classification reduction
- Scaling to truncate large variations in magnitude for each feature
- Evaluate classifiers
- Paramter Study on False Poitives vs False Negatives (on a perfomant model based on previous step)
  
## Dataset
The NSL-KDD dataset is a subset of the KDDCup99 dataset, where repeated data was removed. The KDECup99 data were heavily skewed towards DoS Attacks causing arificilly high model performance (there was too much easily identifiable data in the set).

### Classification Reduction:  
Most machine learning models uses either binary classification (attack or not) or full classification (all classes). [1] suggests reducing it to 4 classes when using the NSL-KDD dataset, as it contains a lot of attack labels, some of which do not occur both in the proposed training and evaluation data.