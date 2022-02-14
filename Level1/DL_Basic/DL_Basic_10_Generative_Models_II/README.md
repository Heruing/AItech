# 10. Generative Models Part II

**Latent Variable Models**

**Vaszriational Auto-encoder**

- Variational inference(VI)

  - Posterior distribution(p)을 찾기 위함
    - ↔ likelihood
  - Variational distribution(q)
    - Poterior distribution에 근사하기 위함
  - KL divergence
  - 목적은 p를 찾는 것이나, p가 무엇인지 모름
    - 마치 target을 모르고 loss function을 찾는 것
  - Evidence Lower Bound(ELBO)를 키움으로써 KL divergence를 줄이는 것
    - p는 계산할 수 없어도 ELBO는 계산할 수 있음
    - reconstruction term
      - encoder를 통해서 x를 latency space로 보냈다가 다시 decoder로 돌아오는
        reconstruction loss를 줄이는 것
    - prior fitting term
      - x라는 image를 latent space에 올려놓고, 이 점들의 분포와 사전 분포를 동시에
        만족하는 분포를 찾는 것

  1. 어떠한 입력이 주어짐
  2. latent space로 보내서 무언가를 찾고 reconstruction하는 term으로 만들어짐
  3. latent space된 prior distribution z를 sampling
  4. 디코더에서 나오는 output을 generation result로 여김?

  - 엄밀히 generative model이라 보긴 어려움?

- limitation

  - explicit한 모델이 아님
    - likelihood 알기 어려움
  - prior fitting term
    - gaussian이 아닐 때 활용 어려움





**Adversarial Auto-encoder**

GAN을 활용해서 latent distribution 사이의 분포를 맞춰줌

prior fitting term을 GAN objective로 바꿈

sampling만 가능한 어떤 분포만 있어도 활용 가능





**Generative Adversarial Network(GAN)**

Two Player Game
discriminator는 결과물을 학습하고, generator도 이를 속이기 위한 output을 만듦

- GAN Objectiv
  - generator와 discriminator의 minimax game
- DCGAN
- Info-GAN
  - class를 집어넣음
    - GAN이 c라는 특정 벡터에 집중하게끔 만듦
- Text2Image
- PuzzleGAN
  - subpatch로 원본을 복원
- CycleGAN
  - image간의 도메인을 변경
  - Cycle-consistency loss
    - 두 개의 GAN 구조
- Star-GAN
  - image control
- Progressive-GAN
