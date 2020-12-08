---
layout: post
title:  "Linear Regression"
summary: Linear Regression
author: Jun
date: '2020-07-24 14:35:23 +0530'
category: ML
use_math: true
thumbnail: /assets/img/thumbnail/linear_regression.png
---

## 선형 회귀(Linear Regression)  
&nbsp;
#### 1) 선형 회귀란?

-> 선형 회귀를 쉽게 이야기를 하면 예측선을 가장 잘 긋는 것!

&nbsp;

가설을 세우고 가설에 대해 영향을 주는 정보를 통해서 예측하는 방정식을 만들 수 있다.

영향을 주는 값을 x, 즉 독립변수라고 하고

영향을 받는 값을 y, 즉 종속변수라고 한다.

선형 회귀는 독립 변수를 사용해서 종속 변수의 움직임을 예측 하고 설명하는 것이다.

독립변수는 2개 이상이 될수 있는데 독립변수가 1개일 경우에는 단순 선형회귀(simple linear regression)라고 하고

2개 이상일 경우에는 다중 선형 회귀(multiple linear regression)라고 한다.

&nbsp;

#### 2) 예측선 공식

&nbsp;

기본적으로 선형 회귀 공식은 다음과 같다

> $ y = ax + b $

a는 직선의 기울기이며 값은 $ a={y값의 증가량 \over x값의 증가량} $ 이고,

b는 y축을 지나가는 y절편, 즉 x에 0을 넣었을 시의 값이다.
