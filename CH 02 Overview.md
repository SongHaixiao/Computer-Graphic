# Overview

[toc]

## Two Basic Elements

<img src="Resources/18.png" style="zoom:60%;" />



- Modeling : defines objects inside the scene
- Rendering : draws defined objects

## Conceptual Framework for Computer Graphics

<img src="Resources/19.png" style="zoom:60%;" />

### Application Model

<img src="Resources/20.png" style="zoom:60%;" />

- represents the data or objects to be pictured on the screen
- geometric and mathematical description of objects
- application-specific model and independent from any particular display system
- consists of a set of...
  - geometric primitives(e.g. lines, faces, spheres, torus)
  - procedures(e.g. fractals)
  - vector and scalar data(e.g. voltage, resistance, etc.)
- Modeling

<img src="Resources/21.png" style="zoom:60%;" />

### Application program

<img src="Resources/22.png" style="zoom:60%;" />

- create, remove, edit, store into and retrieve the data or objects in the application model
- handles user interaction(logical level)
- send commands to graphics system to make a picture
  - modeling command
  - viewing condition specification
  - shading and illumination parameter setting
  - special effects
- Programming (programmer's point of view) Open GL/Direct 3D

<img src="Resources/23.png" style="zoom:60%;" />

### Graphics System

- actually produce pictures and pass user input to the application program
- raster operation such as scan conversion & clipping
- PHIGS, GKS, SRGP, X-window, GDI of MS windows, Open GL
- Graphics System (developer's point of view)

## Example

- Graphics Process of 3D Computer Graphics

<img src="Resources/24.png" style="zoom:60%;" />

- 3D Geometric Modelling

<img src="Resources/25.png" style="zoom:60%;" />

<img src="Resources/26.png" style="zoom:60%;" />

- 3D Animation Definition 

<img src="Resources/27.png" style="zoom:60%;" />

- Texturing

<img src="Resources/28.png" style="zoom:60%;" />

<img src="Resources/29.png" style="zoom:60%;" />

## Rendering Process (Pipeline)

<img src="Resources/30.png" style="zoom:60%;" />

- 응용단계 : 충돌검출, 가속 알고리즘, 애니메이션, 등
- 기하단계 : 기하변환, 투영, 조명처리
- 래스터화 단계 : 이미지 생성

<img src="Resources/31.png" style="zoom:60%;" />

## Image Display

<img src="Resources/32.png" style="zoom:60%;" />

## Display Technology

### CRT(Cathode Ray Tube)

The response of phosphors to excitation by an electron beam phosphor decay (persistence)

<img src="Resources/33.png" style="zoom:60%;" />

- Intensity Resolution

  Each pixe has only "Depth" bits for colors/intensities

- Spatial Resolution

  Image has only "Width" x "Height" pixels

- Temporal Resolution

  Monitor refreshes images at only "Rate" Hz

<img src="Resources/34.png" style="zoom:60%;" />

- Screen refresh

  - need to be refreshed (at least 60Hz) (flickering effect)

  - Moving the electron beam, and turning it On and OFF, generates a visually perceived display pattern on the screen

<img src="Resources/35.png" style="zoom:60%;" />

### LCD

<img src="Resources/36.png" style="zoom:60%;" />

## Vector vs. Raster Display

- The beam pattern may be either regular(RASTER) or directed as required (VECTOR). 
- Vector CRT developed from established osiloscope technology (early 1960's)
- Raster graphics became feasible as memory costs dropped (mid 70's)
- Colors are created by separately exciting red, green, and blue phosphors inside the CRT imaging device.

<img src="Resources/37.png" style="zoom:60%;" />

<img src="Resources/38.png" style="zoom:60%;" />

<img src="Resources/39.png" style="zoom:60%;" />

<img src="Resources/41.png" style="zoom:60%;" />

- Example

<img src="Resources/40.png" style="zoom:60%;" />

## Frame Buffer Architecture

- The graphical data to be displayed on the raster is stored by the **frame buffer**
- scan conversion : the process of forming geometric shapes raster grids

<img src="Resources/42.png" style="zoom:60%;" />

<img src="Resources/43.png" style="zoom:100%;" />

- Bit planes
  - 2D arrays of bits 
  - The frame buffer is built from one or more "bit planes" 
  - The number of bits per pixel in the frame buffer determines the complexity of images that can be displayed.

- Resolution depends on

  - frame buffer resolution
  - display H/W characteristics
  - sampling method

  <img src="Resources/44.png" style="zoom:100%;" />

## Screen Refresh 

- Raster images are displayed by drawing the pixels sequentially in a fixed order
  - vertical retrace(tEA) ~1.3msec
  - horizontal retrace(tBC) ~10usec
  - 512 lines * 1024 pixels 50nsec/pixel

<img src="Resources/45.png" style="zoom:100%;" />

- Interlacing
  - a usual frame display rate : 60 Hz 
  - divide a frame into even-numbered scan lines (1/60 sec) and odd-numbered scan-lines(1/60 sec)
  - whole frame takes 1/60 + 1/60 = 1/30 sec 

- Graphics Adapter
  - frame buffer + display controller (+ display processor) (e.g., Super VGA 1024x768 pixels)

## 3D Rendering Pipeline

<img src="Resources/46.png" style="zoom:60%;" />

<img src="Resources/47.png" style="zoom:60%;" />

## Graphics Hardware

- Input Device :
  - mouse, keyboard, scanner, trackball, light pen, joystick

- Special Processors : 
  - graphics memory, scan converter, graphics accelerators. 

- Output Device :

  - display : CRT(refresh CRT, DVST), Plasma-panel, LED/LCD monitors

  - Hard-copy devices: printers (raster device), plotters (vector device)

## Color and Intensity 

- light :
  - made up of many little particles(photons) 
  - particle model (cf. wave model)

- color :
  - the frequency of a photon

- energy of a photon :

  - directly related to the frequency

  

<img src="Resources/48.png" style="zoom:70%;" />

## Visible Spectrum

We perceive electromagentic energy having wavelengths in the range 400-700nm as visible light.

<img src="Resources/49.png" style="zoom:70%;" />

## Color Model

### RGB Model

- RGB model:
  - red, green, blue
  - additive model
  - illumination based
- The color that reaches your eye from your monitor depends on illuminating light it emits

- RGB monitor

<img src="Resources/50.png" style="zoom:70%;" />

<img src="Resources/51.png" style="zoom:70%;" />

### CMYK Model

- CMYK model:
  - cyan, magenta, yellow and black
  - subtractive model
  - reflection based

- color printer

<img src="Resources/52.png" style="zoom:70%;" />

<img src="Resources/53.png" style="zoom:70%;" />

- W - G (Complement of Magenta) = R + B = Magenta
- (W - G) - R (Complement of Cyan) = Blue
- (W - G - R) - B (Complement of Yellow) = Blcak

<img src="Resources/54.png" style="zoom:70%;" />

## Specifying Color

- direct color:
  - each pixel directly specifies a color value
    - e.g., 24 bit : 8 bits(R) + 8 bits(G) + 8bits(B)
- palette-based color : indirect specification
  - use palette(CLUT : color lookup table)
    - e.g., 8 bits pixel can represent 256 colors

- Color Lookup Table(CLUT)

<img src="Resources/55.png" style="zoom:70%;" />

## Gamma Correction

the process of changing the balance of R, G, B to correct for the sensitivity of our eyes(or monitor, printer) to different colors.

<img src="Resources/56.png" style="zoom:70%;" />

## Interactive Graphics System

<img src="Resources/57.png" style="zoom:70%;" />

Advantages : extensive, high-bandwidth user-computer interaction

## Graphics System

- Simple raster graphics system

<img src="Resources/58.png" style="zoom:70%;" />

- Fixed frame buffer in system memory

<img src="Resources/59.png" style="zoom:70%;" />

- Display processor

  

<img src="Resources/60.png" style="zoom:70%;" />

## 2D Recutangular Coordinate System

<img src="Resources/61.png" style="zoom:70%;" />

## 3D Rectangular Coordinate System

- Right-hand System

  - Standard in most graphics packages

    <img src="Resources1/00.png" style="zoom:70%;" />

- Left-hand System

  - Easy to know the distance from the viewer
  - Video monitor coordinate system

<img src="Resources1/01.png" style="zoom:70%;" />

## Polar Coordinate System

<img src="Resources1/02.png" style="zoom:70%;" />

### Why Polar Coordinates in Circles?

- In recutangular system : 

  Irregular distributition of continuous points

<img src="Resources1/03.png" style="zoom:70%;" />

<img src="Resources1/04.png" style="zoom:70%;" />

## Point/Vector

- Point : 좌표계의 한 점을 차지, 위치 표시

- Vector : 두 position 간의 차로 정의
  $$
  V = P_2 - P_1 =(x_2 - x_1, y_2 - y_1) = (V_x,V_y)
  $$

- Magnitude와 Direction으로도 표기

  <img src="Resources1/05.png" style="zoom:70%;" />

$$
|V| = \sqrt{{v_x}^2+{V_y}^2} \\
α = tan^{-1} {{V_y} \over {V_x}}
$$

## Vector

- Normalized Vector(정규화 백터)

  - Normalized?

    Direction is the same.

    Hower, the magnitude is scaled as the maximum size is 1.0.

  - e.g.) p = t - s = (6,4) - (2,1) = (4,3)

    ​	 p` = (4/5,3/5)

- 3 차원에서의 Vector

  <img src="Resources1/06.png" style="zoom:70%;" />
  $$
  \begin{align}
  V = P_2 - P_1 = (x_2 - x_1, y_2 - y_1, z_2 - z_1) = (V_x,V_y,V_z) \\
  |V| = \sqrt{V_x^2+V_y^2+V_z^2}\\
  cos\alpha = {{V_x}\over{|V|}}, cos\beta={{V_y}\over{|V|}}, cos\gamma={{V_z}\over{V}}\\
  cos^2{\alpha}+cos^2{\beta}+cos^2{\gamma}=1
  \end{align}
  $$
  

## Affine Space

- $V = P_2 - P_1$
- $P_2 = V + p_1$

<img src="Resources1/07.png" style="zoom:70%;" />

- Expand the VECTOR space as dealing with POINT and VECTOR as the same race. = 동족(同族) 좌표

- As a result, the point $P_1$ in the affine space is regarded as Vector $P_1$ directed to origin to point $P_1$.
- $ V = P + {{1}\over{2}}(Q-P)$
- $V = P + t(Q-P)=(1-t)P+(t)Q(0\leq t \leq1)$

<img src="Resources1/08.png" style="zoom:70%;" />

## Parametric / Nonparametric

- Circle example in computer graphics

  e.g. radius 2, entered at the origin

- Parametric expression : $x = 2cos\theta$, $y = 2sin\theta$

- Nonparametric expression
  $$
  \begin{align}
  Implicit: x^2+y^2=4\\
  explicit: y = \pm{\sqrt{4-x^2}}
  \end{align}
  $$
  

<img src="Resources1/09.png" style="zoom:70%;" />

- Easy to draw the shape of an object smoothly
  - Just increase one parameter ex) $\theta$
    - The other parameters are automatically calculated by $\theta$

- Especially for symmetric objects
  - Circle,sphere,ellipsoid,etc.
- Preferred in computer graphics
  - Nonparametric representation is used mainly in numerical analysis

## Dot Product

- Dot Product = Scalar Product = Inner Product
- Definition : $V_2$가 $V_1$에 미치는 영향력

<img src="Resources1/10.png" style="zoom:70%;" />
$$
\begin{align}
V_1 \cdot V_2 = |V_1||V_2|cos\theta,0\leq\theta\leq\pi\\
V_1 \cdot V_2 = V_{1x}V_{2x}+V_{1y}V_{2y}+V_{1z}V_{2z}
\end{align}
$$

- Property

  - Commutative : $V_1 \cdot V_2 = V_2 \cdot V_1$
  - Distributive : $V_1 \cdot (V_2 + V_3) = V_1 \cdot V_2 + V_1 \cdot V_3$

- Example

  <img src="Resources1/12.png" style="zoom:70%;" />

## Cross Product

- Cross Product = Vector Product = Outer Product
- Definition:

<img src="Resources1/11.png" style="zoom:70%;" />
$$
\begin{align}
V_1 \times V_2 = u|V_1||V_2|sin\theta, 0\leq\theta\leq\pi \\
V_1 \times V_2 = (V_{1y}V_{2z} - V_{1z}V_{2y},V_{1z}V_{2x} - V_{1x}V_{2z},V_{1x}V_{2y} - V_{1y}V_{2x})
\end{align}
$$

- Property
  - Anti-commutative : $V_1 \times V_2 = -(V_2 \times V_1)$ **Careful for its direction**
  - Not associative : $V1 \times (V_2 \times V_3) \neq (V_1 \times V_2) \times V_3$
  - Distributive: $V_1 \times (V_2+V_3) = (V_1 \times V_2) + (V_1 \times V_3)$

- Example

<img src="Resources1/13.png" style="zoom:70%;" />