# Single-Image-Dehazing-Python
python implementation of the paper: "Efficient Image Dehazing with Boundary Constraint and Contextual Regularization"

## Installation and Running the tests

### method 1
  ```
  pip install git+https://github.com/XavierJiezou/Single-Image-Dehazing-Python.git
  ```
  
  **Usage:**
  ```
  import image_dehazer										# Load the library

  HazeImg = cv2.imread('image_path')						# read input image -- (**must be a color image**)
  HazeCorrectedImg, HazeTransmissionMap = image_dehazer.remove_haze(HazeImg)		# Remove Haze

  cv2.imshow('input image', HazeImg);						# display the original hazy image
  cv2.imshow('enhanced_image', HazeCorrectedImg);			# display the result
  cv2.waitKey(0)											# hold the display window
  ```
### user controllable parameters (with their default values):
```
airlightEstimation_windowSze=15
boundaryConstraint_windowSze=3
C0=20
C1=300
regularize_lambda=0.1
sigma=0.5
delta=0.85
showHazeTrasmissionMap=True
```
### method 2

  1. Go to the src folder
  2. run the file "example.py"
  3. sample images are stored in the "Images/" folder
  4. Output images will be stored in the "outputImages/" folder


# Libraries needed:
  1.numpy==1.19.0
  
  2.opencv-python
  
  3.scipy

# Theory
This code is an implementation of the paper "Efficient Image Dehazing with Boundary Constraint and Contextual Regularization"
The algorithm can be divided into 4 parts:
  - Airlight estimation
  - Calculating boundary constraints
  - Estimate and refine Transmission
  - Perform Dehazing using the estimated Airlight and Transmission
  
# License
  - This project is licensed under the BSD 2 License - see the LICENSE.md file for details
  
# Acknowledgements

  - The author would like to thank "Gaofeng MENG" and his implementation of his algorithm: https://github.com/gfmeng/imagedehaze

  - The author would like to thank Gaofeng MENG, Ying WANG, Jiangyong DUAN, Shiming XIANG, Chunhong PAN for their paper "Efficient Image Dehazing with Boundary Constraint and Contextual Regularization"
  
  - The author would like to thank Alexandre Boucaud. The function psf2otf was obtained from his repository. (https://github.com/aboucaud/pypher/blob/master/pypher/pypher.py)
  
  - The Author would like to thank Dr. Suresh Merugu for his matlab implementation of the codes. This repository is the python implementation of the matlab codes.
  
  - The Author would like to thank Mayank Singal for his repository "[PyTorch-Image-Dehazing](https://github.com/MayankSingal/PyTorch-Image-Dehazing)" which gives a pytorch implementation of the AOD-Net architecture. [Link to ICCV 2017 paper](https://openaccess.thecvf.com/content_ICCV_2017/papers/Li_AOD-Net_All-In-One_Dehazing_ICCV_2017_paper.pdf)
 
 Merugu, Suresh. (2014). Re: How to detect fog in an image and then enhance the image to remove fog?. Retrieved from: https://www.researchgate.net/post/How_to_detect_fog_in_an_image_and_then_enhance_the_image_to_remove_fog/53ae3f10d2fd64c3648b45a9/citation/download. 


# Citation
```
@INPROCEEDINGS{6751186, 
  author={G. Meng and Y. Wang and J. Duan and S. Xiang and C. Pan}, 
  booktitle={IEEE International Conference on Computer Vision}, 
  title={Efficient Image Dehazing with Boundary Constraint and Contextual Regularization}, 
  year={2013}, 
  volume={}, 
  number={}, 
  pages={617-624}, 
  month={Dec},}
```

# Results
![2](https://user-images.githubusercontent.com/13918778/84451507-1cbbb180-ac08-11ea-816f-8ec983fd370d.JPG)
============================================================================================================
![1](https://user-images.githubusercontent.com/13918778/84451353-b0d94900-ac07-11ea-8f1b-3791e9f2f600.JPG)
============================================================================================================
![3](https://user-images.githubusercontent.com/13918778/84451641-8471fc80-ac08-11ea-8a7d-59f566b1c3bb.JPG)




# Performance Comparison:
In this section, I am comparing the dehazing output with that of AOD-Net. I am using this [python implementation of AOD-Net](https://github.com/MayankSingal/PyTorch-Image-Dehazing/tree/master) to run a pretrained AOD-Net model
![image](https://github.com/Utkarsh-Deshmukh/Single-Image-Dehazing-Python/assets/13918778/f61f6906-e466-487b-ad8c-b289b2d95b90)


Here are some cases where AOD-Net is better:
![image](https://github.com/Utkarsh-Deshmukh/Single-Image-Dehazing-Python/assets/13918778/c04d8157-40d1-4a92-b3fb-e85f1c50326c)
