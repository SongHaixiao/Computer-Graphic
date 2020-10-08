# Illumination and Shading

[toc]

## 3D Rendering Pipeline

![](Resources1/96.png)

## Shading

- Given ：

  scene specification (object positions, optical properties of the surface, viewer position, viewing direction, ......) 

- Find :

  intensity for each pixel

![](Resources1/97.png)

## Illumination Models

- Rendering need a model for how light interacts with objects.

- Physically correct model:
  - the intensity reflected from every point depends on the intensity from every other points
  - global illumination
- Sim