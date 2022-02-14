# 1. Historical Review

- Deep Learning은 AI를 위한 Machine Learning의 한 부분
- Model
  - AlexNet, GoogLeNet, ResNet ..
  - 데이터가 주어졌을 때 원하는 방식으로 바꿔주는 '모델'
  - 모델의 성질에 따라 결과가 다르게 나옴

- Loss
  - loss function: 모델과 데이터가 정해져 있을 때 '어떻게 학습할 지'
  - loss function을 줄이는 것이 반드시 원하는 결과가 나온다는 보장은 아님
    - data에 noise가 많은 경우

- optimization Algorithm
  - 목적은 처음 보는 데이터에서 잘 작동하는 것
  - Dropout, Early stopping, k-fold validation, Weight Decay 등 다양한 기법 함께 적용






- 2012
  - AlexNet
    - paradigm shift
    - 역사적으로 DL이 실성능을 발휘하기 시작
    - 기계학습의 판도가 바뀐 계기
- 2013
  - DQN
    - AlphaGo
- 2014
  - Encoder / Decoder
    - 단어의 sequence를 다른 언어로 변환하는 번역 모델
  - Adam
- 2015
  - Generative Adversarial Network(GAN)
    - Network가 Generator와 discriminator를 만들어 경쟁시킴
  - Residual Networks(ResNet)
    - layer를 너무 깊게 쌓으면 성능이 낮아지는 문제
    - ResNet의 등장으로 한계 깊이를 확장시킴
- 2017
  - Transformer
    - Attention Is All You Need
    - 굉장히 중요한 recurrent network 구조
- 2018
  - Bert
    - fine-tuned NLP models
    - language model 학습
- 2019
  - BIG Language Models(GPT-X)
    - OpenAI
    - 굉장히 많은 parameter
- 2020
  - Selfe-Supervised Learning
    - SimCLR 
    - 한정된 학습 데이터가 주어졌을 때 모델 변형하는 것이 일반적이었음
    - Label을 모르는 data를 학습에 활용하기 위함
