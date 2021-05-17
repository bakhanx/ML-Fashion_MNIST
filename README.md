# ML-Fashion_MNIST

# Title : fashion MNIST and scikit_learn

## fashion MNIST 데이터 1000개만 가지고 학습, 평가(교차검중)함 : 아래 프로그램 참조

내용 : <br>

- 분류기 정확도(accuracy) 비교 : SVM, DecisionTree, RandomForestClassifier <br>
- 가장 좋은 분류기 성능 계산 : Confusion Matrix, Confusion Matrix error plot, Error Analysis <br>

1. 목적 : Fashion MNIST 데이터를 가지고 ( SVM / DecisionTree / RandomForest ) <br>세 가지 모델을 파라미터 튜닝해서 각각의 최고성능(인식율)을 구한다. <br>
2. 내용 및 방법 : 데이터 읽기 빛 분석, 모델 성능평가 <br>
3. 결과 : 각 분류기 성능 비교, 선택된 분류기로 결과 <br>

## 데이터 읽기 및 분석

1. Train

- 60000개의 데이터중 1000개만 추출 <br>
- 2차원 데이터를 1차원 데이터로 reshape (28x28 -> 1x784)

2. Test

- 10000개의 데이터중 1000개만 추출
- 2차원 데이터를 1차원 데이터로 reshape (28x28 -> 1x784)

<br>

<img src="https://user-images.githubusercontent.com/46181173/118445879-ee085e00-b729-11eb-97dd-aaed04cb5664.png" height="50%" width="50%"> <br>
<예시 : 추출한 1000개의 데이터 중 100개의 이미지> <br>

## SVM

결정 경계(Decision Boundary), 즉 분류를 위한 기준 선을 정의하는 모델<br>
분류되지 않은 새로운 점이 나타나면 경계의 어느 쪽에 속하는지 확인해서 분류 과제를 수행

- Default
- polynomial (Best)
- RBF
- Sigmoid

## DecisionTree

결정 트리는 의사 결정 규칙과 그 결과들을 트리 구조로 도식화한 의사 결정 지원 도구의 일종. <br>
의사 결정 분석에서 목표에 가장 가까운 결과를 낼 수 있는 전략을 찾기 위해 주로 사용되는 방식.

- Default
- Grid Search

<img src="https://user-images.githubusercontent.com/46181173/118445481-74707000-b729-11eb-8838-2fdbeee98e56.png">

## RandomForest

결정트리(Decision Tree)분류기 여러 개를 훈련시켜서 그 결과들을 가지고 예측을 하는데,
각각의 결정트리를 훈련시킬 때 전체 훈련 세트에서 중복을 허용하여 샘플링한 데이터셋을
개별 결정트리 분류기의 훈련 세트로 하여 훈련시키는 방식

- Default
- Grid Search

## 성능비교 (정확도)

- SVC : 0.815
- DecisionTree : 0.695
- RandomForest : 0.818 <br>

RandomForest의 성능이 가장 좋음

## Error Analysis

### Confusion Matrix <br>

<img src="https://user-images.githubusercontent.com/46181173/118446333-7b4bb280-b72a-11eb-938e-ceb08d9c4c04.png" width="55%">
<img src="https://user-images.githubusercontent.com/46181173/118446235-5c4d2080-b72a-11eb-943b-24cc92d8920e.png" width="40%">  <br>

<img src="https://user-images.githubusercontent.com/46181173/118446297-6f5ff080-b72a-11eb-9e71-1ee210c58c35.png" width="50%"> <br>
Pullover > Coat 오인식 20개 <br>
Shirt > Pullover 오인식 19개
