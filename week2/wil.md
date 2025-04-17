# 기초 인공지능 스터디 2주차

### 이미지
- 이미지의 구성
    + 이미지: 픽셀들의 행과 열로 구성
    + 채널: 픽셀의 색을 구성 (RGB,  HSV)

- 이미지 처리
    + Image Classification: Detection -> Segmentation -> Image Captioning
    + 해결할 것: viewpoint, illumination, deformation, occlusion, background clutter, intraclass variation

### Loss Function
- 더 정확한 예측을 위해 현재 예측값과 실제 값과의  차이를 수치화하여 이를 바탕으로가중치를 업데이트 하기위한 함수

- 경사하강법
    + 함수의 값이낮아지는 방향으로 각 독립변수들의값을변형시키면서 함수가 최솟값을 갖도록 하는 독립변수의 값을 탐색하는 방법
    + W = W - α(∂L/∂W), α(learning rate): 학습률

- SVM(Support Vector Machine)
    + safety margin: 정답 클래스의 예측 점수가 다른 클래스의 예측 점수보다 더 커야하는 최속값
    + 정답 클래스 yi를 제외한 나머지 클래스 y의 합을 구하고 정답 클래스의 스코어와 오답 클래스의 스코어 비교

- Softmax
    + SVM에서는 스코어 자체에 해석으로 고려하지 않고 정답 클래스가 정답이 아닌 클래스들보다 더 높은 스코어를 기대
    + softmax는 스코어 벡터값을 이용해 클래스별 확률 분포를 계산
    + 스코어에 지수를 취해 양수로 만들고 그 지수들의 합으로 다시 정규화 -> 해당 클래스일 확률

### 정규화(Regularization)
- 과적합(Overfitting)
    + 과소적합: 이미 있는 train  set도 학습을 하지 못한 상태
    + 과적합: 학습 데이터와 너무 유사하여 새 데이터를 올바르게 예측하지 못하는 모델을 만드는것

- 손실 함수에 특정규제 함수를 더하여  손실이 너무 작아지지 않도록 W에 패널티를 가하는 방법

- L1 Regularization: 특정 가중치를 0으로 만드는 효과 -> 불필요한 가중치의 특성을 없앰

- L2 Regularization: 큰가중치 값에 더 큰 패널티 부과 -> 대부분의 특성이 조금씩 반영됨
