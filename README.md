# Maze-Solver-using-OpenCV-and-Python.
This project is based on **Image Processing using OpenCV and Python**. The unsolved maze image is taken as an input.
## **STEPS**
There are 7 steps to solve the maze and highlight the recommended path.

#### **FIRST STEP**
The First Step in solving the maze is ***Binary Conversion***. 
At first, the image is converted to grayscale using [cvtColor](https://docs.opencv.org/2.4/modules/imgproc/doc/miscellaneous_transformations.html) function of OpenCV. That is, the image is converted from RGB to GrayScale. Now, the image is converted into black and white using [cv2.thresold](https://docs.opencv.org/master/d7/d4d/tutorial_py_thresholding.html).

