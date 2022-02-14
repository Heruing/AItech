# 8. Sequential Models - Transformer

기본적으로 sequential data를 다루는 방법론

- sequential model
  - 중간에 빠지거나 잘린 data를 다루기 굉장히 어려움
  - transformer의 등장

**Transformer**

- RNN이 재귀적으로 돌아가던 것과 달리, attention이라는 구조를 사용한 구조

- sequential한 data를 처리하고 encoding하는 방법

  - nmt 문제에 한정되지 않음
  - 이미지 분류 등에 사용 가능

- sequence to sequence

- RNN에서는 n개의 단어가 들어가면, n번의 재귀적인 절차 수행

- encoder를 통해 한번에 n개의 단어를 처리

- Encoder

  - self-attention
    - encoder와 decoder에 모두 존재
    - input이 처리될 때 나머지 input도 고려하는 dependency존재
  - feed forward neural network
    - independent

- Query, Key, Value

  - 단어가 하나 들어오면 각 3개의 vector를 생성

    - query와 key의 차원은 같음

  - score vector

    - query●key
    - 나머지 단어들과의 interaction 고려
    - attention

  - normalize

    - vector dimension sqrt로 나눔
    - take softmax
    - attention rate(scalar)

  - 최종적으로 나오는 차원은 value의 차원과 같음

    

  1. X x W<sup>Q</sup> = Q
  2. X x W<sup>K</sup> = K
  3. X x W<sup>V</sup> = V
  4. softmax(QxK<sup>T</sup>/sqrt(d<sub>k</sub>)) * V = Z

  

  - CNN이나 MLP에서는 input이 fix되면 output이 고정
  - transformer는 주변 input에 영향을 받아 출력이 달라질 여지가 있는 flexible
    - 많은 computation 요구(N x N)
    - transformer의 한계
  - Multi-headed attention
    - N개의 attention을 반복하면 N번 encoded output

- positioning encoding

  - Transformer encoder는 order independent

i번째 query vector와 나머니 input의 vector의 곱
