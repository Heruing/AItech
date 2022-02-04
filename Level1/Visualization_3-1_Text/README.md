## Text 사용하기

#### 1. Matplotlib에서 Text

1. Text in Viz
   - 전달에 있어 오해를 방지할 수 있음
   - 과한 사용은 이해를 방해
2. Anatomy of a Figure(Text ver.)
   - Title
     - 가장 큰 주제를 설명
   - Label
     - 축에 해당하는 정보를 제공
   - Tick Label
     - 축에 눈금을 사용한 스케일 정보 추가
   - Legend
     - 2개 이상의 다른 데이터를 분류하기 위한 보조 정보
   - Annotation(Text)
     - 이 외 설명을 추가
3. Text API

#### 2. Text Properties

1. Font Components
2. Easy to use Props
3. Alignment
4. Bbox

#### 3. 한글 in Matplotlib

1. 한글 설정하기



**실습**

- `fig.text(n, m, s='string')`
  - figure의 비율 n, m 위치에 s가 들어감
- Font
  - family
    - 글꼴
    - 기본 serif
  - style
    - normal과 italic 정도만 숙지
  - weight
    - 글자 두께 지정
    - 숫자로 지정 가능
  - size
- Details
  - color
  - linespacing
  - backgroundcolor
  - alpha
  - zorder
  - visible
- Alignment
  - ha
    - horizontal alignment
  - va
    - vertical alignment
  - rotation
  - multialignment
- Advanced
  - bbox
  - [fancy box](https://matplotlib.org/stable/gallery/shapes_and_collections/fancybox_demo.html)
- legend
  - loc
  - shadow
  - loc
    - lower
  - bbox_to_anchor = [n, m]
