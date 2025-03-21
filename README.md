# 환자의 특성에 따른 폐암 진행 속도 예측하는 모델

# 1️⃣ 팀 소개
> SK네트웍스 Family AI 캠프 11기 ML Project<br/>
> 팀 명: 3조 <br/>
> 기간: 2025.03.14 - 2025.03.21<br/>

## 👤팀원 소개

<table align="center">
  <thead>
    <td align="center">
      <a href="">
        <img src="https://github.com/user-attachments/assets/a28f14f0-2e04-4bb9-be4f-2fe81924e523" height="200" width="200" alt="jungsu"/><br /><hr/>
        배정수
      </a><br />
    </td>
    <td align="center">
      <a href="https://github.com/HybuKimo">
        <img src="https://github.com/HybuKimo.png" width="200" alt="junhee"/><br /><hr/>
        신준희
      </a><br />
    </td>
    <td align="center">
      <a href="https://github.com/yugyeongh">
        <img src="https://github.com/yugyeongh.png" width="200" alt="yugyeong"/><br /><hr/>
        현유경
      </a><br />
    </td>
  </thead>
</table>

<br/><br/>

# 2️⃣ 기술 스택
<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white">
  <img src="https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=vscode&logoColor=white">
  <img src="https://img.shields.io/badge/numpy-%235865F2.svg?style=for-the-badge&logo=numpy&logoColor=white">
</p>
<p align="center">
  <img src="https://img.shields.io/badge/pandas-%23000000.svg?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black">
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
</p>
<br/><br/>

# 3️⃣ EDA 결과 다시보기
- 기존 예측: 폐암 진행 속도는 공기 오염도와 연관이 있을 것이다.
- 실제 폐암 진행 속도에 영향을 끼치는 TOP 6 요인
  - 비만, 알코올, 균형 잡히지 않은 식단, 먼지 알레르기, 유전적 요인, 간접 흡연
<img width="793" alt="image" src="https://github.com/user-attachments/assets/13636432-f78d-4b45-baed-40a6462cca55" />

<br/><br/>

