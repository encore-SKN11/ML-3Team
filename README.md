# 데이터로 보는 폐암 진행 속도의 결정 요인

# 1️⃣팀 소개
> SK네트웍스 Family AI 캠프 11기  <br/>
> 팀 명: 3조 <br/>
> 기간: 2025.03.10 - 2025.03.14<br/>

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

# 2️⃣프로젝트 개요
폐암은 전 세계적으로 암 사망의 주요 원인으로 뽑힐 만큼 조기 발견과 치료가 생존율을 결정짓는 중요한 질환 중 하나이다. 폐암은 조기에 발견하지 않으면 빠르게 진행되며, 생존에도 큰 영향을 미치는 치명적인 질환이다. 폐암이 얼마나 빨리 진행되는지는 다양한 변수에 의해 달라질 수 있다. 본 프로젝트에서는 환자의 환경적·유전적 요인 및 생활 습관이 폐암 진행 속도에 미치는 영향을 분석하고, 데이터 탐색적 분석(EDA)을 통해 주요 요인을 시각적으로 이해하는 것을 목표로 한다.
<br/>
<br/>
![Image](https://github.com/user-attachments/assets/2b475128-f22e-45dc-9017-f8018296c489)
![Image](https://github.com/user-attachments/assets/2b991392-3030-4353-8ef6-e28dc7ff6ade)
## 🚀프로젝트명
- 데이터로 보는 폐암 진행 속도의 결정 요인
<br/>

## 📂사용한 데이터
-  [Lung Cancer Prediction](https://www.kaggle.com/datasets/thedevastator/cancer-patients-and-air-pollution-a-new-link/data?status=pending&suggestionBundleId=178)
<br/>

# 3️⃣기술 스택
<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white">
  <img src="https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=vscode&logoColor=white">
  <img src="https://img.shields.io/badge/numpy-%235865F2.svg?style=for-the-badge&logo=numpy&logoColor=white">
</p>
<p align="center">
  <img src="https://img.shields.io/badge/pandas-%23000000.svg?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black">
</p>
<br/><br/>

# 4️⃣WBS
| 작업 명                | 시작일 | 종료일 | 담당자         | 산출물        |
|-------------------------|-------|-------|-----------------|---------------|
| 프로젝트 주제 선정       | 03-10 | 03-11 | ALL             | 주제          | 
| 데이터 수집              | 03-11 | 03-11 | ALL             | csv           | 
| 데이터 시각화            | 03-12 | 03-13 | ALL             | Jupiter Notebook 코드   | 
| 데이터 전처리            | 03-13 | 03-13 | ALL             | Jupiter Notebook 코드     | 
| 문서 작업 및 발표 준비   | 03-13 | 03-13 | ALL             | Jupiter Notebook 코드     | 
| 최종 점검                | 03-13 | 03-13 | ALL             |               | 

<br/><br/>

# 5️⃣분석 방법
## 1. 데이터 로드
- csv 데이터 파일 로드

## 2. 데이터 구조 확인 및 기초 통계 확인
- 데이터 구조 파악을 위한 head, info, describe 함수 사용

## 3. 결측치 탐색
- isnull 함수를 사용해 결측치 값이 존재하는지 확인

## 4. 데이터 시각화를 통한 탐색
- 데이터를 기반으로 폐암 진행을 예측할 수 있는 패턴을 분석
- 폐암 예방 및 치료에 활용할 수 있는 인사이트 제공
<br/><br/>

# 6️⃣시각화 결과

## 1. 데이터 로드
![eda01](https://github.com/user-attachments/assets/72eba9e5-113b-4fa5-93ce-ae60fe31b4dc)

<br/><br/>

## 2. 데이터 구조 확인 및 기초 통계 확인
- 2-1. 데이터 구조 확인 (info)
![eda02](https://github.com/user-attachments/assets/928c7eca-61c6-4f48-8a22-3fd65267f908)

<br/>

- 2-2. 데이터 구조 확인 (describe)
![eda03](https://github.com/user-attachments/assets/efa689ac-3159-4ff1-9d86-a5419743be9b)
![eda04](https://github.com/user-attachments/assets/4365be22-8aa5-4e38-a03d-1e053658b11e)

<br/><br/>

## 3. 결측치 탐색
- 3-1. 데이터 결측치 확인
![eda05](https://github.com/user-attachments/assets/ba6b8933-04b1-4cea-bea2-2868af602994)

<br/><br/>

## 4. 데이터 시각화를 통한 탐색

### 4-1. 전체 데이터 Heatmap
![eda06](https://github.com/user-attachments/assets/37e43b2a-9041-46f4-b9a8-1c07f102283f)

<br/>

- 4-1-1. 상대적으로 연관 없는 컬럼 삭제하기
![eda07](https://github.com/user-attachments/assets/a88eb5fc-fd5e-4d44-ab08-6f30290cbe2f)

<br/>

### 4-2. 연령별 폐암 환자 분포 시각화
![eda08](https://github.com/user-attachments/assets/f1d2572e-7e02-4518-90b2-fb3f0b0ede27)

<br/>

- 4-2-1, 20대 미만과 20대 이상 중 Alhocol use, Smoking 컬럼 시각화
![eda10](https://github.com/user-attachments/assets/079ebfa4-425c-4c3b-8bd3-21a00d1a3947)
![eda11](https://github.com/user-attachments/assets/3706dc57-6a3c-4c53-ad6c-28c90ae0e3cd)

<br/><br/>

### 4-3. 연관있는 컬럼들 시각화
![eda12](https://github.com/user-attachments/assets/c7c7bec3-51d6-4f29-817d-ce3f91f214fc)

<br/><br/>

### 4-4. 폐암 진행 Level
![eda13](https://github.com/user-attachments/assets/c471163a-2f25-46dc-9120-bba1aa54970a)

<br/>

- 4-4-1. 각 특성에 따른 폐암 진행 Level 시각화
![eda14](https://github.com/user-attachments/assets/711b8281-25b3-4851-832f-c1d3180b592a)

<br/>

- 4-4-2. 공기 오염도에 따른 Level 시각화
![eda15](https://github.com/user-attachments/assets/f41421ee-4b51-456b-a8ab-973721c7bc2c)

<br/>

- 4-4-3. 각 특성별 폐암 진행 중 Level 3 분포 시각화
![eda16](https://github.com/user-attachments/assets/40222c9c-aa89-4c32-b6df-ad05f0e94366)


<br/><br/>

# 한 줄 회고
| 팀원  | 한 줄 회고                 |
|-------|----------------------------|
| 정수  | 팀원들 덕분에 협업이 매끄럽게 진행된 것 같아서 고맙습니다 |
| 준희  | 데이터 분석과 전처리 과정을 더 많이 이해하는 시간이었고, 협업이 잘 진행되면서 더 많은 인사이트를 도출하고 싶은 욕심이 생겼습니다 |
| 유경  | 컬럼 간의 연관관계를 분석해서 그래프로 어떻게 시각화해야 전달하고자 하는 바를 효과적으로 전달할 수 있을지 많이 고민했던 프로젝트였습니다! 그리고 모두들 본인의 역할을 책임감있게 수행해주셔서 수월히 협업이 진행되었습니다~ 다들 수고하셨어요🤩 |
