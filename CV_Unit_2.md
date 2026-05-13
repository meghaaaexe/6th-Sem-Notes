
## Segmentation by Humans - Gestalt Principles

1. __Proximity Principle__ - Objects that are closer to each other are grouped together
2. __Similarity Principle__ - Similar objects are grouped together. Proximity principle is given more priority than similarity principle
3. __Commom Fate__ - Objects with similar motion or change in appearence are grouped together
4. __Common region/Connectivity__ - Connected objects are grouped together
5. __Continuity Principle__ - Features on a cintinuous curve are grouped together.
6. __Symmetry Principle__ - Parallel and symmetrical features are grouped together
7. __Illusory Contours - Illusion's grouping__ - Illusory or subjective contours are percieved.

---

## Two approaches towards Segmentation

1. __Top-Down Segmentation (Model - Driven)__ - It uses high-level knowledge, such as object shapes. Pixels belong together as they come from the same object.

__Methods:__

* __Active contours (Snake)__ - Segment using curves and not by pixels. It is used in medical imaging, industrial inspection, object tracking etc.

> V(S) = (X'(S)Y(S))
  >E = E<sub>internal</sub> + E <sub>image</sub >+ E<sub>external</sub>

* __Scissors__ - Intelligent Scissors/Live-Wire is an interactive image segmentation technique. The algorithm finds optimal (shortest) boundary path b/w clicks. It is used in photo editing, medical images etc.

2. __Bottom-up Segmentation (Data driven)__ - Group pixels based on local cues like color or textue. Pixels belong together as they look similar. 

__Methods:__

* __Thresholding__
* __Region growing__

---
## K- Means Clustering


Choice of K :
k = 2 - background or foreground
k = 5 - coarse regions
k = 50 - fine over segmentation

Disadvantages of k means:

 * We have to pick optimal value of k
 * It maybe sensitive to initialization and outliers 




---

## Mean Shift Segmentation

Choosing window size:
Small bandwidth -  many small clusters
Large bandwidth -  few large clusters

* Each hill represents a cluster.
* Simple but computationally expensive
* Clustering depends on window size w
* Robust to outliers
* Clustering depends on window size w



__Example:__ Data Points [1,2,3,7,8,9,10,11]
__Solution:__
Each point is a potential cluster center
Mean Shift Iteration (for point 1):
* Window: 2, radius = 2
* Mean Shift: (1 + 2 + 3)/ 3 = 2 New center is 2
* Window: Points w bandwidth 2 of 2 : [1,2,3]
* Mean Shift : ( 1 + 2 + 3)/ 3 = 2
1 is the hill with 2 as peak

Mean Shift Iteration (for point 7):
* Window: Points w bandwidth 2 of 7 : [ 7,8,9 ]
* Mean Shift : 7 + 8 + 9/3 = 8, center = 8
* Window: [7,8,9,10]
* Mean Shift: 7 + 8 + 9 + 10/4 = 8.5
* Window: Points w bandwidth 2 of 8.5 is [7,8,9,10]
* Converges at 8.5
7 is the hill with 8.5 as peak


---

## Graph Based Segmentation

* Every pixel is a vertex
* An edge btwn each pair of pixels (vertices)
> G = (V,E)
* Measuring affinity: smaller the dissimilarity, larger the affinity
* Normalized Cut - Minimize cost of Normalized Cut during partition.. The Ncut value ranges from 0 to 2. 0 indicates high-quality cut and 2 indicates poor partiotion.
__Example__
 A = {1}, B = {2,3,4}
 Cut (A,B) = (1,2) = 5; (1,3) = 1; (2,3) = 1; (2,4) = 1; (3,4) = 5
 Assoc(A,V) = (1,2) + (1,3) = 6;
 Ncut = 6/6 + 6/7 = Approches towards 2

---

## Edge Based Segmentation

* It is a method of segmenting an image into regions of discontinuity
* It detects boundaries using operators like Sobel, Canny, Laplacian
* Converts 2D image into a set of points.
* Gaussian - Computes first order derivations like sobel
* Gradient - Cpmutes second-order derivations like Canny

![alt text](image-12.png)

__Question__
$$
I =\begin{bmatrix} 
100 & 120 & 130 & 140 \\\\
90&110 &120 &130\\\\
80&100 &110 &120 \\\\
70&90 &100 &110 \\\\
\end{bmatrix}
$$

Compute gradients and orientation for all pixels. Use 0 padding and sobel opertion for edge detection and orientation
 :
$$
sobel  matrix_x  =\begin{bmatrix}    
-1 & 0 & 1 \\\\
-2 & 0 & 2 \\\\
-1 & 0 & 1
\end{bmatrix}
$$

$$
sobel  matrix_y  =\begin{bmatrix}
1 & 2 & 1 \\\\
0 & 0 & 0 \\\\
-1 & -2 & -1
\end{bmatrix}
$$

__Solution__

Add zeros in all 4 rows and coloums and multiply sobel x  matrix with 3 X 3 I matrix


$$
I_x=\begin{bmatrix}
350& 90  &60  & -380  \\\\
440 & 120  & 80  &-480  \\\\
400&120  &80  &-440  \\\\
280& 90 & 60 & -310 \\\\
\end{bmatrix}
$$

$$
I_y=\begin{bmatrix}
-290& -430  &-480  & -380  \\\\
60 & 80  & 80  &60  \\\\
60&80  &80  &60  \\\\
260& 390 & 440 & 350 \\\\
\end{bmatrix}
$$

Now, perform sqrt of I<sub>x</sub> + I <sub>y</sub>

$$
Magnitude matrix =\begin{bmatrix}
440& 439  &483  &537 \\\\
444&144  &113  & 483\\\\
404& 144 &113  &444 \\\\
382&400  & 444 & 487\\\\
\end{bmatrix}
$$


Orientation matrix = tan (theta) (I<sub>x</sub> / I <sub>y</sub>)

---

## Feature Detection and Matching

__Image Stitching:__ Aligning two images so that they can be seamlessly stitched into a complete mosiac.

__Object Recognition:__ Identifying specific objects within an image by comparing extracted features to a known database of images.

__Image Registration:__ Process of aligning two or more images of the same taken at different times, angles or sensors. It is used in medical imaging, computer vision and robotics.

__3D Construction:__ Eshtablish a dense set of correspondences so that a 3D model can be generated.

__Object Tracking:__ Feature detectiona nd matching is used to identify and locate key points on an object across multiple frames.

### Feature
A piece of info relevant for solving the computational task 

__Main Categories:__ 

1. __Key Point/Interest Point/Corner Feature:__ Peaks, corners, appearance of patches of pixels surrounding the point location.
  
2. __Egdes(object boundaries):__ It is based on orientation and local appearance

### Main components of Feature Detection and Matching

1. __Detection__ Identifying intrest point
2. __Description__ It gives descriptor vector for each intrest point
3. __Matching__ Descriptors are compared across the images to identify similar images. It gives a set of pairs of matching images.

---

## SIFT Detector

* Scale Invarient Feature Transfrom (SIFT) 
* It is close ot real time performance
* Actual size considered in SIFT IS 16 X 16

### Main steps involved

1. Detecting Intrest points: edges, corners, peaks
2. 
3. Extract feature descriptor

### Attributes of Key / Interest Points

* Well defined representation, position in image
* Should be invarient to image rotation and camera lighting
* Blobs: A region of an image that differs from its surrounding area in color or brightness

---

## Scale Invarience

* Once detected the interest points, normalize / scale up or down to match the other for the applications
* Increase or decrase the size as per sigma value

## Rotation Invariant

* Construct gradient magnitude and orientation for each blob region.
* Build an orientation histogram and assign dominant direction.

---

## Application of SIFT 

* __Image registration or alignment(2D)__ : Process of transforming multiple images into a common coordinate system
* __Object recognition__ : Help identify objects by finding distinctive features
* __Image Stitching__ : Used to stitch images together for panoramic photography
  
---


