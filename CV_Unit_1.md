# Computer Vision

## Computer Vision vs Machine Vision

![CV vs MV](image.png)

## Cognitive vision

It refers to the cognitive processes involved in  visual perception, Attention, Memory, Pattern recognition. It is used to simulate human-like understanding and reasoning about visual information to  achieve context-aware, intelligent decision-making.

---
## Factors in Image Formation

1. __Geometry:__ The relationship between points in the  three-dimensional world and their images
2. __Radiometry:__ The relationship between the amount of light radiating from a surface and the amount incident at its image
3. __Photometry:__ Ways of measuring the intensity of visible light
4. __Digitization:__ Ways of converting continuous signals to digital approximations

## Radiometry and Photometry

![alt text](image-1.png)

---
## Working Model

![alt text](image-2.png)

* __Optics / Lens:__ The first part of a camera which interacts with  photons of light from the environment.
* __Aperture:__ Controls how much light enters your camera.
* __Shutter Speed:__ Controls how long light enters your camera

### Sensors

* __CCD (charge-coupleddevice) and CMOS (complementary metaloxide semiconductor):__ Two types of image sensors that are  used in digital cameras.  They are used to capture and transform light into electrical signals
* __Gain:__ It amplifies this signal to ensure that even low-light conditions result in a bright image.

### DSP

* __Demosaicing:__ The camera runs a demosaicing algorithm internally to generate the full RGB image.
* __Sharpening:__ It enhances edges and fine details by increasing local contrast.
* __White balance:__ It is a camera setting that establishes the true color of white. This produces a baseline from which all other colors are measured.
* __Gamma correction:__ It is a nonlinear method used in luminance encoding and decoding to adjust to human visual perception.
* __JPEG  (Joint Photographic Experts Group) :__ It is a graphic image file compressed with lossy compression using the standard developed by the ISO/IEC

---

## Intensity Square Law

The intensity of a light source falls off with the square of the distance between the source and the object being lit

![ ](image-4.png){width=50% height=300px}

---

## BRDF (Bidirectional Reflectance Distribution Function) 

* This model defines how light reflects off surfaces, which is crucial for photorealistic rendering in 3D graphics and material analysis.
  
> BRDF Calculation 𝑓𝑟 = L <sub>o </sub>/ E <sub> i </sub>

* L <sub>o </sub> - Measured outgoing radiance; E <sub> i </sub> - Incident irradiance

* __Albedo (ρ)__ is a material property that measures how much incoming  light a surface reflects, relative to how much it receives.

> Albedo : ρ = π . 𝑓𝑟
> Lambertian BRDF fr = ρ / π

* Albedo controls the overall brightness
* BRDF controls the directional distribution

*  BRDF determines the direction and intensity of the reflected light that eventually reaches the sensor.
*  __Photodiodes__ are arranged in a grid pattern on the surface of the  image sensor
*  Each photodiode corresponds to one pixel in the final image.

---

## Light enters into the sensor(CCD/ CMOS)

* __Photon Detection__
  
> E = h.f    
>    E = h c / λ
>  f = 1 / λ

f - frequency of the light; h - 6.62×10<sup>-34</sup> Planck's constant; c - 3 × 10 <sup>8</sup>  Speed of light   

![alt text](image-5.png)

* __Outgoing Radiance Using BRDF__

> L (Luminance / Radiance) = 𝑓𝑟 . E

---
### Intensity of Sensor

* Bayer filters helps to filter each color in the analog signal so that only 1 color is displayed on the image plane.
* Each pixel measures the intensity for one color channel.
* 50% - Green, 25% - Red, 25% - Blue
* The dominance of geen color is due to the human eye being more sensitive to green color and this also enhances the sharpness and details of the image.
* Green is crucial for luminance (brightness) and preserving fine details in an image.


__Analog Voltage  == > Bayer Filtering  == > ADC == > RAW Bayer Image == > Demosaicing__

---
### Standard Bayer Pattern

RGBG Pattern

|R|G|R|G|
|--|--|--|--|
|G|B|G|B|
|R|G|R|G|
G|B|G|B|

### Alternative Bayer Pattern

GRBG Pattern

|G|R|G|R|
|--|--|--|--|
B|G|B|G
G|R|B|G|
G|B|G|B|

---


## Reconstruction of image

__Demosaicing / Debayering__ is the digital image processing step used to reconstruct a full-color RGB image from a RAW Bayer image, where each pixel contains only one color component.

RAW Bayer image == > Demosiacing == > RGB image

---

## Interpolation Techniques

1. __Nearest Neighbour Interpolation__
   
* Simplest method which fills the missing color values for a pixel by copying the value of the nearest neighboring pixel of the same color.
* Priority to be given to __top / left element__ (first encountered).
*  It is fast and simple but produces __blocky and low quality images__.

2. __Bileniar Interpolation__

