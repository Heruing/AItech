# 9. Generative Models Part I

- Learning Generative Model
  - generation
  - Density estimation
    - discriminative model의 의미를 내포
    - explicit model
  - feature learning

**Basic Discrete Distributions**

- Bernoulli distribution
  - 확률은 1개 필요(p, 1-p)
- Categorical distribution
  - n-1개의 parameter 필요
- example
  - r, g, b case
    - 256 x 256 x 256
    - parameter numbers: 256 x 256 x 256 - 1
  - binary
    - 2ⁿ-1개의 parameter가 필요
- Structure Through Independence
  - n pixels가 independent하다고 가정하면, n개의 parameter로 줄어듦
    - 줄어든 만큼 말이 안 되는 가정
    - 표현할 수 있는 이미지가 없어짐
- Conditional Independence
  - parameter 값을 줄이며 타당성을 갖는 가지기 위한 기법
  - Chain rule(연쇄 법칙)
    - 2<sup>n</sup>-1 개의 parameter
    - Markov assumption
      - i+1번째 pixel은 i번째 pixel에만 dependent하다는 가정
      - 2n - 1개의 parameter
  - Bayes' rule(베이즈 정리)
  - Conditional independence(조건부 독립성)

**Auto-regressive Model**

chain rule, Markov assumption, ordering
이전의 n개를 고려하는 model
어떤 식으로 conditional independence를 주는 지

- NADE: neural autoregressive density estimator
  - i번째 pixel을 첫 번째부터 i-1 pixel에 dependent하게 만듦
    - 1번째 pixel은 independent
    - 2번째는 1번째에만, n번째는 1부터 n-1번째 pixel에 dependent
  - neural network은 weight가 점점 커짐
  - explicit model
    - 임의의 vector가 주어지면 확률을 계산할 수 있음
  - continous  output이면 Gaussian mixture 활용
- Pixel RNN
  - oredering
    - Row LSTM
    - Diagonal BiLSTM
