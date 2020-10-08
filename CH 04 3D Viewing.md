# 3D Viewing



[toc]

## 3D Geometric Transformation

- Homogeneous Coordinates

  <img src="Resources1/30.png" style="zoom:80%;" />

- Translation

<img src="Resources1/31.png" style="zoom:80%;" />

- Scaling

<img src="Resources1/32.png" style="zoom:80%;" />

- Z-Axis Rotation

<img src="Resources1/33.png" style="zoom:80%;" />

<img src="Resources1/36.png" style="zoom:60%;" />

- X-Axis Rotation

<img src="Resources1/34.png" style="zoom:80%;" />

<img src="Resources1/37.png" style="zoom:60%;" />

- Y-Axis Rotation

<img src="Resources1/35.png" style="zoom:80%;" />

<img src="Resources1/38.png" style="zoom:60%;" />

## 3D Viewing

- Transforms the shape and position of an object according to viewing parameters
- Specification of projection type 
  - Parallel VS Perspective
- Specification of viewing parameters
  - Viewer position, viewing plane
- Clipping in 3D
  - Window, view volume
- Projection

## 3D Rendering Pipeline

<img src="Resources1/39.png" style="zoom:60%;" />

## Transformation

<img src="Resources1/40.png" style="zoom:60%;" />

<img src="Resources1/41.png" style="zoom:60%;" />

<img src="Resources1/42.png" style="zoom:60%;" />

## Model Transformation

- Coordinate Systems

  - Local(Modeling) coordinate

  <img src="Resources1/43.png" style="zoom:60%;" />

  - World coordinate : scene

<img src="Resources1/44.png" style="zoom:60%;" />

## Viewing Transformation

- After the modeling transformation stage of the rendering pipeline, all of the object in the scene have been placed within a common coordinate system commonly called *world space*.

- Definition

  - Orient the objects in a coordinate system where the center of projection is located at the origin.

    This coordinate system is called either *eye space or camera space*

  - Mapping from **world** to **viewing** coordinates

## Camera Models

- Real camera models have ...

  - Lens distortion
  - Motion blur

- Pin-hole camera

  - The most basic model :
    - Without lens distortion
    - Without motion blur
    - Ideal projection case

  <img src="Resources1/45.png" style="zoom:60%;" />

## Viewing Parameters

- Position
  - Eye position (px,py,pz)
- Orientation
  - View direction(dx,dy,dz)
  - Up direction(ux,uy,uz)
- Aperture
  - Field of view(xfov,yfov)
- View Plane
  - "look at" point
  - View-plane normal

<img src="Resources1/46.png" style="zoom:60%;" />

## Viewing Transformation

<img src="Resources1/47.png" style="zoom:60%;" />

