# 카카오테크 부트캠프 해커톤 2회 회고
## 날짜: 2025-02-25 ~ 2025-02-28

### LINK2TRIP
 <img src="img/1.png">

[LINK2TRIP - 깃허브 링크](https://github.com/KTB-post2trip)

### 참가 전 마음가짐
카테부 교육과정 중 열리는 해커톤에 참여하게 되었다. 사실 클라우드를 열심히 학습중이긴 하지만 웹+서버 프로젝트 자체가 이번이 처음이었고, 해커톤 참가도 처음인데다가 클라우드를 다뤄본지도 얼마 되지 않아 걱정이 많았었다. 그래서 마음가짐은 최선을 다해 소통하고, 부딪히고, 부족한 점이 있다면 많이 배우자!!! 였다. 디자인이나 기획 측면 등 개발 외 부분을 도와드릴 수 있으므로 해당 부분도 최대한 돕고자 했다. 그렇게 팀빌딩이 시작되었다.

### 0일차 (팀빌딩, 기획 구체화)
1분씩 자기 PR을 마치고 아이디어 발표자 분들에게 컨택하여 팀을 짜게 되었다. 내가 들어간 팀의 아이디어는 "유튜브 링크를 입력하면, 해당 유튜브의 장소 데이터를 AI를 활용해 추출한 뒤, 장소에 대한 데이터와 맞춤형 여행 계획을 제공하는 서비스" 였다. 

당일 팀이 결성된 후 3일 내에 구성할 수 있도록 팀 그라운드룰 + 역할 분배 + 기획 구체화 회의를 진행했다. 

1. 팀 그라운드 룰 : 노션 템플릿을 활용하여 각 업무별 코드를 부여하고, 코드를 브랜치 이름으로 사용해 진행 상황을 한 눈에 볼 수 있도록 만들었다. 또한 소통을 위해 하루를 한 스프린트로 잡아 전원 회의를 진행하고, 중간중간 소회의 또한 진행하도록 했다. 
2. 역할 분배 : 총 인원 6명, FE 2명 / BE 1명 / AI 2명 / 클라우드 1명으로 분배하였다. 
3. 기획 구체화 : 3일 안에 개발하는 프로젝트인 만큼 국내 여행 한정으로 정했으며, 최소 경로 알고리즘 + 경로 안내는 후순위로 미루었다. 여행 장소 별 일자 수도 제한을 두었다. 

또한 회의 후 간단하게 피그마를 활용한 프로토타입 디자인을 했다. 프론트 담당 한 분과 함께 진행했으며, 신뢰감을 주는 파란색을 활용해 최대한 깔끔하고 직관적으로 사용할 수 있는 UI를 설계하고자 했다. 

### 1일차 (아키텍처 설정, Github action)
 <img src="img/2.png">
아키텍처를 설정하고, 먼저 BE 레포지토리에 깃헙 액션을 이용해 CI/CD를 설정하기로 했다. 

도커 파일로 DB + 백엔드 서버를 통합해 만들어서 자꾸 BE 서버가 만들어질 때마다 DB가 내려가버리는 오류가 있었다. 도커파일을 분리해 compose를 사용함으로써 해결할 수 있었다.

### 2일차 (Flask server)
### 3일차 (마무리, 발표 준비)

### 도전 과제와 해결 방법
- 
### 회고
- 

### 참고 자료 및 링크
- 
