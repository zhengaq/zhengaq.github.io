---
layout: post
title:  "KDD 2019 Tutorial Accepted! (Tutorial Page)"
date:   2019-04-22 15:00:00 -0400
tags: kdd tutorial 2019
---

### SIGKDD 2019 Tutorial:
<center>
<h1>
T17: Constructing and Mining Heterogeneous Information Networks from Massive Text
</h1>
Jingbo Shang, Jiaming Shen, Liyuan Liu, Jiawei Han<br/>
Computer Science Department, University of Illinois at Urbana-Champaign<br/>
Time: <b>1:00PM - 5:00PM, Aug 4, 2019</b><br/>
Location: <b>Kahtnu 2-Level 2, Dena’ina</b><br/>
</center>

## Slides

[preliminary version](https://www.dropbox.com/s/asqpts97hz7zmaf/kdd19-slides-preliminary-version.pdf?dl=0)

## Abstract

Real-world data exists largely in the form of unstructured texts. A grand challenge on data mining research is to develop effective and scalable methods that may transform *unstructured text* into *structured knowledge*. Based on our vision, it is highly beneficial to transform such text into *structured heterogeneous information networks*, on which *actionable knowledge* can be generated based on the user's need.

In this tutorial, we provide a comprehensive overview on recent research and development in this direction.  First, we introduce a series of effective methods that construct *heterogeneous information networks* from massive, domain-specific text corpora. Then we discuss methods that mine such text-rich networks based on the user's need. Specifically, we focus on scalable, effective, weakly supervised, language-agnostic methods that work on various kinds of text. We further demonstrate, on real datasets (including news articles, scientific publications, and product reviews), how information networks can be constructed and how they can assist further exploratory analysis.

## Outline

1. Introduction
    - Motivations: Why construction and mining of heterogeneous information networks from massive text?
    - An overview of network construction from massive texts
    - An overview on exploration of applications of constructed networks
2. Phrase Mining
    - Why phrase mining and how to define high-quality phrases?
    - Supervised Methods
        * Noun Phrase Chunking Methods
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
    - System demos and software introduction
        * A multilingual phrase mining system which integrates [AutoPhrase](https://github.com/shangjingbo1226/AutoPhrase), [SegPhrase](https://github.com/shangjingbo1226/SegPhrase), and TopMine together and supports phrase mining in multiple languages (e.g., English, Spanish, Chinese, Arabic, and Japanese).
3. Information Extraction: Entity, Attribute, and Relation
    - What is Named Entity Recognition (NER)?
    - Traditional Supervised Methods
        * CorNLL03 shared task
        * Sequence labeling framework
        * Conditional random fields
        * Handcrafted features
    - Modern End-to-End Neural Models
        * Bidirectional LSTM-based models
        * Language model and contextualized representations
        * Raw-to-end models
    - Distantly Supervised Models
        * Data programming for entity typing
        * Learning from domain-specific dictionaries
    - Meta-Pattern based Information Extraction
        * Meta-Pattern Discovery
        * Meta-Pattern-Enhanced NER
    - System Demos and Software
        * Named entity recognition inference Python package: [LightNER](https://github.com/LiyuanLucasLiu/LightNER). This module helps users easily apply the pre-trained NER models to their own corpus in an efficient and portable manner.
4. Taxonomy Construction
    - Taxonomy Basics
        * Taxonomy Definition
        * Taxonomy Application
        * Taxonomy Construction Pipeline
    - Instance-based Taxonomy Construction
        * Used Resources Overview
        * Pattern-based Methods
        * Supervised Methods
        * Weakly-supervised Methods
    - Cluster-based Taxonomy Construction
        * Hierarchical Topic Modeling
        * General Graphical Model Approach
        * Hierarchical Clustering
5. Mining Heterogeneous Information Networks (Structured Analysis)
    - Basic Analysis System Demo
        * AutoNet system: It constructs a huge structured network from the PubMed papers (title & abstract) and supports online construction (new documents) and intelligent exploration (search).
    - Summarization
        * Graph-based Summarization
        * Clustering and Ranking for Summarization
    - Meta-Path Guided Exploration
        * Meta-Path based Similarity
        * Meta-Path guided Node Embedding
    - Link Prediction
        * Task-Guided Node Embedding
        * Link Enrichment in Constructed Networks
6. Summary and Future Directions
    - Summary
        * Principles and Techniques
        * AdvantagesandLimitations
    - Challenges and Future Research Directions
    - Interaction with the Audience
        * How to construct and mine heterogeneous information networks based on your text data and application need?
7. Question Answering and Discussions

## Presenters

<img align="left" img src="/img/BIO/jingbo.jpg" alt="Drawing" style="width: 200px;margin-right:50px;margin-top:10px"/>**Jingbo Shang**, Ph.D. candidate, Department of Computer Science, Univ. of Illinois at Urbana-Champaign. His research focuses on mining and constructing structured knowledge from massive text corpora with minimum human effort. His research has been recognized by multiple prestigious awards, including Grand Prize of Yelp Dataset Challenge (2015), Google PhD Fellowships (2017-2019) on Structured Data and Database Management. Mr. Shang has rich experiences in delivering tutorials in major conferences (SIGMOD'17, WWW'17, SIGKDD'17, and SIGKDD'18).


<img align="left" img src="/img/BIO/jiaming.jpeg" alt="Drawing" style="width: 200px;margin-right:50px;"/>**Jiaming Shen**, Ph.D. candidate, Department of Com- puter Science, Univ. of Illinois at Urbana-Champaign. His research focuses on turning massive unstructured text cor- pora into structured knowledge, for better retrieval, explo- ration, and analysis of domain-specific corpora. He is the recipient of Brian Totty Graduate Fellowship in 2016.
<br/>
<br/>

<img align="left" img src="/img/BIO/liyuan.jpg" alt="Drawing" style="width: 200px;margin-right:50px;"/>**Liyuan Liu**, Ph.D. candidate, Department of Computer Science, Univ. of Illinois at Urbana-Champaign. His research interest mainly lies in data-driven text mining, including contextualized representations with language modeling, weak and heterogeneous supervision.

<br/>
<br/>

<img align="left" img src="/img/BIO/hanj.jpg" alt="Drawing" style="width: 200px;margin-right:50px;"/>**Jiawei Han** is Abel Bliss Professor in the Department of Computer Science at the University of Illinois. He has been researching into data mining, information network analysis, and database systems, with over 600 publications. He served as the founding Editor-in-Chief of ACM Transactions on Knowledge Discovery from Data (TKDD). Jiawei has received ACM SIGKDD Innovation Award (2004), IEEE Computer Society Technical Achievement Award (2005), IEEE Computer Society W. Wallace McDowell Award (2009), and Daniel C. Drucker Eminent Faculty Award at UIUC (2011). He is a Fellow of ACM and a Fellow of IEEE. He is currently the Director of Information Network Academic Research Center (INARC) supported by the Network Science-Collaborative Technology Alliance (NS-CTA) program of U.S. Army Research Lab. His co-authored textbook ``Data Mining: Concepts and Techniques'' (Morgan Kaufmann) has been adopted worldwide.