It`s a convenient coordinate system for orienting the floor and walls. 

The chair and teapot could be easily placed and oriented in this 

coordinate system.



<img src="Resources1/48.png" style="zoom:60%;" />

Specify the image of our model that we desire. 

We'll find this to be much easier when the origin of our coordinate 

system coincides with the camera

## Projection Transformation

- General Definition

  - dimension reduction from m- to n-space (m>n)

- In Computer Graphics

  - map viewing coordinates to 2D screen coordinates

- Projection Plane(View Plane)

  - viewing surface where objects are projected

  

<img src="Resources1/49.png" style="zoom:60%;" />

## Planar Geometric Projection

- Hierarchy of planar geometric projection

<img src="Resources1/50.png" style="zoom:60%;" />

### Parallel & Perspective

- Parallel projection

<img src="Resources1/51.png" style="zoom:60%;" />

- Perspective projection

<img src="Resources1/52.png" style="zoom:60%;" />

### Parallel

#### Parallel Projection

- Center of projection is at infinity

  - Direction Of Projection (DOP)

    - same for all points

    <img src="Resources1/53.png" style="zoom:60%;" />

- Preserves relative dimension
- Accurate views of sides
- DOP at infinity
- Types of parallel projections
  - orthographic projections
  - obliques projections

#### Parallel Projection View Volume

<img src="Resources1/54.png" style="zoom:60%;" />

#### Parallel Projection

- orthographic projections
  - direction of projection is normal to the projection plane (that is, 
    perpendicular to the view plane)
  - architectural, engineering drawings

<img src="Resources1/55.png" style="zoom:60%;" />

- oblique projections
  - projection plane is normal to a principle axis but DOP is not perpendicular to the projection plane
  - only faces of the object parallel to the projection plane are shown true size and shape

<img src="Resources1/56.png" style="zoom:60%;" />

### Perspective Projection

- Map points

  - onto “view plane”
  - along “projectors”
    - emanating from “Center Of Projection” (COP)

  

<img src="Resources1/57.png" style="zoom:60%;" />

- Realistic

  - Lines that are not parallel to the projection plane converge to a vanishing point 

- Principal vanishing point

  - vanishing point of parallel lines which are parallel to the principal axis

- Principal axis: 

  - coordinate axis in which an object is defined

- The number of principle vanishing points 

  **= the number of axes the projection plane cuts**

- How many vanishing points?

<img src="Resources1/58.png" style="zoom:60%;" />

<img src="Resources1/59.png" style="zoom:60%;" />

<img src="Resources1/60.png" style="zoom:60%;" />

<img src="Resources1/61.png" style="zoom:60%;" />

- One point perspective projection

<img src="Resources1/62.png" style="zoom:60%;" />

- Perspective Projection View Volume

<img src="Resources1/63.png" style="zoom:60%;" />

- View Frustum = 절두체
  - 가시부피 설정에 의한 절단

<img src="Resources1/64.png" style="zoom:60%;" />



<img src="Resources1/65.png" style="zoom:60%;" />

<img src="Resources1/66.png" style="zoom:60%;" />

## Viewing Angle & Camera lens

- 초점 거리 50mm 기준
  - 광각렌즈(Wide Angle Lens) : 50보다 작음
  - 망원렌즈(Telescope Lens) : 50보다 큼 
  - Ex. 20mm = 85도 시야각, 85mm = 24도 시야각

<img src="Resources1/67.png" style="zoom:60%;" />

## Perspective vs Parallel

- Perspective projection
  - Size varies inversely with distance
  - Looks realistic
  - Distance and angles are not (in general) preserved
  - Parallel lines do not (in general) remain parallel

- Parallel projection 

  - Good for exact measurements

  - Parallel lines remain parallel

  - Angles are not (in general) preserved

  - Less realistic looking

<img src="Resources1/68.png" style="zoom:60%;" />

## Viewing Specification

<img src="Resources1/69.png" style="zoom:60%;" />

### Specifying the View Plane

1. view reference point (in the world coordinate) 
   - a point on the plane
   - the origin of the View Reference Coordinate system
2. view plane normal VPN (in the world coordinate)
3. view-up vector VUP (in the world coordinate)

<img src="Resources1/70.png" style="zoom:60%;" />

### View reference coordinates

- origin of viewing coordinate system: VRP
- direction of n : VPN
- direction of v : projection of VUP onto projection plane direction of u : VUP$\times$VPN

### Window

- a rectangular region on the view plane
- defined by $(u_{min} ,v_{min} ) (u_{max} ,v_{max})$ in VRC
- the center of window (CW)

<img src="Resources1/71.png" style="zoom:60%;" />

### View Volume

- for clipping
- defined by front and back clipping planes (which are parallel to view plane)

<img src="Resources1/72.png" style="zoom:60%;" />

<img src="Resources1/73.png" style="zoom:60%;" />

### Center Of Projection (COP) / Direction Of Projection (DOP)

- defined by a projection reference point(PRP)
- PRP is specified in the VRC system
- in perspective projection: PRP = COP
- in parallel projection : DOP = (a vector directed from PRP to CW)

<img src="Resources1/74.png" style="zoom:60%;" />

<img src="Resources1/75.png" style="zoom:60%;" />

## Viewing Examples

- Geometric Model
  - model space

<img src="Resources1/76.png" style="zoom:60%;" />

<img src="Resources1/77.png" style="zoom:60%;" />

- Perspective Viewing

  - viewing specification (1)

    ```txt
    VRP(WC) (0,0,0)
    VPN(WC) (0,0,1)
    VUP(WC) (0,1,0)
    PRP(VRC) (8, 6, 84)
    Window(VRC) (-50, 50, -50, 50)
    perspective projection
    ```

    

  - viewing specification (2)

    ```txt
    VRP(WC) (0,0,54)
    VPN(WC) (0,0,1)
    VUP(WC) (0,1,0)
    PRP(VRC) (8, 6, 30)
    Window(VRC) (-1, 17, -1, 17)
    perspective projection
    ```

    <img src="Resources1/78.png" style="zoom:60%;" />

- Perspective Viewing

  - viewing specification

    ```txt
    VRP(WC) (16,0,54)
    VPN(WC) (0,0,1)
    VUP(WC) (0,1,0)
    PRP(VRC) (20, 25, 20)
    Window(VRC) (-20, 20, -5, 55)
    perspective projection
    ```

    - view point change

    - actually it’s just one-point perspective

      

<img src="Resources1/79.png" style="zoom:60%;" />

- Two-Point Perspective Viewing

  - viewing specification

    > VRC(WC) (16,0,54)
    >
    > VPN(WC) (1,0,1)
    >
    > VUP(WC) (0,1,0)
    >
    > PRP(VRC) (0, 25, 20$\sqrt{2}$)
    >
    > Window(VRC) (-20, 20, -5, 35)
    >
    > perspective projection

    <img src="Resources1/80.png" style="zoom:60%;" />

  - view plane change

<img src="Resources1/81.png" style="zoom:60%;" />

## Mathematics of Projection

- Parallel projection

<img src="Resources1/82.png" style="zoom:60%;" />

- Perspective projection

  

<img src="Resources1/83.png" style="zoom:60%;" />

<img src="Resources1/84.png" style="zoom:60%;" />

## Normalizing Transformation

- Normalizing Transformation

  transforms an arbitrary parallel- or perspective- projection view volume into the **canonical view volume**

<img src="Resources1/85.png" style="zoom:60%;" />

- Parallel Projection
  - Transformation sequence
    1. translate VRP to the origin of the WC. 
    2. rotate VRC such that *n* axis = *z* axis, *u* axis = *x* axis and *v* axis = *y* axis.
    3. shear so the direction of projection parallel to the *z* axis. (not necessary for orthographic projections) 
    4. translate and scale into the parallel-projection canonical view volume.

<img src="Resources1/86.png" style="zoom:70%;" />

	> - 물체에 대한 이동, 크기조절, 반사변환으로 간주
	>
	> - Reflection: 정규화 가시부피는 왼손좌표계
	>
	> - 결과적인 좌표계 = 절단 좌표계(CCS: Clip Coordinate System)

- Perspective Projection

  - Transformation sequence

    1. translate VRP to the origin of the WC. : *T*(-VRP)

    2. rotate VRC such that *n* axis = *z* axis, *u* axis = *x* axis and *v* axis = *y* axis.

    3. translate such that COP (= PRP) is at the origin.

       ​				:*T*(-PRP)

    4. shear so the center line of the view volume becomes the *z* -axis.

    5. scale such that the view volume becomes the canonical perspective view volume

- 일반적 형태의 가시부피: void glFrustum(GLdouble left, GLdouble right, 

  GLdouble bottom, GLdouble top, GLdouble near, GLdouble far); 

<img src="Resources1/87.png" style="zoom:70%;" />

## Perspective Projection of OpenGL

<img src="Resources1/88.png" style="zoom:70%;" />

- 원근분할(Perspective Division, Homogenization)
  - 동차좌표의 마지막 요소로 이전 요소를 나누는 작업
  - 절단이 동차좌표에서 이루어지기 때문에 절단 이후로 미루어 짐.

<img src="Resources1/89.png" style="zoom:70%;" />

- 원근변환
  - 어파인 변환이 아님: 마지막 행이 (0, 0, 0, 1)이 아님
  - 3차원 좌표관점: x' = x/(z/d): 비선형 변환
  - 4차원 동차좌표 관점: 선형변환

<img src="Resources1/90.png" style="zoom:70%;" />

## Normalized View Frustum on Perspective Projection

<img src="Resources1/91.png" style="zoom:70%;" />

- 전방 절단면에 비해 후방 절단면이 줄어듬. 
  - 멀리 있는 것이 작게 보야야 함.

<img src="Resources1/92.png" style="zoom:70%;" />

- T 행렬
  - Z 값에 영향을 미침: 원래의 물체 정점의 깊이 z와 정규화 변환 후의 물체 정점의 깊이 z'의 관계

<img src="Resources1/93.png" style="zoom:70%;" />

## From Viewing Coord. To Clipping Coord.

<img src="Resources1/94.png" style="zoom:70%;" />

- 높이: 멀어질수록 전봇대 높이가 낮아짐(원근변환)

- 간격:더욱 촘촘해 짐에 유의(비선형 변환) 
- 전방 절단면: 시점에서 멀리, 물체에 최대한 근접시켜 설정
  - 물체간격이 상대적으로 보존, 지-버퍼 처리에 유리

<img src="Resources1/95.png" style="zoom:70%;" />

