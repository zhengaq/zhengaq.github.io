---
layout: post
title:  "KDD 2018 Tutorial Accepted! (Tutorial Page)"
date:   2018-04-21 08:00:00 -0400
tags: kdd tutorial 2018
---

### SIGKDD 2018 Tutorial:
<center>
<h1>
Towards Multidimensional Analysis of Text Corpora
</h1>
Jingbo Shang, Chao Zhang, Jiaming Shen, Jiawei Han<br/>
Computer Science Department, University of Illinois at Urbana-Champaign<br/>
Time: <b>August 19, 2018, 1:00PM - 5:00PM</b><br/>
Location: <b>ICC Capital Suite Room 4</b><br/>
</center>

## Slides

[[preliminary version](https://www.dropbox.com/s/0ca5wjwutzrioie/kdd18-tutorial-slides.pdf?dl=0)]

## Abstract

In today's information society, we are soaked with overwhelming amounts of natural-language text data, ranging from news articles and social media posts to research literature, medical records, and corporate reports. 
A grand challenge for data miners is to develop effective and scalable methods to mine such massive unstructured text corpora to discover hidden structures and generate  multidimensional text cubes and structured heterogeneous information networks from which *actionable knowledge* can be generated based on user's need.
 
In this tutorial, we introduce data-driven methods to construct *structured text cubes*
from text corpora of different kinds (especially for massive, domain-specific text corpora).
Such constructed text cubes can further enhance *information networks mining* problems by providing more structure information and guidance.
We focus on methods that are weakly-supervised, domain-independent, and language-agnostic for fast, high-quality text cube and network construction in various domains (e.g., news, computer science, and biomedical sciences). We demonstrate on real datasets including news articles, scientific publications, and product reviews on how text cubes and information networks can be constructed to assist multidimensional analysis of massive text corpora.

## Outline

1. Introduction
    - Motivations & Prior Arts
    - Overview of Multidimensional Text Analysis
2. Phrase Mining and Entity Recognition
    - What are quality phrases?
    - Supervised Methods
        * Noun Phrase Chunking Methods
        * Named Entity Recognition Methods
        * Neural Network Models for Sequence Labeling
        * Parsing-based Methods
        * How to rank entities at the corpus-level?
    - Unsupervised Methods
        * Raw Frequency based Methods
        * Concordance based Methods
        * Topic Model based Methods
        * Comparative Methods
    - Weakly/Distantly Supervised Methods
        * Phrasal Segmentation and its Variants
        * How to leverage distant supervision?
3. Named Entity Recognition
    - What is named entity recognition?
    - Handcrafted Features + Human Supervision
        * Classical Models: Conditional Random Filed
        * Standford NER
        * Twitter NER
    - Automated Features + Human Supervision
        * LSTM-CRF, LSTM-CNN-CRF, ...
        * LM-LSTM-CRF, EMLo, Flair, ...
        * Multi-task learning
    - Automated Features + Distant Supervision
        * AutoEntity, SwellShark, ClusType, Distant-LSTM-CRF, ...
        * FuzzyCRF & AutoNER
4. Taxonomy Construction
    - Cluster-based Taxonomy Construction
        * Hierarchical Topic Modeling
        * General Graphical Model Approach
        * Hierarchical Clustering
    - Instance-based Taxonomy Construction
        * Used Resources Overview
        * Pattern-based Methods
        * Supervised Methods
        * Weakly-supervised Methods
5. Text Cube Construction and Multidimensional Explorations for Effective Knowledge Discovery 
    - Supervised Models
        * Text Classification Models
        * Adaption for Cube Construction
    - Weakly Supervised and Unsupervised Models
        * Weakly Supervised Models
        * Unsupervised Models
    - Cube-based Multidimensional Analysis
        * Statistical Measures Aggregation
        * Phrase-based Cell Summarization
        * Key N-gram based Ranking and Exploration
    - Integrating Text Cube with HIN
        * HIN Embedding
        * Cube-Aided HIN Embedding and Mining
6. Summary and Future Directions
    - Summary of Multidimensional Text Analysis
        * Principles and Techniques
        * AdvantagesandLimitations
        * How to choose a method based on your application?
    - Future Directions

## Presenters

<img align="left" img src="/img/BIO/jingbo.jpg" alt="Drawing" style="width: 200px;margin-right:50px;margin-top:10px"/>**Jingbo Shang**, Ph.D. candidate, Department of Computer Science, Univ. of Illinois at Urbana-Champaign. His research focuses on mining and constructing structured knowledge from massive text corpora. He received Google Global PhD Fellowship in Structured Data and Database Management in 2017. He is the recipient of Computer Science Excellence Scholarship and Grand Prize of Yelp Dataset Challenge in 2015. Mr. Shang has rich experiences in delivering tutorials in major conferences, including SIGMOD 2017, WWW 2017, and SIGKDD 2017.

<img align="left" img src="/img/BIO/chao.jpg" alt="Drawing" style="width: 200px;margin-right:50px;"/>**Chao Zhang**, Ph.D. candidate, Department of Com- puter Science, Univ. of Illinois at Urbana-Champaign. His research focuses on knowledge discovery from social sensing data. He has won the 2015 ECML/PKDD Best Student Paper Runner-up Award, the Microsoft Star of Tomorrow Excellence Award, and the Chiang Chen Overseas Gradu- ate Fellowship. He has given research talks and tutorials on multiple data mining conferences, such as KDD, WWW, VLDB, ICDE, and CIKM.


<img align="left" img src="/img/BIO/jiaming.jpeg" alt="Drawing" style="width: 200px;margin-right:50px;"/>**Jiaming Shen**, Ph.D. candidate, Department of Com- puter Science, Univ. of Illinois at Urbana-Champaign. His research focuses on turning massive unstructured text cor- pora into structured knowledge, for better retrieval, explo- ration, and analysis of domain-specific corpora. He is the recipient of Brian Totty Graduate Fellowship in 2016.
<br/>
<br/>

<img align="left" img src="/img/BIO/hanj.jpg" alt="Drawing" style="width: 200px;margin-right:50px;"/>**Jiawei Han** is Abel Bliss Professor in the Department of Computer Science at the University of Illinois. He has been researching into data mining, information network analysis, and database systems, with over 600 publications. He served as the founding Editor-in-Chief of ACM Transactions on Knowledge Discovery from Data (TKDD). Jiawei has received ACM SIGKDD Innovation Award (2004), IEEE Computer Society Technical Achievement Award (2005), IEEE Computer Society W. Wallace McDowell Award (2009), and Daniel C. Drucker Eminent Faculty Award at UIUC (2011). He is a Fellow of ACM and a Fellow of IEEE. He is currently the Director of Information Network Academic Research Center (INARC) supported by the Network Science-Collaborative Technology Alliance (NS-CTA) program of U.S. Army Research Lab. His co-authored textbook ``Data Mining: Concepts and Techniques'' (Morgan Kaufmann) has been adopted worldwide.