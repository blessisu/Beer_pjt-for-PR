# 비어있는 편의점 🍻

> 협업 필터링 기반 맥주 추천 시스템
>
> 맥주 상세 정보, 리뷰, 맥주 친구 찾기 등의 기능 제공



## 0. 프로젝트 개요



1. **기획 의도**

   세상의 맥주는 많고, 마실 친구도 많습니다.

   하지만 그 중에 내가 마실 맥주는 무엇이며, 나와 마실 친구는 누구일까요?



2. **서비스**

   각 사용자가 매긴 맥주 점수 데이터를 모아 협업 필터링을 통해 사용자 맞춤 맥주를 추천합니다.

   사용자 위치를 기반으로 최대 1km 반경의 맥주 친구도 추천해줍니다.

   

   

   🍺 저희 서비스를 통해 맥주를 잘 아는 유저에게는 정보 나눔의 기회, 기록의 즐거움과 새로운 친구를 맥주를 잘 모르는 유저에게는 빅데이터를 통한 맞춤 맥주 추천을 제공할 것입니다. 





> UCC 

https://youtu.be/8EtcKhJcVsk



> 배포 사이트

[https://j5c205.p.ssafy.io/](https://j5c205.p.ssafy.io/api/login/)



## 1. 역할

💻 

- 추천 알고리즘, 채팅을 제외한 모든 백 로직
- 회의, Readme 등 서기



## 2. 개발 도구

- Vue, Vuex, Vuetify

- Django, MySQL

- JIRA, GIT, AWS



## 3. ERD

![ERD](/assets/ERD.png)



## 4. figma / API 문서



> 컴포넌트 구조 - figma

https://www.figma.com/file/zw33mEpult6Pk8Evds8jpR/'%EB%B9%84%EC%96%B4'%EC%9E%88%EB%8A%94-%ED%8E%B8%EC%9D%98%EC%A0%90?node-id=9%3A11



> API 문서

https://www.notion.so/94e69bf4ec6b4acb9ef8a7c46554279d?v=87a48277b93940b3a6ab2c63c5de1506





## 5. 기능

**Beer**

- 전체 맥주/상세 맥주

   ![image-20211008000347538](/images/image-20211008000347538.png)

  ![image-20211008000410324](/images/image-20211008000410324.png)

  전체 맥주 목록에서 맥주를 클릭하면 상세 맥주 정보를 볼 수 있습니다.



- 맥주 검색

  ![image-20211008000549570](/images/image-20211008000549570.png)

  화면 상단의 검색창을 통해 맥주를 검색할 수 있습니다.

  

- 맥주 찜하기

  ![image-20211008000653673](/images/image-20211008000653673.png)

  ![image-20211008000743413](/images/image-20211008000743413.png)

맥주 상세 정보에서 찜하기를 누르면 내가 찜한 맥주 목록에서 해당 맥주가 보여집니다.



- 맥주 추천 (협업 필터링X)

  ![image-20211008000932481](/images/image-20211008000932481.png)

유저들이 가장 리뷰를 많이 쓴 맥주, 찜이 많은 맥주, 맥주 score가 가장 높은 맥주 최대 6개를 메인 페이지에서 보여줍니다.

-

--------------------



**User**

- 회원가입

   ![image-20211007234902561](/images/image-20211007234902561.png)

  아이디와 닉네임이 모두 기존의 유저와 겹치지 않을 경우만 회원가입이 가능합니다.

  

- 회원가입 - 선호도

  ![image-20211007235955499](/images/image-20211007235955499.png)

  자신이 좋아하는 맥주 종류를 세 가지 선택할 수 있습니다. 

  잘 모르는 경우는 "모름"을 선택할 수 있고,

  마우스를 올리면 상세 설명과 대표 맥주를 알 수 있습니다.

  

- 회원가입 - 선호도

  ![image-20211008000218802](/images/image-20211008000218802.png)

  앞에서 선택한 취향 기반으로, 모르는 것을 고를 경우 대표적인 맥주 몇 가지로 이상형 월드컵 형식의 선호도 조사를 한 번 더 조사합니다.

  여기서 선택된 맥주에는 5점이 부여되어, 첫 추천에 기반이 됩니다.



- 회원 정보 수정

![image-20211008001052002](/images/image-20211008001052002.png)

![image-20211008002339583](/images/image-20211008002339583.png)

회원 정보 수정란에서 닉네임/선호도 수정 및 회원탈퇴가 가능합니다.



-----------



**Board**

- 맥주 별점 + 리뷰

  ![image-20211008002703764](/images/image-20211008002703764.png)

  맥주 상세 페이지에서 간단히 댓글 형식으로 별점과 함께 마셔본 맥주에 대한 평가를 남길 수 있습니다. 여기에 남긴 리뷰는 점수가 사용자 맞춤 맥주를 추천할 때 이용됩니다.



------------------------



**Feed**

- 피드 작성 / 피드 댓글 작성

  ![image-20211008003652200](/images/image-20211008003652200.png)

  자유롭게 피드를 쓰고 다른 사용자와 댓글을 주고받을 수 있습니다.



------------



**Chat**

- 채팅

  ![image-20211008005022758](/images/image-20211008005022758.png)

가입한 유저들끼리 상호 채팅이 가능합니다. 

유사도를 통해 추천받은 유저와 혹은 거리가 가까운 유저와 채팅을하여 맥주 친구를 찾는 기능입니다.



-----------



**Recommend**

- 맥주 추천 기능

  ![image-20211008010000444](/images/image-20211008010000444.png)

사용자들이 작성한 리뷰를 기반으로, 높은 점수를 줄 것으로 예상되는 맥주들을 추천해줍니다.



- 빅데이터 기반 친구 추천 기능 (CSS 오류)

  ![image-20211008010015173](/images/image-20211008010015173.png)

사용자들이 작성한 리뷰를 기반으로, 자신과 맥주 점수가 유사한 유저들을 추천합니다.



- 위치 기반 친구 추천 기능

  ![image-20211008010748297](/images/image-20211008010748297.png)

위치를 동의한 사용자들은 반경 1km 이내의 사용자들에게 자신의 위치를 보여줍니다.

가까이 살고있는 유저와 맥주 한 잔을 하고 싶을 경우 맥주팟에서 사람들의 위치를 확인하고, 

채팅을 이용해 약속을 잡아 맥주를 마실 수 있습니다.



## 6. 느낀점



- api를 restful 하게 만드는게 생각보다 신경쓸 것이 많다는 것을 느꼈고, 시간이 촉박한 프로젝트인만큼 프론트와 백의 소통, 선택과 집중의 중요성과 필요성을 알게됨.
