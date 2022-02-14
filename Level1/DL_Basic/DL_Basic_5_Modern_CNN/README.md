# 5. Modern CNN

결론적으로, depth는 깊게 parameter는 적게 하는 방향으로 발전

**ILSVRC**

- **I**mageNet **L**arge-**S**cale **V**isual **R**ecognition **C**hallenge





- **AlexNet**
  - 2012
  - ReLU activation
    - R(z) = max(0, z)
    - optimize에 용이
    - sigmoid, tanh에 존재하던 gradient vanishing problem 극복
  - GPI implementation
    - 2012년도 당시 일반적이지 않았음
  - overlapping polling
  - data augmentation
  - dropout
- **VGGNet**
  - 2013
  - 3x3 convolution filter
    - AlexNet은 11x11, 5x5 ..
    - 크기가 커지면 고려되는 input의 크기가 커지는 이점이 있음
    - 3x3을 두 번 사용하는 것이 receptive field 관점에서는 같음
    - parameter 수는 40% 가량의 차이 발생
    - 같은 receptive field를 받는 관점에서 작은 filter를 사용하는 것이 유리
    - 이후 더 이상 큰 사이즈 filter를 사용하지 않게 됨
  - 1x1 convolution
  - Dropout
- **GoogLeNet**
  - 2014
  - dimension(channel) reduction
  - 1x1 convolution으로 
  - Network In Network(NIN) 구조
  - Inception blocks
    - convolution 전에 1x1 convolution
- **ResNet**
  - 과도한 parameter 수가 overfitting의 위험 야기
    - 혹은 학습이 진행되지 않는 현상 발생
  - identity map
    - 출력을 convolution layer에 더함
    - "차이"를 학습하게 하여 deep한 layer를 거쳐도 학습할 수 있게 만듦
    - 차원을 맞추기 위해 1x1 Conv
    - Convolution 뒤에 Batch Norm(의견차 있음)
    - 3x3 conv 앞, 뒤로 1x1 conv로 크기 조절?
  - 결론적으로 1x1 Conv로 channel을 줄이고 parameter를 줄이는 기법
- **DenseNet**
  - ResNet처럼 더하지 않고, concatenation하는 기법
  - 2배씩 기하급수적으로 커지는 문제 발생
    - parameter 수가 함께 증가
  - 중간에 한 번씩 이를 줄이는 과정
    - DenseBlock에서 Concat
    - Transition Block에서 1x1 Conv
