---
layout: post
title:  Real-time tracking of self-reported symptoms to predict potential COVID-19
date:   2020-05-13
image:  
tags:   [Logistic Regression]
---
I have been self-reporting symptoms using the COVID Symptom Study App from King's College London, so I was interested to see Tim Spector post on Twitter about a new study in Nature using machine learning to create a model combining symptoms to make predictions about probable infection.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Could you predict <a href="https://twitter.com/hashtag/COVID19?src=hash&amp;ref_src=twsrc%5Etfw">#COVID19</a> likelihood without a test? The team <a href="https://twitter.com/Join_ZOE?ref_src=twsrc%5Etfw">@Join_ZOE</a> are innovating with <a href="https://twitter.com/hashtag/MachineLearning?src=hash&amp;ref_src=twsrc%5Etfw">#MachineLearning</a> so that we might be able to: <a href="https://t.co/wvykOsIofi">https://t.co/wvykOsIofi</a> <a href="https://twitter.com/KingsCollegeLon?ref_src=twsrc%5Etfw">@KingsCollegeLon</a> <a href="https://twitter.com/TwinsUKres?ref_src=twsrc%5Etfw">@TwinsUKres</a> <a href="https://twitter.com/GlobalHealthMGH?ref_src=twsrc%5Etfw">@GlobalHealthMGH</a> <a href="https://twitter.com/MassGeneralNews?ref_src=twsrc%5Etfw">@MassGeneralNews</a> <a href="https://twitter.com/AndyChanMD?ref_src=twsrc%5Etfw">@AndyChanMD</a> <a href="https://twitter.com/Join_ZOE?ref_src=twsrc%5Etfw">@Join_ZOE</a> <a href="https://t.co/SiFIwL9lfe">pic.twitter.com/SiFIwL9lfe</a></p>&mdash; tim spector (@timspector) <a href="https://twitter.com/timspector/status/1259789366496542721?ref_src=twsrc%5Etfw">May 11, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Anosmia. Matches previous reports

Variables
including symptoms, hospitalization,  demographic information and pre-existing medical conditions.

Labels
reverse-transcription PCR (RT-PCR) test outcomes,

2,450,569 participants
18,401 had undergone a SARS-CoV-2 test (15,638 UK and 2,763 US participants)
39% positive test

Methods
80:20 train test split in UK cohort
Logistic regression model
5,638 UK and 2,763 US participants
Prediction model = −1.32 − (0.01 × age) + (0.44 × sex) + (1.75 × loss of smell and taste) + (0.31 × severe or significant persistent cough) + (0.49 × severe fatigue) + (0.39 × skipped meals)

The obtained value is then transformed into predicted probability using exp(x)/(1 + exp(x)) transformation followed by assigning cases of predicted COVID-19 for probabilities >0.5 and controls for probabilities <0.5.