# 4️⃣ WBS
| 작업 명                | 시작일 | 종료일 | 담당자         | 산출물        |
|-------------------------|-------|-------|-----------------|---------------|
| Machine Learning 모델 선택       | 03-14 | 03-14 | ALL    |  [GitHub Wiki](https://github.com/encore-SKN11/ML-3Team/wiki/%F0%9F%A4%96-%EC%96%B4%EB%96%A4-%EB%A8%B8%EC%8B%A0%EB%9F%AC%EB%8B%9D-%EB%AA%A8%EB%8D%B8%EC%9D%84-%EC%A0%81%EC%9A%A9%ED%95%A0%EA%B9%8C)  | 
| KNN, Logisitic Regression, Decision Tree 모델 실행       | 03-15 | 03-17 | ALL    |  Jupyter Notebook, 그래프 시각화  | 
| KNN 학습 및 KNN 최적화    | 03-14 | 03-20 | 신준희    |  Jupyter Notebook, 그래프 시각화  |
| Decision Tree 및 Random Forest를 통한 학습       | 03-15 | 03-20 | 배정수, 현유경    |  Jupyter Notebook, 그래프 시각화  | 
| 각 모델 교차 검증 및 모델 최적화       | 03-15 | 03-20 | 배정수    |  Jupyter Notebook, 그래프 시각화  | 
| SVC 및 DecisionBoundaryDisplay를 통한 시각화    | 03-15 | 03-20 | 신준희, 현유경    |  Jupyter Notebook, 그래프 시각화  | 
| Voting Classifier       | 03-17 | 03-20 | 현유경    |  Jupyter Notebook, 그래프 시각화  |
| 문서 작업   | 03-19 | 03-20 | 배정수, 현유경   |  README.md     | 
| 발표 준비   | 03-19 | 03-20 | 신준희             |  발표     |
| 최종 점검                | 03-20 | 03-21 | ALL             |               | 

<br/><br/>

# 5️⃣ 적합한 머신러닝 모델 선택하기
### 🤖 프로젝트 목표: 환자의 특성에 따른 폐암 진행도를 예측하자!
- EDA를 통해 파악한 데이터 구조 활용
  - `Target data`: 페암 진행 레벨 컬럼
  - `Input data`: EDA를 통해 폐암 진행 레벨과 상관관계를 보인 컬럼
> [!IMPORTANT]
> Input data를 폐암 진행 레벨(1,2,3)로 분류하는 것이니 지도학습 중 분류 모델을 사용하자!

<br/><br/>

# 6️⃣ 지도 학습 분류 모델 적용하기
### 1) KNN
- 적용 이유: 비선형 데이터에서 정확도가 높은 모델
- 정확도: 98.4% -> ⚠️ 과적합 의심
- K 값에 따른 성능 변화 시각화 <br/>
  ![image](https://github.com/user-attachments/assets/632eab53-821d-472c-9576-87cf71529fb0)

- KFold를 통한 교차검증 진행
  - 모델 정확도: 99.2% <br/>
  ![image](https://github.com/user-attachments/assets/36aa70bc-cb92-43e6-9cba-7d6ab1a4a932) <br/>

- 차원 축소를 통한 KNN 시각화
  - PCA <br/>
  ![image](https://github.com/user-attachments/assets/257cca82-7005-4cfc-bf0c-9649203669f9)
  - LDA <br/>
  ![image](https://github.com/user-attachments/assets/9f2f50ff-c359-4073-87bb-48262c803035)

- LDA 후 K값에 따른 성능 변화 시각화<br/>
  ![image](https://github.com/user-attachments/assets/db4b2c5b-3519-40fb-92ce-0d95b8b9f326)<br/>

 <br/>
   
### 2) Logistic Regression
- 적용 이유: 소프트맥스를 사용하면 다중 클래스 분류가 가능
- 정확도: 88% <br/>
  ![image](https://github.com/user-attachments/assets/99f8de71-6294-48c7-98b0-83501e7d2a6c) <br/>
- 정확도를 높이기 위한 GridSearchCV
  - GridSearchCV 적용 후 정확도: 90.8% <br/>
  ![image](https://github.com/user-attachments/assets/85274a64-a2a3-4501-b180-170c8fa899d8) <br/>


### 3) Decision Tree
- 적용 이유: 폐암 진행 레벨에 따라 분할해 예측하기 위해 사용 <br/>
  ![image](https://github.com/user-attachments/assets/6c5f23f5-2a6c-46c5-852f-1988bc551878) <br/>
- 정확도: 100% -> ⚠️ 과적합 의심
- 특성 중요도 시각화 <br/>
  ![image](https://github.com/user-attachments/assets/aeb4dad7-1a23-488b-b3b1-0098f21d2a34)  <br/>
  > ❓ EDA에서 도출해낸 결과와 다르다!
  > 하나의 Decision Tree만을 사용해서 편향된 결과일 가능성이 높음 <br/>
  >    👉🏻 앙상블 기법 중 Random Forest를 사용하자!
  <br/>

 #### 🌳 Random Forest
- Random Forest 상세 성능 지표<br/>
  ![image](https://github.com/user-attachments/assets/f7de14f3-0684-4a07-82b3-f2623087a20c) <br/>
- 과적합 문제를 해결하기 위한 방안: 하이퍼 파라미터 조정
  - `max_depth=5` (트리의 최대 깊이), `n_samples_split=5` (내부 노드의 최소 샘플 수) 조정<br/>
  - 정확도: 96% <br/>
  ![image](https://github.com/user-attachments/assets/4d75e2b9-99a9-4388-9804-fae739413acc) <br/>
- Random Forest를 적용한 특성 중요도 시각화<br/>
  ![image](https://github.com/user-attachments/assets/66686203-c1ea-4b20-ad9a-a88e1f53f74b) <br/>
  -> EDA에서 도출해낸 결과와 비슷한 결과를 보임


<br/><br/>

# 7️⃣ 과적합 해결하기
### SVM (Support Vector Machine)
- 적용 이유: 고차원 데이터의 과적합을 방지해주는 모델
- 정확도<br/>
  ![image](https://github.com/user-attachments/assets/4b42e0d6-00bc-4dd0-8fe6-670e0618336d) <br/>
- DecisionBoundaryDisplay를 통한 시각화
  - A) PCA를 사용한 차원 축소
    - 적용 이유: 데이터셋의 차원을 축소하기 위함
      ![image](https://github.com/user-attachments/assets/f021bbc0-9614-4628-b896-4b045d078b2b) <br/>
      -> 정확도는 69%, 64%, 68% 로 비교적 낮음
  - B) LDA를 사용한 차원 축소
    - 적용 이유: PCA는 X 데이터만을 사용해 차원 축소를 하지만, LDA는 X 데이터와 y 데이터를 사용해 차원을 축소하기 때문<br/>
      ![image](https://github.com/user-attachments/assets/07b6465d-04b8-40d9-9081-d6f603942a92)<br/>
      -> 정확도가 85%, 80%, 83% 로 증가

<br/><br/>

# 8️⃣ 앙상블 적용하기
- `KNN`, `Logistic Regression`, `Random Forest`, `SVC`
### Hard Voting
- 적용 이유: 학습기를 결합시켜 강한 학습기를 만들기 위해 사용
- Hard Voting 시각화
![image](https://github.com/user-attachments/assets/a5b0fa78-4975-400e-b0ad-ce66a579a0b4)
  -> 각 모델이 높은 성능을 보였기에 Hard Voting은 최적의 결과를 낸 것임
  -> 단, 아직 과적합 우려가 있음

### Soft Voting 
- 적용 이유: 상대적으로 과적합된 모델의 영향력을 낮추기 위해 사용
- Soft Voting 시각화
![image](https://github.com/user-attachments/assets/b717306c-1da0-4a3e-b6ef-94eb625fa10c)
  -> Hard Voting에 비해 정확도가 낮게 나오는 이유는 과적합된 모델의 영향이 낮아진 것이라 볼 수 있음
  
<br/><br/>
# 9️⃣ 결론
- EDA
  - 데이터셋에 이상치,결측치가 없어 전처리 작업이 최소화되었고, 잘 정제되어있어 모델 학습,평가에 어려움이 적었음
- 머신러닝
  - 모델들이 전반적으로 평가지표가 높았음 -> 데이터 전처리의 필요성과 데이터 품질이 중요.
  - 전체적으로 높은 평가지표를 보고 과적합이 의심되어 여러가지 개선방안을 고려하여 시도, 많은 특성과 적은 데이터의 양으로 인한 한계  
- 결론
  - eda에서 폐암심각도와 상관관계가 높았던 특성들이 특성중요도 또한 높게 나옴. 주요특성들로 나온  개인의 생활습관들이  폐암의 조기진단, 예방에 도움이 됨
<br/><br/>

# 🔟 한 줄 회고
| 팀원  | 한 줄 회고                 |
|-------|----------------------------|
| 정수  | EDA에 이어서 모델의 선정, 과적합 해결, 시각화 등을 진행하며 지금까지 학습한 내용들을 종합적으로 다함께 정리해보는 느낌이라 유익한 시간이었습니다. 팀원들 또한 일처리가 매우 야무지고 프로세스가 서로 막힘없이 매끄럽게 진행되어 좋은 협업이 되었습니다. |
| 준희  | 직접 해본 EDA를 가지고 적절한 머신러닝 모델을 찾아서 적용하고 이를 통해 발생하는 문제들을 해결하고, 시각화 자료로 도출하면서 지금까지 배운 지식을 많이 이해할 수 있게 되었습니다. 또한 팀원분들께서 각자 맡은 역할을 성실히 이행하시고, 진행하다가 막히는 부분이 있으면 같이 찾아보고 해결하고 수월하게 진행할 수 있어 감사했던 프로젝트였습니다.🥔 |
| 유경  | 데이터에 알맞은 머신러닝 모델을 찾기 위한 고민부터 여러 가지 머신러닝 모델을 적용하면서 모델의 정확도를 높이거나 과적합을 해결했던 과정 덕분에 모호했던 개념들이 확실하게 잡혔습니다! 그리고 팀원분들께 제가 가진 의문점에 대해 여쭤보면 확실하고 명확하게 답변해 주셔서 얻어가는게 많았던 프로젝트였습니다🤩  |
