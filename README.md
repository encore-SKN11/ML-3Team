# 환자의 특성에 따른 폐암 진행 속도 예측하기

# 1️⃣ 팀 소개
> SK네트웍스 Family AI 캠프 11기 ML Project<br/>
> 팀 명: 3조 <br/>
> 기간: 2025.03.14 - 2025.03.21<br/>

## 👤팀원 소개

<table>
  <thead>
    <td align="center">
      <a href="">
        <img src="https://github.com/user-attachments/assets/a28f14f0-2e04-4bb9-be4f-2fe81924e523" height="150" width="150" alt="jungsu"/><br /><hr/>
        배정수
      </a><br />
    </td>
    <td align="center">
      <a href="https://github.com/HybuKimo">
        <img src="https://github.com/HybuKimo.png" width="150" alt="junhee"/><br /><hr/>
        신준희
      </a><br />
    </td>
    <td align="center">
      <a href="https://github.com/yugyeongh">
        <img src="https://github.com/yugyeongh.png" width="150" alt="yugyeong"/><br /><hr/>
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
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white">
</p>
<br/><br/>

# 3️⃣ EDA 결과 다시보기
- 기존 예측: 폐암 진행 속도는 공기 오염도와 연관이 있을 것이다.
- 실제 폐암 진행 속도에 영향을 끼치는 TOP 6 요인
  - 비만, 알코올, 균형 잡히지 않은 식단, 먼지 알레르기, 유전적 요인, 간접 흡연
![image](https://github.com/user-attachments/assets/50923369-c6eb-4d4b-941b-506a2378bd97)

<br/><br/>

# 4️⃣ WBS
| 작업 명                | 시작일 | 종료일 | 담당자         | 산출물        |
|-------------------------|-------|-------|-----------------|---------------|
| Machine Learning 모델 적용       | 03-14 | 03-19 | ALL    |  Jupyter Notebook  | 
| 문서 작업   | 03-19 | 03-20 | 배정수, 현유경            |  README.md     | 
| 발표 준비   | 03-19 | 03-20 | 신준희             |  발표     |
| 최종 점검                | 03-20 | 03-21 | ALL             |               | 

<br/><br/>

# 5️⃣ 적합한 머신러닝 모델 선택하기
- 프로젝트 목표: 환자의 특성에 따른 폐암 진행도를 예측하자!
- EDA를 통해 파악한 데이터 구조 활용
  - `Target data`: 페암 진행 레벨 컬럼
  - `Input data`: EDA를 통해 폐암 진행 레벨과 상관관계를 보인 컬럼
> [!NOTE]
> Input data를 폐암 진행 레벨(1,2,3)로 분류하는 것이니 지도학습 중 분류 모델을 사용하자!

<br/><br/>

# 6️⃣ 지도 학습 분류 모델 적용하기
### 1) KNN
- 적용 이유: 비선형 데이터에서 정확도가 높은 모델
- 정확도: 98.4% -> ⚠️ 과적합 의심
- KFold를 통한 교차검증 진행
  - 모델 정확도: 99.2%
  ![image](https://github.com/user-attachments/assets/36aa70bc-cb92-43e6-9cba-7d6ab1a4a932)

   
### 2) Logistic Regression
- 적용 이유: 소프트맥스를 사용하면 다중 레이블 분류가 가능
- 정확도: 88%
  ![image](https://github.com/user-attachments/assets/99f8de71-6294-48c7-98b0-83501e7d2a6c)


### 3) Decision Tree
- 적용 이유: 폐암 진행 레벨에 따라 분할해 예측하기 위해 사용
  ![image](https://github.com/user-attachments/assets/6c5f23f5-2a6c-46c5-852f-1988bc551878)
- 정확도: 100% -> ⚠️ 과적합 의심
- 특성 중요도 시각화
  ![image](https://github.com/user-attachments/assets/aeb4dad7-1a23-488b-b3b1-0098f21d2a34)
  <br/>
  > ❓ EDA에서 도출해낸 결과와 다르다!
  > 하나의 Decision Tree만을 사용해서 편향된 결과일 가능성이 높음 <br/>
  >    👉🏻 앙상블 기법 중 Random Forest를 사용하자!
  <br/>
  - Random Forest 상세 성능 지표
    ![image](https://github.com/user-attachments/assets/21c90c90-a338-430b-a779-754762455743)
  - Random Forest를 적용한 특성 중요도 시각화
    ![image](https://github.com/user-attachments/assets/66686203-c1ea-4b20-ad9a-a88e1f53f74b)
    -> EDA에서 도출해낸 결과와 비슷한 결과를 보임
  - 과적합 문제를 해결하기 위한 방안: 트리의 최대 깊이(5), 내부 노드의 최소 샘플 수(5) 조정
    ![image](https://github.com/user-attachments/assets/4d75e2b9-99a9-4388-9804-fae739413acc)

<br/><br/>

# 7️⃣ 과적합 해결하기
### SVM (Support Vector Machine)
- 적용 이유: 고차원 데이터의 과적합을 방지해주는 모델
- 정확도
  ![image](https://github.com/user-attachments/assets/4b42e0d6-00bc-4dd0-8fe6-670e0618336d)
- DecisionBoundaryDisplay를 통한 시각화
  - 0) 차원이 맞지 않아 시각화 실패
    ![image](https://github.com/user-attachments/assets/e45589e5-0bed-4ba3-bb9f-6c565264b461)
  - 1) PCA를 사용한 차원 축소
    - 적용 이유: 데이터셋의 차원을 축소하기 위함
      ![image](https://github.com/user-attachments/assets/896b3340-1c3b-4d2d-930d-86bfe2015cb2)
      -> 정확도는 70%, 64%, 70% 로 비교적 낮음
  - 2) LDA를 사용한 차원 축소
    - 적용 이유: PCA는 X 데이터만을 사용해 차원 축소를 하지만, LDA는 X 데이터와 y 데이터를 사용해 차원을 축소하기 때문
      ![image](https://github.com/user-attachments/assets/fed959a9-ddef-4c25-9ea8-5bc2dbf8f282)
      -> 정확도가 83%, 82%, 85% 로 증가


# 7️⃣ 한 줄 회고
| 팀원  | 한 줄 회고                 |
|-------|----------------------------|
| 정수  |  |
| 준희  |  |
| 유경  |  |
