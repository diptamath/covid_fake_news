# COVID19 Fake News Detection in English: 
It is a subtask in the CONSTRAINT-2021 shared task on the hostile post detection.
This subtask focuses on the detection of COVID19-related fake news in English. The sources of data are various social-media platforms such as Twitter, Facebook, Instagram, etc. Given a social media post, the objective of the shared task is to classify it into either fake or real news. 

For example, the following two posts belong to fake and real categories, respectively.
![image](https://user-images.githubusercontent.com/29734492/109349580-338c5c00-789c-11eb-8400-a836364974af.png)


**English Dataset**: https://competitions.codalab.org/competitions/26655 or https://github.com/diptamath/covid_fake_news/tree/main/data

**English dataset paper**: https://arxiv.org/abs/2011.03327

**Link to Competition**: https://constraint-shared-task-2021.github.io/


**Our Approach**:
Our basic approach involves trying out different language models. Such model have achievedstate-of-the-art results on a variety of text classification tasks, which was the basic driving force behind our intuition to use them. We have tried out different language models like XLNet, RoBERTa, XLM-RoBERTa, DeBERTa, ELECTRA and ERNIE2.0. The individual training model files can be obtained [here](https://github.com/diptamath/covid_fake_news/tree/main/training_code).

In order to improve the performance of our classification model, we have tried out various ensemble techniques using various combinations of these models. The combination that has yielded the best result is the one using XLNet, RoBERTa, XLM-RoBERTa, DeBERTa. We have also tried out 2 ensemble techniques: Hard Voting and Soft Voting, where Soft Voting has achieved superior results with the above model combination. The code files related to ensembling can be found at https://github.com/diptamath/covid_fake_news/tree/main/Boosting.
