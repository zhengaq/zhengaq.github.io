---
layout: post
title:  "Our KDD 2017 Tutorial on This Sunday!"
date:   2017-08-11 08:00:00 -0400
tags: kdd tutorial 2017
---

### SIGKDD 2017 Tutorial:
<center>
<h1>
Mining Entity-Relation-Attribute Structures from Massive Text Data
</h1>
Jingbo Shang, Xiang Ren, Meng Jiang, Jiawei Han<br/>
Computer Science Department, University of Illinois at Urbana-Champaign<br/>
Time: <b>Aug 13, 2017, Sunday, 8:00AM --- 12:00PM</b><br/>
Location: <b>Room 200C2</b><br/>
</center>

## Abstract

Entity-Relation-Attribute (ERA) structures, forming structured networks between entities and attributes, have demonstrated the flexibility of storing rich information and the effectiveness of gaining insights and knowledge. However, the majority of massive amount of data in the real world are unstructured text, ranging from news articles, social media post, advertisements, to a wide range of textual information from various domains (medical records, corporate reports). Without heavy human annotations and curations, most of existing approaches have difficulties in extracting named entities and their relations as well as typing and organizing knowledge as networks.

## Slides

We provide the *preliminary* versions of slides [here](https://www.dropbox.com/s/k0qruxo0gtspgf1/KDD17-tutorial.pdf?dl=1). Separated slides for each part can be found in the following sections. The *final* version will be updated after the tutorial.


### Introduction
[[slides](https://www.dropbox.com/s/5ca3hh4osfkejyw/KDD17-tutorial-Intro.pdf?dl=1)]

### Part I. Entity Extraction through Phrase Mining 
[[slides](https://www.dropbox.com/s/2bl3rj1fo8n6utq/KDD17-tutorial-part1.pdf?dl=1)][[AutoPhrase](https://github.com/shangjingbo1226/AutoPhrase)][[SegPhrase](https://github.com/shangjingbo1226/SegPhrase)][[ToPMine](http://web.engr.illinois.edu/~elkishk2/code/ToPMine.zip)]

- Jingbo Shang, Jialu Liu, Meng Jiang, Xiang Ren, Clare R Voss, Jiawei Han, "[Automated Phrase Mining from Massive Text Corpora](https://arxiv.org/abs/1702.04457)", submitted to TKDE, under review. 
- Jialu Liu, Jingbo Shang, and Jiawei Han, "[Phrase Mining from Massive Text and Its Applications](http://www.morganclaypool.com/doi/abs/10.2200/S00759ED1V01Y201702DMK013)", Synthesis Lectures on Data Mining and Knowledge Discovery, Morgan & Claypool Publishers, 2017.
- Jialu Liu, Jingbo Shang, Chi Wang, Xiang Ren, Jiawei Han, "[Mining Quality Phrases from Massive Text Corpora](http://hanj.cs.illinois.edu/pdf/sigmod15_jliu.pdf)",  in Proc. of 2015 ACM SIGMOD Int. Conf. on Management of Data (SIGMOD'15),  Melbourne, Australia, May 2015 (**<span style="color:red">won Grand Prize in Yelp Dataset Challenge, 2015</span>**)
- Ahmed El-Kishky, Yanglei Song, Chi Wang, Clare R. Voss, and Jiawei Han, "[Scalable Topical Phrase Mining from Text Corpora](http://hanj.cs.illinois.edu/pdf/vldb15_ael-kishky.pdf)", PVLDB 8(3): 305 - 316, 2015. Also, in Proc. 2015 Int. Conf. on Very Large Data Bases (VLDB'15), Kohala Coast, Hawaii, Sept. 2015.

### Part II. Typing Entities and Relations
[[slides](https://www.dropbox.com/s/33brgzj1vzt4bc1/KDD17-tutorial-part2.pdf?dl=1)][[ReHession](https://github.com/LiyuanLucasLiu/ReHession)][[CoType](https://github.com/shanzhenren/CoType)][[AFET](https://github.com/shanzhenren/AFET)][[PLE](https://github.com/shanzhenren/PLE)][[ClusType](https://github.com/shanzhenren/ClusType)]

- Liyuan Liu, Xiang Ren, Qi Zhu, Shi Zhi, Huan Gui, Heng Ji and Jiawei Han, "[Heterogeneous Supervision for Relation Extraction: A Representation Learning Approach](http://hanj.cs.illinois.edu/pdf/emnlp17_lliu.pdf)",  in Proc. of 2017 Conf. on  Empirical Methods in Natural Language Processing (EMNLP'17), Copenhagen, Denmark, Sept. 2017
- Xiang Ren, Zeqiu Wu, Wenqi He, Meng Qu, Clare Voss, Heng Ji, Tarek Abdelzaher and Jiawei Han, "[CoType: Joint Extraction of Typed Entities and Relations with Knowledge Bases](http://hanj.cs.illinois.edu/pdf/www17_xren.pdf)", in Proc. of 2017 World-Wide Web Conf. (WWW'17), Perth, Australia, Apr. 2017.
- Xiang Ren, Wenqi He, Meng Qu, Lifu Huang, Heng Ji, and Jiawei Han, "[AFET: Automatic Fine-Grained Entity Typing by Hierarchical Partial-Label Embedding](http://hanj.cs.illinois.edu/pdf/emnlp16_xren.pdf)", in Proc. of 2016 Conf. on Empirical Methods in Natural Language Processing (EMNLP'16), Austin, TX, Nov. 2016
- Xiang Ren,  Wenqi He,  Meng Qu, Clare R. Voss, Heng Ji, Jiawei Han, "[Label Noise Reduction in Entity Typing by Heterogeneous Partial-Label Embedding](http://hanj.cs.illinois.edu/pdf/kdd16_xren.pdf)", in Proc. of 2016 ACM SIGKDD Conf. on Knowledge Discovery and Data Mining (KDD'16), San Francisco, CA, Aug. 2016
- Xiang Ren, Ahmed El-Kishky, Chi Wang, Fangbo Tao, Clare R. Voss, Heng Ji, Jiawei Han, "[ClusType: Effective Entity Recognition and Typing by Relation Phrase-Based Clustering](http://hanj.cs.illinois.edu/pdf/kdd15_xren.pdf)", in Proc. of 2015 ACM SIGKDD Int. Conf. on Knowledge Discovery and Data Mining (KDD'15), Sydney, Australia, Aug. 2015

### Part III. Pattern-based Methods for Attribute Discovery
[[slides](https://www.dropbox.com/s/92rie6xniacm6gj/KDD17-tutorial-part3.pdf?dl=1)][[MetaPAD](https://github.com/mjiang89/MetaPAD)]

- Meng Jiang, Jingbo Shang, Taylor Cassidy, Xiang Ren, Lance Kaplan, Timothy Hanratty and Jiawei Han, "[MetaPAD: Meta Patten Discovery from Massive Text Corpora](http://hanj.cs.illinois.edu/pdf/kdd17_mjiang.pdf)", in Proc. of 2017 ACM SIGKDD Int. Conf. on Knowledge Discovery and Data Mining (KDD'17), Halifax, Nova Scotia, Canada, Aug. 2017

### Part IV. Structure Discovery from Text: Application Exploration
[[slides](https://www.dropbox.com/s/22lrfr3tabwm37c/KDD17-tutorial-part4.pdf?dl=1)][[SetExpan](https://github.com/mickeystroller/SetExpan)][[DPE](https://github.com/mnqu/DPE)][[LAKI](https://github.com/remenberl/Latent-Keyphrase-Inference)]

- Huan Gui, Qi Zhu, Liyuan Liu, Aston Zhang, and Jiawei Han, "Expert Finding in Heterogeneous BibliographicNetworks with Locally-trained Embeddings", submitted for publication
- Jiaming Shen, Zeqiu Wu, Dongming Lei, Jingbo Shang, Xiang Ren, Jiawei Han, "[SetExpan: Corpus-based Set Expansion via Context Feature Selection and Rank Ensemble](http://hanj.cs.illinois.edu/pdf/ecmlkdd17_jshen.pdf)",  in Proc. of 2017 European Conf. on Machine Learning and Principles and Practice of Knowledge Discovery in Databases (ECMLPKDD'17), Skopje, Macedonia, Sept. 2017
- Meng Qu, Xiang Ren and Jiawei Han, "[Automatic Synonym Discovery with Knowledge Bases](http://hanj.cs.illinois.edu/pdf/kdd17_mqu.pdf)", in Proc. of 2017 ACM SIGKDD Int. Conf. on Knowledge Discovery and Data Mining (KDD'17), Halifax, Nova Scotia, Canada, Aug. 2017
- Fangbo Tao, Honglei Zhuang, Chi Wang Yu, Qi Wang, Taylor Cassidy, Lance Kaplan, Clare Voss, Jiawei Han, "[Multi-Dimensional, Phrase-Based Summarization in Text Cubes](http://hanj.cs.illinois.edu/pdf/deb16_ftao.pdf)", Data Eng. Bulletin 39(3), Sept. 2016, pp. 74-84.
- Jialu Liu, Xiang Ren, Jingbo Shang, Taylor Cassidy, Clare Voss and Jiawei Han, "[Representing Documents via Latent Keyphrase Inference](http://hanj.cs.illinois.edu/pdf/www16_jliu.pdf)", in Proc. of 2016 Int. World-Wide Web Conf. (WWW'16), Montreal, Canada, April 2016

### Summary and Future Directions
[[slides](https://www.dropbox.com/s/ujunlspj0ahi54b/KDD17-tutorial-Summary.pdf?dl=0)]


## Presenters

<img align="left" img src="/img/BIO/jingbo.jpg" alt="Drawing" style="width: 200px;margin-right:50px;"/>
**Jingbo Shang** is a Ph.D. student in Department of Computer Science, University of Illinois at Urbana-Champaign. His research focuses on mining and constructing structured knowledge from massive text corpora. He is the recipient of Computer Science Excellence Scholarship and Grand Prize of Yelp Dataset Challenge in 2015. He received Google PhD Fellowship in Structured Data and Database Management in 2017.

<img align="left" img src="/img/BIO/xiangren.jpg" alt="Drawing" style="width: 200px;margin-right:50px;"/>**Xiang Ren** is an incoming assistant professor in the Department of Computer Science at USC and a member of the USC Machine Learning Center. Currently, he is a visiting researcher at Stanford University, and a PhD candidate of Computer Science at UIUC where he works with Jiawei Han. Xiang’s research develops data-driven and machine learning methods for turning unstructured text data into machine-actionable structures. More broadly, his research interests span data mining, machine learning, and natural language processing, with a focus on making sense of big text data. His research has been recognized with several prestigious awards including a Google PhD Fellowship, a Yahoo!-DAIS Research Excellence Award, a WWW 2017 Outstanding Reviewer Award, a Yelp Dataset Challenge award and a C. W. Gear Outstanding Graduate Student Award from CS@Illinois. Technologies he developed has been transferred to US Army Research Lab, National Institute of Health, Microsoft, Yelp and TripAdvisor.

<img align="left" img src="/img/BIO/jiangm.jpg" alt="Drawing" style="width: 200px;margin-right:50px;"/>**Meng Jiang** received his B.E. degree and Ph.D. degree in 2010 and 2015 at the Department of Computer Science and Technology in Tsinghua University. He is now an assistant professor in the Department of Computer Science and Engineering at the University of Notre Dame. He worked as a postdoctoral research associate at University of Illinois at Urbana-Champaign from 2015 to 2017. He has published over 20 papers on behavior modeling and information extraction in top conferences and journals of the relevant field such as IEEE TKDE, ACM SIGKDD, AAAI, ACM CIKM and IEEE ICDM. He also has delivered six tutorials on the same topics in major conferences. He got the best paper finalist in ACM SIGKDD 2014.

<img align="left" img src="/img/BIO/hanj.jpg" alt="Drawing" style="width: 200px;margin-right:50px;"/>**Jiawei Han** is Abel Bliss Professor in the Department of Computer Science at the University of Illinois. He has been researching into data mining, information network analysis, and database systems, with over 600 publications. He served as the founding Editor-in-Chief of ACM Transactions on Knowledge Discovery from Data (TKDD). Jiawei has received ACM SIGKDD Innovation Award (2004), IEEE Computer Society Technical Achievement Award (2005), IEEE Computer Society W. Wallace McDowell Award (2009), and Daniel C. Drucker Eminent Faculty Award at UIUC (2011). He is a Fellow of ACM and a Fellow of IEEE. He is currently the Director of Information Network Academic Research Center (INARC) supported by the Network Science-Collaborative Technology Alliance (NS-CTA) program of U.S. Army Research Lab. His co-authored textbook ``Data Mining: Concepts and Techniques'' (Morgan Kaufmann) has been adopted worldwide.
