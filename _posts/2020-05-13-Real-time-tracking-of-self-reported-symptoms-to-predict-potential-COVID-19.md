---
layout: post
title:  Real-time tracking of self-reported symptoms to predict potential COVID-19
date:   2020-05-13
image:  symptom_tracker.png
tags:   [Logistic Regression]
---
I have been self-reporting symptoms using the COVID Symptom Study App from King's College London, so I was interested to see Tim Spector post on Twitter about a new study in Nature using machine learning to create a model combining symptoms to make predictions about probable infection.

<blockquote class="twitter-tweet" align='center'><p lang="en" dir="ltr">Could you predict <a href="https://twitter.com/hashtag/COVID19?src=hash&amp;ref_src=twsrc%5Etfw">#COVID19</a> likelihood without a test? The team <a href="https://twitter.com/Join_ZOE?ref_src=twsrc%5Etfw">@Join_ZOE</a> are innovating with <a href="https://twitter.com/hashtag/MachineLearning?src=hash&amp;ref_src=twsrc%5Etfw">#MachineLearning</a> so that we might be able to: <a href="https://t.co/wvykOsIofi">https://t.co/wvykOsIofi</a> <a href="https://twitter.com/KingsCollegeLon?ref_src=twsrc%5Etfw">@KingsCollegeLon</a> <a href="https://twitter.com/TwinsUKres?ref_src=twsrc%5Etfw">@TwinsUKres</a> <a href="https://twitter.com/GlobalHealthMGH?ref_src=twsrc%5Etfw">@GlobalHealthMGH</a> <a href="https://twitter.com/MassGeneralNews?ref_src=twsrc%5Etfw">@MassGeneralNews</a> <a href="https://twitter.com/AndyChanMD?ref_src=twsrc%5Etfw">@AndyChanMD</a> <a href="https://twitter.com/Join_ZOE?ref_src=twsrc%5Etfw">@Join_ZOE</a> <a href="https://t.co/SiFIwL9lfe">pic.twitter.com/SiFIwL9lfe</a></p>&mdash; tim spector (@timspector) <a href="https://twitter.com/timspector/status/1259789366496542721?ref_src=twsrc%5Etfw">May 11, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


### Methods and Results

The study has data from 2,450,569 participants using the app.  Of these 18,401 had undergone a SARS-CoV-2 test (15,638 in the UK cohort and 2,763 in the US).  39% of participants who had a test were positive.

Before doing any machine learning, the association of loss of smell (anosmia) and taste was investigated.  After accounting for age, sex and BMI, presence of anosmia was found to have an odds ratio of 6.74 (95% confidence interval 6.31–7.21) for having coronavirus.  This matched previous reports of an association.  Interestingly, as more of these reports had appeared in the media, the association in the UK became stronger, presumably as the population became more aware of this as a potential symptom (although the finding was not replicated in the UK).

For predictive modelling, the UK Cohort was randomly split 80:20 into training and test sets.
Logistic regression was used to model the probability of reverse-transcription PCR (RT-PCR) test outcomes.  The prediction model derived was:
>Prediction model = −1.32 − (0.01 × age) + (0.44 × sex) + (1.75 × loss of smell and taste) + (0.31 × severe or significant persistent cough) + (0.49 × severe fatigue) + (0.39 × skipped meals)

The obtained value is then transformed into predicted probability using exp(x)/(1 + exp(x)).  Predicted COVID-19 probabilities >0.5 are assigned cases, and probabilities <0.5 as controls.

With this threshold, a positive test has a probability of 0.69 (0.66–0.71) of being a true positive, while the negative predictive value is 0.75 (0.73–0.77).


### Discussion
The small proportion of the overall participants who have had a test are not a random selection, but are likely to be more unwell individuals.  As such, the prevalence of infection in the untested population (even those with symptoms) is likely to be a lot lower.
The model used is a very simple logistic regression model with 4 binary variables, 1 continuous variable (age) and a bias.
