# 기초 인공지능 스터디 1주차

### 인공지능
- 인간의 학습/추론/지각능력을 인공적으로 구현하려는 컴퓨터 과학의 세부분야 중 하나
- e.g. 자율주행, chatGPT, Siri 등

### 머신러닝
- 컴퓨터가 데이러부터 패턴을 학습하고, 학습한 내용 바탕으로 결정을 내리는 기술
- e.g. 스팸메일 분류, 이미지 속 객체 인식 등
- 모델: 학습된 패턴을 수학적으로 나타냄

### 딥러닝
- 인공신경망을 이용한 모델 학습방법
- 인공신경망: 인간의 뉴런을 본따 만든 네트워크로 학습하는 모델 (FNN, CNN 등)
- 여러 층을 쌓아 복잡한 문제 표현 가능

### 학습 방법
- 지도학습
    + 대상에 x, 데이터에 y라는 레이블을 달아 그 특징을 학습시킴
    + 분류 문제, 번역기 등에 활용

- 비지도학습
    + 정답이 없는 데이터를 학습
    + e.g. clustering algorithm: 레이블 없이 데이터 내에서 거리가 가까운 것들끼리 그룹핑

- 데이터 분리
    + 전체 데이터를 세가지 데이터로 나누어 사용
    + 학습: 모델 학습용
    + 검증: 모델의 하이퍼파라미터 학습용
    + 테스트: 최종 모델 평가용

### 기초적인 모델
1. Nearest Neighbor Classifier
    - 모든 학습 데이터 기억
    - 모든 학습 데이터와 비교해 가장 가까운 학습 이미지의 레이블 리턴
    - 픽셀별 rgb값 비교
    - L1 distance: 절대값 / L2 distance: 유클리드

2. KNN
    - NNC랑 대체로 비슷한데 가장 가까운 이미지만 리턴하는게 아니라 K개의 가까운 이미지를 찾고 가장 많이 나온 이미지의 레이블 리턴
    - 똑같이 L1, L2 distance 이용
    - 여러 이미지를 보기 때문에 정확성 100% 나오지 않음
    - 정해야할 것: 어떤 distange 사용할지, K 몇으로 할지 (validation data를 가지고 테스트하여 가장 정확성 높게)
    - 학습데이터 많을수록 테스트 시간도 길고, shifted/messed up/darken 등 이미지 조금만 변형해도 성능이 떨어짐

3. 선형분류
    - 분류를 파라미터적으로 접근 (like 함수)
    - F(x, W): x는 input, W는 가중치 -> f(x) = Wx + b
    - 색에 영향을 많이 받음
    - 평가: score 행렬을 만들고 이를 정답과 비교하여 loss function 정의해야 함

