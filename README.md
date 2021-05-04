# COVID19 Fake News Detection in English :mag_right: :eyes:
This repository contains the code for implementing the **"A Heuristic-driven Ensemble Framework for COVID-19 Fake News Detection
" (Accepted at CONSTRAINT Workshop, AAAI 2021)**.

**Preprint**: https://arxiv.org/abs/2101.03545

:bulb: **Please look into our extended work**: https://arxiv.org/pdf/2104.01791.pdf

## Task Description
It is a subtask in the CONSTRAINT-2021 shared task on the hostile post detection.
This subtask focuses on the detection of COVID19-related fake news in English. The sources of data are various social-media platforms such as Twitter, Facebook, Instagram, etc. Given a social media post, the objective of the shared task is to classify it into either fake or real news. 

For example, the following two posts belong to fake and real categories, respectively.
![image](https://user-images.githubusercontent.com/29734492/109349580-338c5c00-789c-11eb-8400-a836364974af.png)


**English Dataset**: https://competitions.codalab.org/competitions/26655 or https://github.com/diptamath/covid_fake_news/tree/main/data

**English dataset paper**: https://arxiv.org/abs/2011.03327

**Link to Competition**: https://constraint-shared-task-2021.github.io/


## Our Approach
Our basic approach involves trying out different language models. Such model have achievedstate-of-the-art results on a variety of text classification tasks, which was the basic driving force behind our intuition to use them. We have tried out different language models like XLNet, RoBERTa, XLM-RoBERTa, DeBERTa, ELECTRA and ERNIE2.0. The individual training model files can be obtained [here](https://github.com/diptamath/covid_fake_news/tree/main/Boosting).

In order to improve the performance of our classification model, we have tried out various ensemble techniques using various combinations of these models. The combination that has yielded the best result is the one using XLNet, RoBERTa, XLM-RoBERTa, DeBERTa. We have created a new [feature set](https://github.com/diptamath/covid_fake_news/blob/main/Boosting/Boosting_Data_Creation.ipynb) using the predictions from different model predictions and saved the resulting feature [data](https://github.com/diptamath/covid_fake_news/tree/main/Boosting/Boosting%20Data). We have also tried out 2 ensemble techniques: Hard Voting and Soft Voting, where Soft Voting has achieved superior results with the above model combination. The code files related to ensembling can be found at this [link](https://github.com/diptamath/covid_fake_news/tree/main/Boosting/Voting).

All our work related to *Heuristic Post-Processing* can be obtained from the [Analysis Folder](https://github.com/diptamath/covid_fake_news/tree/main/Analysis). First, we extract our [username statistics](https://github.com/diptamath/covid_fake_news/blob/main/Analysis/Domain%20Stats%20Extraction.ipynb) and [domain statistics](https://github.com/diptamath/covid_fake_news/blob/main/Analysis/Domain%20Stats%20Extraction.ipynb) from the training data and save them in the [Statistical meta folder](https://github.com/diptamath/covid_fake_news/tree/main/Analysis/Statistical%20meta). We merge our statistical features using [this code](https://github.com/diptamath/covid_fake_news/blob/main/Analysis/Statistical%20Data%20Merge.ipynb). Finally, we [create](https://github.com/diptamath/covid_fake_news/blob/main/Analysis/Post%20Processing/Postproc%20Data%20Creation.ipynb) our [datasets](https://github.com/diptamath/covid_fake_news/tree/main/Analysis/Post%20Processing/data) for post-processing and apply our [post-processing algorithm](https://github.com/diptamath/covid_fake_news/tree/main/Analysis/Post%20Processing) to obtain the final classification result. 

We also perform an ablation study regarding the priority of username handles and URL domains, and also regarding the threshold parameter, which can be accessed [here](https://github.com/diptamath/covid_fake_news/tree/main/Analysis/Ablation%20Study).

## Results
* Our initial approach using ensembling achieved an F-score of **98.31** against the **98.69** F1-score of the leaderboard topper
* Post evaluation, we have been able to improve our solution drastically achieving an F1-score of **98.83**, using Heuristic Post-Processing

## Citation
Please consider citing our paper in your publications if the project helps your research. The BibTeX reference is as follows:
```
@article{das2021heuristic,
title={A Heuristic-driven Ensemble Framework for COVID-19 Fake News Detection},
author={Das, Sourya Dipta and Basak, Ayan and Dutta, Saikat},
journal={arXiv preprint arXiv:2101.03545},
year={2021}

```
