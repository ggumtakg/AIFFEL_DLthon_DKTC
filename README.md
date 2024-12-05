# AIFFEL_DLthon_DKTC

## Overview
대화의 성격을 위협 세부 클래스 4개 또는 일반 대화 중 하나로 예측하는 과제

- 학습 데이터는 '협박', '갈취', '직장 내 괴롭힘', '기타 괴롭힘' 등 4개 클래스 각 약 1천 개로 구성

- 테스트 데이터는 '협박', '갈취', '직장 내 괴롭힘', '기타 괴롭힘', '일반 대화' 등 5개 클래스 각 1백여 개로 구성

    - train data에는 없지만, test data는 일반 대화 클래스가 존재합니다. 5개 문장을 분류할 수 있게 train data에 일반 대화 데이터셋을 추가합니다.

        - 일반대화는 합성데이터로 구성합니다. 다양한 프롬프트로 문장을 생성하고, 이를 학습에 활용합니다.
            - [일반대화 클래스]를 제외한 데이터의 추가나 외부 데이터 사용 불가(단, Augmentation은 가능)
        - Pre-trained model은 공개된 모델에 한하여 사용 가능(재현성을 위함)
        - 학습 결과를 확인하며 어떤 일반 대화 데이터셋이 성능을 높이는데 도움을 주는지 비교/기록합니다.
            - 위 기준에서 벗어나지 않는 범위 내에서 데이터셋의 구성은 자유입니다. 성능을 비교/기록해보세요 :)
            - 일반대화 데이터셋은 여러 방식으로 구할 수 있습니다. 어떤 경로를 통해 얻은 데이터셋의 성능이 좋은지 비교/기록합니다.
                - 합성데이터 생성 및 활용
                - 기 확보된 데이터 활용(추가실험)
        - 실험 결과를 Ablation study형식으로 기록합니다
```python
# 일반대화 예시
{
    "id": {
        "text": "이거 들어봐 와 이 노래 진짜 좋다 그치 요즘 이 것만 들어 진짜 너무 좋다 내가 요즘 듣는 것도 들어봐 음 난 좀 별론데 좋을 줄 알았는데 아쉽네 내 취향은 아닌 듯 배고프다 밥이나 먹으러 가자 그래"
    }
}
```
  
## Description
### 과제
DKTC 훈련 데이터를 이용해
협박, 갈취, 직장 내 괴롭힘, 기타 괴롭힘, 일반 대화 5가지 대화 유형 Class를 분류하는 딥러닝 모델을 만듭니다.
DKTC 테스트 데이터를 활용해 분류 성능을 평가합니다.
리더보드를 이용해봅니다.

원본 과제 참고 링크  
[Tunib GitHub](https://github.com/tunib-ai/DKTC)  

## 데이터 구조
![data](https://user-images.githubusercontent.com/42150335/149441163-7728a543-5dbd-4fb6-b12f-cae5fc79c6fe.png)
  
|클래스|Class No.|# Training|# Test|
|:----:|:------:|:------:|:------------:|
|협박|00|896|100|
|갈취|01|981|100|
|직장 내 괴롭힘|02|979|100|
|기타 괴롭힘|03|1,094|100|
|일반|04|-|100|

## 팀원
|팀장|팀원|팀원|팀원|
|:----:|:------:|:------:|:------------:|
|김영민|김준석|김희찬|이예지|