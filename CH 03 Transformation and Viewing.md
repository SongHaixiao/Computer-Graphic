# 2D Transformation and Viewing

[toc]

## What is redering?

The collection of operations necessary to project a view of an object onto a screen

- Viewing Transformation

- Visible Surface Determination

- Shading and Illumination



## 3D Rendering Pipeline

<img src="Resources1/14.png" style="zoom:60%;" />

<img src="Resources1/15.png" style="zoom:60%;" />

## Geometric Transformation

- 2D geometric transformation : for 2D graphics
- 3D geometric transformation : for 3D modeling and rendering

## Representation of 2D objects

- Graphical Objects
  - geometric primitive : point, line, polygon, curve
  - composite : diagrams, video signals
- Mathematical Representation
  - points : (x,y)
  - lines:
    - $y = mx + B$
    - $Ax + By + C = 0$
    - $L = P + tT $: parametric vector representation​
    - $L = P_1 + t(P_2-P_1) $: line segment​

## 2D Geometric Transformation

- altering or manipulation display
- reducing size of a graph
- rearranging design patterns
- animation(change of shape)

## Homogeneous Coordinates

- It is possible to represent scaling, rotation, and translation in a matrix form.(Multiplication)

- 3차원좌표 (x,y,z), 4차원좌표 (x,y,z,w)→3D(x/w,y/w,z/w)

- $동차좌표계의 좌표 = p * WorldMat * ViewMat * ProjectionMat$

- 해당좌표에서 3D 좌표를 얻기위 w로 나눔

  - 월드 공간, 카메라 공간의 w = 1
  - 투영 공간의 w의 값은 카메라로 부터의 거리에 따라 달라짐

  <img src="Resources1/16.png" style="zoom:60%;" />

## Basic Transformation

- Transform P(x,y) to P'(x',y')

  e.g. $P' = [x',y',1]^T$, $ P = [x,y,1]^T $ then $P'=M\cdot P$

  

- Translation

<img src="Resources1/17.png"/>

- Scaling

  <img src="Resources1/19.png"/>

- Rotation

<img src="Resources1/18.png"/>

- Shearing

  - shear along x-axis shear along y-axis

  - $x' = x + ay, y'=y       x' = x, y' = y + bx$

    

<img src="Resources1/20.png" style="zoom:60%;" />

## Composite Transformation

- Composition(Concatenation):

  **Product of individual transformation matrices**

- Translation:
  $$
  M = T(tx_1,ty_1) \cdot T(tx_2,ty_2) = T(tx_1+tx_2,ty_1+ty_2)
  $$
  

<img src="Resources1/21.png" style="zoom:60%;" />

- Scaling:
  $$
  M = S(Sx_2,Sy_2) \cdot S(Sx_1,Sy_1) = S(Sx_1Sx_2,Sy_1Sy_2)
  $$
  <img src="Resources1/22.png" style="zoom:60%;" />

- Rotation
  $$
  M = R(\theta_2) \cdot R(\theta_1)=R(\theta_1+\theta_2)
  $$
  

<img src="Resources1/23.png" style="zoom:60%;" />

- Scaling relative to a fixed point
  $$
  M = T(tx,ty) \cdot S(Sx,Sy) \cdot T(-tx, -ty)
  $$
  <img src="Resources1/24.png" style="zoom:60%;" />

- Rotation about a pivot point
  $$
  M = T(tx,ty) \cdot R(\theta) \cdot T(-tx,-ty)
  $$
  

<img src="Resources1/25.png" style="zoom:60%;" />

<img src="Resources1/26.png" style="zoom:70%;" />

## Concatenation Properties

- Associativity(결합)

  - $(A \cdot B) \cdot = A \cdot (B \cdot C)$

- Commutativity(교환)

  - $T(tx_1,ty_1) \cdot T(tx_2,ty_2)=T(tx_2,ty_2) \cdot T(tx_1,ty_1)$
  - $S(Sx_1,Sy_1) \cdot S(Sx_2, Sy_2) = S(Sx_2, Sy_2) \cdot S(Sx_1, Sy_1)$
  - $R(\theta_1) \cdot R(\theta_2) = R(\theta_2) \cdot R(\theta_1)$
  - $S(Sx,Sy) \cdot R(\theta) = R(\theta) \cdot S(Sx,Sy) \quad with \quad Sx = Sy$

  

## Transformation

<img src="Resources1/27.png" style="zoom:100%;" />

- Rigid Body Transformation(강체 변환)

  - 이동 변환, 회전 변환
  - 물체 자체의 모습은 불변

- Similarity Transformation(유사 변환)

  - 강체변환 + 균등 크기조절 변환, 반사 변환
  - 물체면 사이의 각이 유지됨
  - 물체 내부 정점간의 거리가 일정한 비율로 유지됨

- Affine Transformation(어파인 변환)

  - 유사 변환 + 차등 크기 조절 변환, 전단 변환

  - 물체의 타입이 유지

    - 직선은 직선으로, 다각형은 다각형으로, 곡면은 곡면으로
    - 평행선이 보존
    - 변환행렬의 마지막 행이 항상(0,0,0,1)

    

- Perspective Transformation(원근변환)

  - 평행선이 만남
  - 직선이 직선으로 유지
  - 변환행렬의 마지막 행이 (0,0,0,1) 아님

- Linear Transformation(선형변환)

  - 어파인 변환 + 원근 변환

  - 선형 조합(Linear Combination)으로 표시되는 변환

    - $L(a+b)=L(a)+L(b) \quad \quad L:Linear Mapping$

    - $L(sa) = sL(a)$

      a,b를 정점이라 했을 때, 두 점의 합의 L한 것과 각각 L한것을 더한 것이 같고 스칼라 값 s를 곱한 것이 같은 속성을 유지하는 변환

## 2D Rendering Pipeline

<img src="Resources1/28.png" style="zoom:60%;" />

## Coordinates

- Local coordinate system = Modeling coor system
- World coordinate system = Global coor system
- View coordinate system

<img src="Resources1/29.png" style="zoom:60%;" />