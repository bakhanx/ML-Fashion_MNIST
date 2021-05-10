# ML-Fashion_MNIST

# Title : fashion MNIST and scikit_learn

## fashion MNIST 데이터 1000개만 가지고 학습, 평가(교차검중)함 : 아래 프로그램 참조
내용 : <br>
  1) 분류기 정확도(accuracy) 비교 : SVM, DecisionTree, RandomForestClassifier <br>
  2) 가장 좋은 분류기 성능 계산 : Confusion Matrix, Confusion Matrix error plot, Error Analysis <br>
  1) 목적 : Fashion MNIST 데이터를 가지고 ( SVM / DecisionTree / RandomForest ) <br>세 가지 모델을 파라미터 튜닝해서 각각의 최고성능(인식율)을 구한다. <br>
  2) 내용 및 방법 : 데이터 읽기 빛 분석, 모델 성능평가 <br>
  3) 결과 : 각 분류기 성능 비교, 선택된 분류기로 결과 <br>

```python
# 파이썬 ≥3.5 필수
import sys
assert sys.version_info >= (3, 5)

# 사이킷런 ≥0.20 필수
import sklearn
assert sklearn.__version__ >= "0.20"

# 공통 모듈 임포트
import numpy as np
import os

# 노트북 실행 결과를 동일하게 유지하기 위해
np.random.seed(42)

# 깔끔한 그래프 출력을 위해
%matplotlib inline
import matplotlib as mpl
import matplotlib.pyplot as plt
mpl.rc('axes', labelsize=14)
mpl.rc('xtick', labelsize=12)
mpl.rc('ytick', labelsize=12)

# 그림을 저장할 위치
PROJECT_ROOT_DIR = "."
CHAPTER_ID = "classification"
IMAGES_PATH = os.path.join(PROJECT_ROOT_DIR, "images", CHAPTER_ID)
os.makedirs(IMAGES_PATH, exist_ok=True)

def save_fig(fig_id, tight_layout=True, fig_extension="png", resolution=300):
    path = os.path.join(IMAGES_PATH, fig_id + "." + fig_extension)
    print("그림 저장:", fig_id)
    if tight_layout:
        plt.tight_layout()
    plt.savefig(path, format=fig_extension, dpi=resolution)
```
