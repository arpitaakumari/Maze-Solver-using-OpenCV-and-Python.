# Maze-Solver-using-OpenCV-and-Python.
This project is based on **Image Processing using OpenCV and Python**. The unsolved maze image is taken as an input.
## **STEPS**
There are 6 steps to solve the maze and highlight the recommended path.

#### **FIRST STEP**
The First Step in solving the maze is ***Binary Conversion***. 
At first, the image is converted to grayscale using [cvtColor](https://docs.opencv.org/2.4/modules/imgproc/doc/miscellaneous_transformations.html) function of OpenCV. That is, the image is converted from RGB to GrayScale. Now, the image is converted into black and white using [cv2.thresold](https://docs.opencv.org/master/d7/d4d/tutorial_py_thresholding.html).


#### **SECOND STEP**
The second step is to ***Drawing***. At first the contours are found using [cv2.findContours](https://www.docs.opencv.org/2.4/modules/imgproc/doc/structural_analysis_and_shape_descriptors.html). And then contours are drawn using [cv2.drawContours](https://www.docs.opencv.org/2.4/modules/imgproc/doc/structural_analysis_and_shape_descriptors.html)

#### **THIRD STEP**
The third step is ***DILATION***. [Dilation](https://docs.opencv.org/3.4/db/df6/tutorial_erosion_dilatation.html) is one of the two basic operators in the field of mathematical morphology, and the other is erosion.It is usually applied to binary images, but there are some versions available for grayscale images.
The basic effect of the operator on binary images is to gradually enlarge the boundaries of 
foreground pixel regions (usually white pixels).
Therefore, the size of the foreground pixel increases, and the holes in these areas become smaller.

#### **FOURTH STEP**
[Erosion](https://docs.opencv.org/3.4/db/df6/tutorial_erosion_dilatation.html) is a form of the second operator.
It also applies to binary images.
The basic effect of the operator on binary images is to eliminate the boundaries of foreground pixel 
areas (usually white pixels).
Therefore, the area of foreground pixels is reduced, and the holes in these areas become large.

#### **FIFTH STEP**
The fifth step is to find the difference between the dilated image and the eroded image.

#### **SIXTH STEP**
The sixth step is splitting the channels of the maze using [cv2.split](https://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_core/py_basic_ops/py_basic_ops.html)
In order to display the solution on the original maze image, first divide the original maze into r, g, b components.
Now create a mask by inverting the diff image.
The bitwise and r and g components of the original maze using the mask created in the last step.
This step will remove the red and green components from the image portion of the maze solution.
The last one is to merge all the components and we will use the blue marked solution.
