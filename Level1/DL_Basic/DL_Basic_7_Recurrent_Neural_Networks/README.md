# 7. Recurrent Neural Networks

RNN

Sequential Model

- Sequential Data
  - 길이를 알 수 없음
    - 차원을 알 수 없음
  - 몇 개의 입력이 들어와도 작동할 수 있도록
- Sequential model
  - 이전 데이터를 통해 다음 데이터를 예측하는 모델
  - 참조해야하는 과거 데이터가 점차 많아짐
    - 특정 지점까지만 참조하는 기법(fixed time span)
  - Markov model
    - 나의 현재는 바로 직전 과거에만 dependent 한 것
    - 많은 정보를 버리게 됨
    - joint distibution을 표현하는 것이 쉬워짐
  - Latent autoregressisve model
    - 중간에 있는 hidden state가 past정보를 summary하고 있음





- Recurrent Neural Network

  - 이전의 입력이 recurrent하게 input
  - time span을 fix하고 시간으로 풀게 되면 input이 큰 하나의 network가 됨
  - short-term dependencies
    - 먼 과거의 정보가 미래까지 살아남기 어려움
    - weight가 계속해서 곱해지며 넘어오며 vanishing/ exploding gradient 발생

- Long Short Term Memory, LSTM

  - core idea
    - cell state
    - 컨베이어 벨트처럼 동작하여 데이터 선택 여부를 결정
  - Forget Gate
    - 버릴 정보를 결정
  - Input Gate
    - cell state에 저장할 정보를 결정
  - cell state update
  - output gate
    - 현재 cell state에서 얼마나 output으로 반환할 것인가

  1. Input이 들어오게 되면 previous cell state를 바탕으로 Previous hidden state와
     input data를 어떻게 사용할 지 결정 C
  2. 현재 데이터를 바탕으로 어떤 값을 사용할 지 취합 Update cell
  3. update된 cell state와 현재 candidate cell state를 조합하여 다시 새로운 cell state를 만듦
  4. 취합된 cell state를 바탕으로 얼마나 뺄 지 결정 output gate

- Gated Recurrent Unit, GRU

  - 2개의 Gate(reset gate와 update gate)
  - cell state가 없고 hidden state가 곧 output gate
