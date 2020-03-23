# Robot Vision course Homework #1
## Due date : 2020-03-23

<br/>

## Q1. What is computer vision?

> 컴퓨터 비전이란, 사람이 보고 판단하는 다양한 상황을 시스템을 통해 대신하기 위한다. 따라서 여러가지 방법으로 이미지를 가공하여 정보를 받고, 무언가를 판단하는 것이다.

### 사람의 시야와 컴퓨터의 시야

사람은 어떠한 물체를 볼 때 3D인 상태로 그 물체를 보고 판단하게 된다. 하지만 시스템일 경우, 그 물체를 볼 때 2D인 상태로 물체를 보고 판단하게 되는데, 이러한 점이 computer vision에서의 어려움이라고 생각한다. 따라서 요즘 많이 연구가 되는 3D computer vision이 그 어려움을 많이 해결해 줄 것이라고 생각한다.

### computer vision을 부르는 또 다른 이름
- Image Understanding
- Machine Vision
- Robot Vision
- Image Analysis
- Video Understanding



## Q2  What is image processing, machin learning, computer graphics? What is the relationship with computer vision?

- image processing
    - 받는 이미지를 다양하게 변화시켜 강조, 개선, 압축 하거나 이차원 적인 응용을 위해 이미지를 변형하는 것
- machin learning
    - 어떠한 문제를 해결하기 위해 데이터를 이용하여 컴퓨터 스스로가 학습하는 것
- computer graphics
    - 컴퓨터를 이용하여 이미지를 만들어 내는 일련의 과정과 모든 기술을 칭하는 것

> **computer vision 이란** 시스템이 사람처럼 어떠한 이미지를 보고 그 이미지의 특징이나 상황 등을 이해할 수 있도록 하는 것이다.

### 따라서, computer vision은 위의 세 기술과 어떻게 관련이 있는지?

- image processing
    - 컴퓨터가 이미지를 볼 때 불필요한 데이터를 제거하거나 필요한 데이터를 강조하는 등의 이미지 변형을 일으켜, 컴퓨터가 보다 필요한 데이터를 받을 수 있도록 한다.
- machin learning
    - 어떠한 이미지를 보고 그 이미지의 특징이나 상황 등을 이해할 수 있도록 컴퓨터가 받은 데이터를 바탕으로 스스로 학습하고 문제를 해결한다.
- computer graphics
    - 컴퓨터가 판단한 상황이나 해결한 문제를 사람이 다시 볼 수 있도록 구성한다.

## Q3 what are nearby intelligent systems using computer vision? Find more than 5 systems using computer vision

- 자율 주행 자동차
- 글자 인식 (OCR)
- 반려 동물 cctv
- 실시간 교통상황 알림
- 신체 인식 게임

 
## Q4 What computer vision algorithms are applied to those systems? Find at least 3 algorithms for each system

- 자율 주행 자동차
    - Hough transform (차선인식)
    - Yolo (차량인식)
    - LightNet(신호 인식)
- 글자 인식 ( 글자 인식하여 문자로 변경 등)
    - CTC(글자간 사이 파악)
    - Hough transform (직선 모양을 검출해 불필요한 선을 제거)
    - Contour (색깔로 분석한 등고선 형태의 경계 그룹 만들기, 형태 탐지)
- 얼굴 인식 (카메라 자동 초점 등)
    - facenet (face feature)
    - mtcnn (face detection)
    - deep sort (face tracking)
- 객체 탐지 (무인 상점 등)
    - CNN (Convolutional Neural Network)
    - RPN(Region Proposal Netowrk) (영역 제안)
    - Faster RCNN(이단계 방식의 객체 탐지)
- 신체 인식 (게임, 재활훈련 등)
    - openpose (사람의 얼굴, 신체부위, 손가락을 추정)
    - DensePose (3D 표면에 매핑, 자세추정)
    - Total Capture (얼굴 표정, 몸 동작 및 손짓 등을 포착하여 표현)


## Q5 Waht is the computer vision application that you are most interested in ?

> 사람, 딥러닝, opencv, python, video 

일반적인 물체에 대한 인식과 영상처리 보다는 **사람**과 관련하여 사람의 행동을 판단하고, 혹은 만들어 내는 연구에 관심이 있습니다.
 다양한 공부 중 요즘 많이 연구 되는 **딥러닝**에 관한 연구도 함께 하고 싶습니다. 또한 프로젝트를 할 때에는 **python** 언어에 더 흥미가 있으며, 따라서 python을 이용한 **opencv**를 이용하여 프로젝트를 진행한다면,
 보다 더 완성도 높은 프로젝트를 진행할 수 있습니다. 현재 image에 관련한 것만 해도 상당히 많은 양의 공부 내용이 있지만 
 computer vision 이라는 분야에 조금 더 익숙해진다면 image 보다는 **video**에 관련한 연구를 심도 있게 진행하고 싶습니다.