# Robot Vision Course Homework #2

## Due date : 2020-03-30

### Q1.Explain geometric transformations in 3D coordinate. How can we describe the transformations of translation, rigid (Euclidean), similarity, affine, projective? What is the main difference among them?

> geometric object란

기하학 적으로 나타낼 수 있는 선(Line), 평면(Plane), 그리고 3차원 객체(3D object) 등을 나타낸다.
이 중에서 3차원 객체는 3차원 공간 내의 정점들의 집합이며, 표면(surface)에 의해 기술되고, 속은 비었다.

> 3D 에서 geometric trasformation 이란

이러한 3D object들을 어떠한 공식을 통하여 기하학적으로 변형시키는 것을 의미한다. 이것은 2D와 유사한데, 공식으로 보면 그 유사성을 확인할 수 있다.

공식은 2D 에서와 같다.
```
x' = x + t
```
혹은
```
x' = [I t] x̅
```
로 사용된다.

하지만 2D에서와 다른 점이라면 I가 의미하는 값이 2D에서는 2x2이고, 3D에서는 3x3이라는 점이다. 
( 0 역시 zero vector로 의미하는 값이 같다.)

-----

> 아래의 방법들을 설명해보자

공식에 관한 것은 책에 있으니 첨부를 생략하고, 어떤 것들을 의미하는지 작성할 것이다.

- rigid(Euclidean)
    - 가장 기본적인 변환
    - 형태와 크기를 유지한체 위치와 방향만 바꿈
    - 즉, 회전(rotation)과 평행이동(translation)만을 허용
    - 3차원 공간에서 움직이는 물체의 위치 관계를 표현하기 위해서는 3개의 매칭쌍이 필요 ( 3개의 점 )
    
- similarity
    - rigid 변환에 추가적으로 스케일 변화까지 허용
    - 회전(retation), 평행이동(translation), 크기변화(scaling)으로 구성
    - homogeneous 좌표 표현으로 회전, 평행이동, 크기변화를 나타낼 수 있음
    
- affine
    - 직서느 길이(거리)의 비, 평행성(parallelism)을 보전하는 변환
    - 회전, 평행이동, 스케일 뿐만 아니라 shearing, 반전(reflection)까지 포함
- projectivate
    - 3D 의 원근감 변환을 의미
    - 변환은 직선을 지켜 변화한다.

-----
> 위의 방법들의 차이점

Depth of field(이하 DoF) 

- 각각의 Dof
    - translation ==> 3
    - rigid ==> 6
    - similarity ==> 7
    - affine ==> 12
    - projective ==> 15


### Q2 Explain how to derive the camera matrix P in detail. Also, explain all of components of the camera matrix, for example, intrinsic parameters and extrinsic parameters.

카메라 영상은 3차원 공간상의 점들을 2차원 이미지 평면에 투사(perspective projection)함으로써 얻어진다. 예를 들어 카메라 모델에서 이러한 변환 관계는 아래와 같이 모델링 된다. 

![](https://t1.daumcdn.net/cfile/tistory/24758441510E994028)

여기서 [R | t]를 카메라 외부 파라미터 (extrinsic parameter), 그리고 A를 내부 파라미터(intrinsic parameter)라고 부른다.

- 외부 파라미터(extrinsic parameter)
    - 카메라의 설치 높이
    - 방향
    - 위와 같이 카메라의 외부 공간과의 기하학적 관계에 관련된 파라미터


- 내부 파라미터(intrinsic parameters) 
    - 초점거리 (focal length) : fx, fy
    - 주점(principal point) : cx, cy
    - 비대칭계수 (skew coefficient) : skew_c = tanα

### Q3 Explain what is the BRDF. What is the main difference between diffuse and specular reflection?

> BRDF (Bidirectional Reflectance Distribution Function: 양방향 반사도 분포 함수)

불투명한 표면에서 빛이 반사하는 방식을 정의하는 4차 함수이다.
- 입사하는 빛에 따른 반사하는 빛의 비율에 대한 함수
- 빛이 표면에서 어떻게 반사되는지 설명해주는 함수.
- BRDF의 양방향성 : 만약 BRDF가 실제 물리법칙을 따르는 함수로 만들어졌다면, 입사와 반사의 방향이 바뀌어도 그 함수 값을 바뀌지 않는다.

> diffus reflection 과 specular reflection의 차이?

BRDF는 질적으로 다른 3개의 컴퍼넌트로 다룬다.

- BRDF
    1. Diffuse
        - 완전 산란 반사라고 하여 빛이 들어왔을 때 사방으로 모두 반사되는 것을 의미한다.
    2. Mirror ( specular )
        - 완전 거울 반영 반사라고 하며 빛이 들어왔을 때, 들어온 각도 그대로 빛이 반사되어 반대 방향의 같은 각도로 빛이 반사되는 것을 의미한다.
    3. Glossy

### Q4. What is chromatic aberration and vignetting? 

> 모두 상에 맺히는 것과 관련하여 설명할 수 있다.
- chromatic aberration
```
수차(aberration)이란 상을 맺을 때 한점에서 나온 빛이 광학계를 통한 다음 한점에 모이지 않고 영상이 빛깔이 있어 보이거나 일그러지는 현상이 나타나는 것을 말한다.
그 중 색수차는 렌즈의 매질이 가지는 분산 특성에서 비롯된다.
                    - 위키백과 - 
```
색수차란 렌즈의 매질이 가지는 분산 특성에서 비롯된다고 한다. 어떠한 색들이 한번에 렌즈로 들어오게 되면, 색의 파장에 따라서 색이 굴절되는 정도가 다르게 된다. 그렇게 굴절이 다르게 들어오면 빛에 따라 별도의 초점을 갖게 된다. 이것을 색수차라고 한다.
- vignetting

사진 촬영시 주변부의 광량 저하로 이미지의 모서리나 외곽 부분이 어두워지거나 검게 가려지는 현상을 의미한다.
원인은, 렌즈를 통과한 빛은 원형의 상을 맺게 되는데, 이 상을 맺는 범위의 원을 이미지 서클이라고 한다. 렌즈의 이미지 서클의 지름이 화면의 대각선 길이보다 짧아서 모서리 부분에 상이 맺히지 않게 되어 생기는 것이다.

