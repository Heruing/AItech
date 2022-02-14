# 4. Convolution Neural Networks

합성곱 convolution

- continuous convolution
  - 두 개의 함수를 잘 섞어주는 방법
- n x n 필터를 m x m image에 사용하면 m-n+1 x m-n+1 output이 나옴
- RGB
  - depth = 3(r, g, b)
- stack of convolutions
  - 여러 convolution을 거칠 수 있음
  - filter를 여러개 사용하여 채널을 조절할 수 있음





- stride
  - kernel을 넘어가는 단위
- padding
  - 이미지 가장자리를 convolution operating을 하기 위함
    - zero padding





depth는 점점 깊어지지만, parameter 수는 점차 줄어드는 방향으로 발전

- 1 x 1 Convolution
  - depth는 깊어짐
  - parameter 줄어듦
    - dimension 감서
