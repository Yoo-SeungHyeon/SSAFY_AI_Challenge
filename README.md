# SSAFY AI 챌린지

![alt text](./images/image.png)

### Overview

🚗 운전을 하다 갑자기 차가 덜컹!

도로 위 어디서든 불쑥 나타나는 포트홀은 우리의 자동차를 놀라게 하고,

때로는 사고까지 유발하는 도로 위의 ‘깜짝 손님’입니다. 🕳️

이제 이 위험한 존재를 미리 감지할 똑똑한 AI 탐정이 필요해졌어요. 🕵️‍♂️

SSAFY AI 챌린지에서는 여러분이 바로 그 탐정이 됩니다!

주어진 도로 이미지 데이터를 분석해 ‘도로의 블랙홀’ 포트홀을 정확하게 탐지하는 객체 인식 모델을 만들어보세요. 🧠

여러분의 임무는 AI 기술을 활용해 포트홀을 빠르고 정확하게 찾아내는 것! 🛠️

최고의 AI 탐정으로 선정되면 특별한 보상도 기다리고 있으니, 지금 바로 도전하세요! 🎯

- 📦 YOLOv8 템플릿 제공 (초보도 환영!)

- 🧪 실험과 튜닝으로 모델 성능을 쭉쭉!

- 📈 실시간 리더보드 & 시상

- 🏆 최고의 AI 탐정에게는 특별한 보상까지!

- 📷 내가 직접 찍은 도로 사진도 학습 데이터로 포함!모델 성능이 쭉쭉!

![alt text](./images/image-1.png)

---

### Description

도로 위 포트홀(Pothole)은 차량에 손상을 입히고, 심한 경우 사고로 이어질 수도 있는 위험 요소입니다.

포트홀은 주로 도로의 균열이나 침식으로 인해 발생하며, 이를 신속하게 탐지하고 보수하는 것이 매우 중요합니다.

그러나, 기존의 포트홀 감지 방식은 도로 점검원이 직접 육안으로 확인하거나,

차량에 센서를 장착하는 방식이 주를 이루고 있습니다. 이는 비용이 높고, 실시간 탐지가 어렵다는 단점이 있습니다.

이러한 한계를 극복하기 위해 컴퓨터 비전과 AI를 활용한 포트홀 자동 감지 기술이 각광받고 있습니다.

본 챌린지에서는 참가자들이 객체 탐지(Object Detection) 모델을 활용하고

주어진 도로 이미지 데이터셋과 추가 데이터 수집을 통해

포트홀을 정확하게 감지하는 AI 모델을 개발하는 것이 목표입니다.

이를 통해, AI 개념과 작동원리를 이해하고 활용 역량과 실제 문제 해결 능력을 향상시킵니다.

AI 기반 포트홀 감지는 다음과 같은 이점을 제공합니다.

✅ 자동화: 인공지능을 활용해 도로 상태를 실시간으로 점검 가능

✅ 정확성: 육안보다 일관적이고 정밀한 탐지 가능

✅ 비용 절감: 기존 방식보다 유지보수 비용 절감 가능

---

### Evaluation

제출된 모델은 객체 탐지(Object Detection) 성능을 평가하는 지표를 기반으로 점수화됩니다.

**📊 Scoring**

모델의 성능은 mAP (Mean Average Precision @ IoU 0.5) 점수를 기준으로 평가됩니다.

추가적으로 IoU (Intersection over Union), Precision, Recall 등의 보조 지표를 참고합니다.

![alt text](./images/image-2.png)

- mAP@IoU 0.5
  - IoU가 0.5 이상일 때 정답(True Positive)으로 간주하여 평균 정밀도(AP)를 계산하고, 전체 클래스에 대해 평균을 구함
- IoU (Intersection over Union)
  - 예측된 바운딩 박스와 실제 바운딩 박스가 얼마나 겹치는지 평가
- Precision & Recall
  - Precision(정밀도): 검출한 포트홀 중 실제 포트홀 비율
  - Recall(재현율): 전체 포트홀 중 올바르게 검출한 비율

  ---

**📤Submission File**

참가자는 모델을 사용하여 테스트 데이터셋의 포트홀 위치를 예측한 결과를 CSV 파일로 제출해야 합니다.

제출 파일 형식

- CSV 포맷

```
ImageId,   ClassId,   X,        Y,       Width,    Height
test1.jpg,  0,        0.436,    0.546,   0.373,    0.235
```

- 예측 좌표 시각화(X, Y, Width, Height)

![alt text](./images/image-3.png)

제출 파일 Column 상세

| Column Name |	Description |
| --- | --- |
| ImageId	| 예측한 이미지 파일명 (예: 0001.jpg) |
| ClassID |	예측한 객체의 클래스 ID (포트홀의 경우 0) |
| X, Y	| 바운딩 박스의 중심 좌표(X: 가로 위치, Y: 세로 위치) |
| Width, Height	| 바운딩 박스의 너비(Width)와 높이(Height) |

---

⚠️ 유의사항
- 제출 파일에는 반드시 헤더가 포함되어야 합니다.
- 모든 테스트 이미지에 대해 한 줄씩 결과를 작성해야 합니다.
  
  → 포트홀이 감지되지 않은 경우에도 해당 이미지 ID는 반드시 포함
- 포트홀이 감지되지 않은 경우에는 아래처럼 빈 바운딩 박스(0값)를 작성합니다:
```
test2.jpg, 0, 0, 0, 0, 0
```
- 각 이미지에 대해 confidence(신뢰도) 값이 가장 높은 바운딩 박스 단 1개만 제출해야 합니다.

  → 여러 개 예측했더라도, 가장 확신 있는 1개만 선택해 제출
- X, Y, Width, Height 값은 이미지 크기 기준으로 정규화된 값이어야 하며,
모두 0.0 ~ 1.0 범위 내에 있어야 합니다.

---

## [`철환이와 아이들` 플젝 과정](./Team.철환이와아이들/README.md)