# July 14th, 2020 Lecture Response
 1. .
 ### Original Image (misc.face(gray=True))
 ![Face](/DATA310_Images/face.png)
 ### Filter: [ [0, 1, 0], [1, -4, 1], [0, 1, 0]]
 ![Filter 1](/DATA310_Images/Lecture7142000.png)
 ### Filter: [ [-1, -2, -1], [0, 0, 0], [1, 2, 1]]
 ![Filter 2](/DATA310_Images/Lecture7142001.png)
 ### Filter: [ [-1, 0, 1], [-2, 0, 2], [-1, 0, 1]]
 ![Filter 3](/DATA310_Images/Lecture7142002.png)
  - The first filter appears to be a general edge detector, but it didn't pick up much in the picture of the raccoon. The second and third filters are vertical and horizontal edge detectors, respectively. All three filters worked by starting 1 away from both the top and left edges of the image and calculating a new intensity value by multiplying the value at the cursor and its eight neighbors and multiplying them by value of the filter at the matching index of the filter matrix (center of the matrix being where the cursor is). The value of all these multiplications is then summed (and weighted if the filter matrix values don't sum to 0 or 1). By applying filters to our images, we reduce the amount of visual noise in our image and allow the computer to more easily pick out features while training. The new image loses 2 pixels on both dimensions because the cursor never touches the picture's edges (if it did, then there would be less than eight neighbors and the filter would produce an error
 2. .
 ### Pooling on misc.face(gray=True)
  ![Filter 3](/DATA310_Images/Lecture7142003.png)
  - You are reducing the size of the image while, in theory, not losing any important information. This pooling formula takes a 2x2 window and returns only the maximum value within that window (max pooling). The result is that the new image is half the size of the original and consisting of only the most intense values of each 2x2 block. By keeping the most intense values, we are effectively keeping the nonbackground pixels, which are white because our filter turns most of the picture black. As we can see from the above picture, no information appears to have been lost, even though the picture size has been halved from the original 1022x767 to 511x383.
3. 
