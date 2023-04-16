## 기계독해와 데이터 증강기법을 활용한 다목적 차세대 인공지능 챗봇 개발
<hr>

### Purpose
- 목적지향형 챗봇을 개발하기 위하여 데이터 증강과 기계독해(MRC)를 활용한 챗봇 모델 개발

### Data
- 패턴인식 및 증강: 실제 챗봇에서 사용한 데이터
- Table MRC: Aihub의 행정문서와 뉴스 기계독해 데이터, KorQuAD2.0
- Pretrained Data: 위키피디아, 나무위키, KowikiTabular

<hr>

## 1. Pattern Recognition
### Purpose
- 실제 기업은 챗봇을 구축하기 위한 데이터가 많지 않음
- 작은 질문 데이터를 증강 시켜 적은 데이터로도 챗봇 프로세스를 구축하기 위함

### Process
<img src="https://user-images.githubusercontent.com/123627186/232270739-bdaea56d-18e4-4bc3-9b88-fa369231ffdc.png" width="600" height="300">

### Method
- Sentence Transformer
- RoBERTa
- Konlpy
- Ensemble

### Result
<img src="https://user-images.githubusercontent.com/123627186/232271573-8bda011a-e4c1-4fd0-bf4d-c25f5ac16788.png" width="550" height="400">

### Conclusion
- 특정 기관의 실제 챗봇 질의응답 데이터를 이용하여 패턴 인식 프로세스를 수행하였음
- 앙상블을 했을때의 성능이 가장 우수하였지만, 속도 등 여러가지 고려사항을 생각하여 RoBERTa 모델을 사용함

<hr>

## 2. Table MRC
### Purpose
- 학습되지 않은 질의에 대응하기 위해 기계독해 알고리즘이 필요
- 기업의 문서에는 데이터 베이스, 웹문서, 사이트 내부 문서 등 다양한 곳에 다양한 형태로 존재하며, 해당 문서에는 Table이나 List 형식의 데이터들이 다수 존재함
- 기존 HTML에 존재하는 Table Data는 HTML 코드때문에 Column name과 Value값의 차이가 많이 나는 것을 확인하였음
- 이 문제를 해결하기 위해 선행연구를 참고하여 Table MRC를 진행함

### Process
<img src="https://user-images.githubusercontent.com/123627186/232272021-9727c54a-a927-4ef6-b488-4cbbf4bfd74b.png" width="700" height="300">

### Method
- transfer learning
- hugging face
- RoBERTa
- Bert
- Kobigbird

### Result
<img src="https://user-images.githubusercontent.com/123627186/232272272-c140b476-cbb6-41e4-b544-4a4b42df9de9.png" width="550" height="400">

### Conclusion
- Train Data 답변에 존재하는 UNK 단어를 찾아 직접 사전에 추가하는 작업을 진행하였음
- 선행연구를 참고하여 Table에 대한 포맷을 변경하고 Aihub에 존재하는 MRC 데이터를 활용하여 전이학습을 시도
- 다양한 방법을 시도한 결과 Baseline보다 EM과 F1 Score가 평균 4점 이상 상승하는 결과를 얻었음

### Learning Point
- Pretraining을 하고 Fine-tuning의 성능이 아쉬웠지만, Pretraining의 전반적인 과정을 공부할 수 있었음
- 포기하지 않고 다양한 시도를 할 수 있는 자세를 배움
- 챗봇의 전체적인 프로세스를 이해할 수 있었으며, 다양한 사전학습 모델에 대해 공부 할 수 있었음










