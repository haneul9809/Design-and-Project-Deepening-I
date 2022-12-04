# Design-and-Project-Deepening-I
PC 사용자를 위한 자세교정 웹페이지 제작
## 산출물
https://konyang-my.sharepoint.com/:f:/g/personal/19615050_konyang_ac_kr/ErBuJj8gOFdKjAVmlokAKKEBne1tA_wxXjmkAC1v0KYd-Q?e=62JzJd

## 🗓️ 개발 기간

2021/4/6 ~ 2021/6/15

## 📜서비스 내용

- 문제 제기
    - 코로나19의 여파로 재택근무, 온라인 수업 수요가 늘면서 노트북 성수기에 진입했다.그에 따른 온라인 수업 장기화로 ‘신체 불균형’이 우려된다.
        - 운동량은 적으나 컴퓨터, 스마트폰 사용량이 많아 몸에 문제가 생긴다. 특히 어깨랑 목 통증을 호소하는 경우가 증가했다.
    - 하루 평균 앉아서 보내는 시간(출처 : 한국 보건복지부 질병관리본부)
        - 20대 : 8시간 42분
        - 30대 : 7시간 36분
        - 40대 : 7시간 18분
- 문제 해결(기능과 기대효과)
    - 바른자세 6계명
        - 집중력을 좌우하는 목과 등 자세
            - 집중력 향상을 위해 등받이에 기대어 앉기
        - 허리 건강을 돕는 틸트 활용
            - 척추 스트레칭을 위한 틸트 기능 활용하기
        - 무릎 각도 90도 유지하기
            - 혈액 순환에 도움을 주는 90도
        - 팔과 어깨가 편한 자세
            - 책상이나 팔걸이에 자연스럽게 지지하기
        - 바른 자세의 기본은 시선
            - 허리를 펴고 정면을 바라보는 자세
    - 기능
        - 웹
            - 자세 인식 모니터링
            - 자세 인식 후 경고음 재생
        - 딥러닝
            - Teachable Machine 사용
            - 정확한 자세 인식
    - 필요 조건
        - 자세 인식 모니터링에 버벅임이 없어야 한다.
        - 자세 인식 후 경고음이 원활하게 재생되어야 한다.
        - 티처블머신을 활용한 자세 인식이 정확해야 한다.
    - 기대효과
        - 코로나19로 인한 노트북, PC 사용자들의 신체 불균형을 예방할 수 있다.
        - 웹페이지를 활용하여 경제적이고, 정확성 높은 인식률로 자세를 교정할 수 있다.
        - 자세 교정 뿐 아니라 다양한 용도로 활용할 수 있는 방안이 있을 것이다.

## ⚙️ 기술 스택

- 웹 페이지 구성
    - Front-end
        - HTML, CSS, JavaScript, Bootstrap
    - Back-end
        - Netlify
- Deep Learning
    - Teachable Machine

## **👫 팀 구성**

성유정 : Teachable Machine

최하늘 : Teachable Machine, Web

## 💻 개발 내용

1. 시스템 구성도
<img width="1404" alt="스크린샷 2022-12-04 오후 12 20 32" src="https://user-images.githubusercontent.com/67767912/205473721-09e5e131-c6ce-45eb-a789-12b5103ed31d.png">

2. Teachable Machine 개발
    
    <img width="247" alt="스크린샷 2022-12-04 오후 12 25 36" src="https://user-images.githubusercontent.com/67767912/205473729-3597f73a-5aa7-4431-bfca-0747fda1c31c.png">

    
    - 클래스별 정교화로 정확도 상승
        - 클래스별 정확도는 테스트 샘플을 사용해 계산
    <img width="215" alt="스크린샷 2022-12-04 오후 12 26 38" src="https://user-images.githubusercontent.com/67767912/205473734-071b00a9-1b4f-41d0-94e0-192702170014.png">

    
    - 예측의 정확도를 높여 클래스 혼동 하락
        - 모델의 예측이 얼마나 정확한지 요약하는 혼동 행렬입니다. 이 행렬을 사용해 모델이 어떤 클래스에서 혼동을 일으키는지 파악할 수 있습니다.
    
    <img width="243" alt="스크린샷 2022-12-04 오후 12 28 40" src="https://user-images.githubusercontent.com/67767912/205473740-e9fe4341-517e-4e25-9d9a-86d56b3542e9.png">

    - 학습 과정 정교화로 정확도 상승
        - 에포크별 정확도는 모델이 학습 과정에서 정확하게 분류한 비율입니다. 모델의 예측이 완벽하다면 정확도는 1입니다.
    <img width="222" alt="스크린샷 2022-12-04 오후 12 29 43" src="https://user-images.githubusercontent.com/67767912/205473745-0fd4cf1a-5bc8-4010-a3ed-abfd8070343f.png">

    
    - 샘플 세트 분류로 예측률 상승
        - 에포크별 손실이란 모델이 주어진 샘플 세트의 분류를 정확히 예측하도록 얼마나 효과적으로 학습했는지 보여주는 측정 항목입니다. 모델의 예측이 완벽하다면 손실은 0입니다.
    
    <img width="325" alt="스크린샷 2022-12-04 오후 12 30 50" src="https://user-images.githubusercontent.com/67767912/205473750-df8cf0a0-568c-45df-af4d-ea1787cd9620.png">

    - correct(283포즈 샘플), head_right(205포즈 샘플), head_left(299포즈 샘플), teck_neck(151포즈 샘플), shoulder_right(229포즈 샘플), shoulder_left(240포즈 샘플)
    

3. 웹 개발
    <img width="949" alt="스크린샷 2022-12-04 오후 12 33 27" src="https://user-images.githubusercontent.com/67767912/205473756-044c3f2a-da60-4458-9872-6e51d60e4868.png">

    
    - HTML, CSS, Javascript로 기본적인 틀 구성
    - 티처블머신과 웹 연동
    - 바르지 않은 자세에서 경고음 재생
    - 사이트 배포를 위해 Netlify 사용
    
4. 프로그램 시연을 하기 위해 20명 test
    
    https://youtu.be/CodGrCT6Svg

https://user-images.githubusercontent.com/67767912/205473812-f11d46da-e537-4a83-9ce7-db1ec2beab3c.mp4

    https://youtu.be/lu6W_NCEVhs
    - 시연 결과, 사용자가 95% 정도 정확하다고 느꼈음.
    
## **💻 내가 담당한 파트**

[Teachable Machine 개발](https://www.notion.so/Teachable-Machine-8752c19ee4004a339d85409ba949e9a1) 

[웹 개발](https://www.notion.so/14f11b99520c4b77842b77dca23d6488) 

## ✏️후기 및 에세이

티처블머신을 활용하여 인공지능을 학습시켜 생성하고 웹페이지에 띄우는 프로젝트를 진행하면서 인공지능과 가까워지는 시간을 가지게 되었다. 좀 멀게 느껴졌는데 색다른 재미를 느낄 수 있었고 마지막에 알림음을 넣는 코드 부분에 자꾸 오류가 나서 밤을 샜던 기억이 너무 생생하다. 알림음을 무사히 넣었을 때 그 짜릿함을 잊을 수가 없다. 그리고 이 프로젝트로 다양한 사용자에게 적용이 가능하도록 만드는 부분이 어려웠지만 다양한 데이터 수집으로 해결해낼 수 있었다.

## **🗓️ 추진 일정**
<img width="1087" alt="스크린샷 2022-12-04 오후 12 39 26" src="https://user-images.githubusercontent.com/67767912/205473769-d8f5cedb-3142-4692-8c06-5627d00cd877.png">