* Consider all neighbours and take an average.
* Boundary pixels will have partial neighbours and interpolation adjusts accordingly
* Produces smoother results than nearest neighbor interpolation but may blur the fine details and edges.

3. __Gradient-Based Interpolation__

* It considers the direction of edges and gradients in image to avoid interpolation errors.
* Missing values are interpolated along direction of minimum intensity gradient for green. Compute horizontal and vertical gradient (green) and choose the smallest gradient vaule. If both gradient values are same then take average
* Red and blue values are interpolated from diagonal  neighbors

Logic for Bayer to RGB image program
*  GRBG Pattern - even row and odd colomn - Red
*   odd row even colomn - Blue, even row odd column and odd row odd column - Green

``` 
for i in range (0,3):
for j in range(0,3):
if(i % 2 ==0) &&  (j % 2 ==0) || (i %2!=0) && (j %2!=0)
```
Logic for RGB image to Bayer image

```
if (i>0):
RGB [ 0,0,1] = I [ i,j-1]
RGB [0,0,1] = I [i,j]
RGB [0,0,2] = I [i+1,j]
```
---

## Chrominance Reduction

Chrominance reduction is performed by converting RGB image to YCbCr (colors stored in CbCr and Y stores brightness) and averaging 2 X 2 chroma block, resulting in reduced resolution Cb and Cr channels while preserving ful - resolution luminance.


---

## Non linear Device Response


> L = V <sup>gamma 

gamma (approx) = 2.2
V = input voltage ; L =  emitted luminance

---

## Gamma Correction

Gamma is a voltage applied to display the image on the screen

__Step 1__ Inverse Gamma (Gamma Encoding)

> V = L <sup>1/gamma

__Step 2__ Gamma Decoding (Reversing the Inverse)

![alt text](image-6.png)

__Result:__ Effective Linearity

The overall system becomes linear. Input luminance maps correctly to output luminance and image brightness appears correct to the human eye

---

## JPEG Compression

* Joint Photographic Experts Group
* Widely used lossy image compression technique
* Reduce storage and bandwidth 


## Steps in JPEG Conversion

1. __Color Space Conversion__
  convert RGB to CbCr
  Y (Luminance): Represents brightness.
  Cb and Cr (Chrominance): Represents color information.

2.  __Downsampling__
 Reduces file size w/o affecting visual quality
 Reduce the resolution of the chrominance components

3. __Block Splitting__
   Dividing image to 8X8 blocks

* Y Luminance - many 8X8 blocks
* Cb Blue Chroma - fewer  8X8 blocks
* Cr Red Chroma - fewer  8X8 blocks
  
Conversion Formula
  rounded off values
![alt text](image-11.png)

4. __Discrete Cosine Transformation__

Apply DCT to each  8X8 block. Transforms spatial pixel values into frequency components.

5. __Quantization__

  Reduce precision of frequency components using quantization matrix.
  This step is where most of the lossy compression occurs.

6. __Encoding__

  The quantized DCT coefficients are encoded using:
  Run-Length Encoding (RLE): Compresses sequences of zeros efficiently.
  Huffman Encoding: A lossless compression technique for further size reduction

---

## Camera Calibration

* Process of estimating camera parameters.
* We need this to have a mathematical relation between 2D image and 3D real world.

## Fundamental Problem

* A real camera is not a traditional pinhole camera
* __Internal parameters / Intrinsics (Inside the Camera):__ Focal length, Optical Centre, Radial Distortion Cooefficients


  |f<sub>x</sub> | 0| c<sub>x</sub>|
  |--|--|--|
  |0 |f<sub>y</sub> |c<sub>y</sub>|
  |0 | 0| 1|

* __External parameters / Extrinsics :__ Rotation matrix R; Translation vector t

---
## Intrinsic Parameters

### Distortion

Our intention is to undisort the picture by camera caliberation

## Radial Distortion

It causes straight lines to appear curved inwards or outwards

 Mathematical Representation

> x <sub>disorted</sub> = x(1 + k<sub>1</sub> r<sup>2</sup> + k<sub>2</sub> r<sup>4</sup> + k<sub>3</sub> r<sup>6</sup>) y<sub>disorted</sub> = y(1 + k<sub>1</sub> r<sup>2</sup> + k<sub>2</sub> r<sup>4</sup> +k<sub>3</sub> r<sup>6</sup>)

> r<sup>2 </sup> = x<sup>2 </sup> + y<sup>2 </sup>

Square of Euclidean distance

> k<sub>1</sub>, k<sub>2</sub>,  k<sub>3</sub>

Radial distortion coefficients of the lens

## Tangential Distortion

It occurs when the lens and the image plane are not parallel. 

![alt text](image-8.png)

---

## Extrinsic Parameters

### Rotation Matrix (R)

This 3×3 matrix defines the orientation of the camera coordinate system relative to the world coordinate system.

### Translation Vector (t)

This 3×1 vector defines the position of the camera's optical center in the world coordinate system.

![alt text](image-9.png)

---