Download Link: https://assignmentchef.com/product/solved-ee5176programming-assignment-2-motion-deblurring
<br>



You are given a clean image of a scene having <em>M </em>rows and <em>N </em>columns (fish.png). We capture the scene using a static conventional camera with the aperture kept open for the full exposure time. The exposure time is 52 seconds. For simplicity, consider that the camera captures the scene at times <em>t </em>= 0<em>,…,</em>51 (i.e. at 52 instants). At time <em>t </em>= 0, the image has zero translation. Then, the whole image as seen by the camera moves at 1 pixel per second to the right (horizontal translation).

<ol>

 <li>Generate the blurred image having <em>M </em>rows and <em>N </em>+ 51 columns captured by the camera. Generate translated versions of the image for <em>t </em>= 0<em>,…,</em>51, and average them. Add Gaussian noise of mean 0 and standard deviation 1 (with respect to the maximum intensity of</li>

</ol>

255) from gaussNoise.mat. Display the blurred image.

<ol>

 <li>Form the blur matrix <strong>A </strong>of size (<em>N </em>+ 51) × <em>N </em>corresponding to the horizontal translation described above. Note that this matrix will be a Toeplitz matrix. Display <strong>A </strong>using imshow command.</li>

 <li>Use <strong>A </strong>to deblur the blurred image using least squares. The size of the deblurred image should be <em>M </em>× <em>N </em>for each colour channel. (Note: Since the blurring is horizontal, you have to operate A on each row of the blurred image.) Display the deblurred image. Determine the RMSEs between the given clean image and the deblurred image. Use the formula</li>

</ol>




<h1>2         Motion deblurring with flutter shutter</h1>

With the same setup as in previous section, we use a <em>flutter shutter camera </em>with code

1010000111000001010000110011110111010111001001100111

where each bit represents one second of the exposure time. The code is given in codeSeq.mat.

<ol>

 <li>Generate the blurred image with noise (same as in Problem-1) for the exposure code given above.</li>

 <li>Form the blur matrix <strong>A </strong>of size (<em>N </em>+ 51) × <em>N</em>.</li>

 <li>Plot the DFTs of the conventional and flutter shutter codes. Use the first column of the respective <strong>A </strong> Plot the magnitude in decibels. Comment.</li>

 <li>Let the noise be absent in both problems (1) and (2). Compare and comment on the deblurred outputs.</li>

</ol>

<h1>3         Deblurring with motion-invariant photography</h1>

You are given images of the top view of a road scene (background.png) and a foreground moving object (redcar.png).

<ol>

 <li>Assuming static camera and the velocity of the car as 1 pixel per second to the right (horizontal translation) relative to a static camera, generate the blurred image captured for an exposure time of 52 (Hint: First create individual frames for each second, i.e. 52 frames. To create each frame, apply translation corresponding to that frame on the foreground object and merge it with background. Merging: For all pixels with a non-zero values in the foreground image, assign foreground pixel values. or else use background pixel values.)</li>

 <li>Consider the same scenario captured using motion invariant photography (i.e. the camera also moves during the exposure). The translational values of the static background due to camera motion at each second are given in CameraT.mat. Generate the blurred image captured in this case with both camera and object motions for an exposure time of 52

  <ul>

   <li>Create individual frames for each second: Apply camera translations to the background image and the relative translations to the moving object separately. Then, merge them to obtain a frame. The relative translations of the moving object with respect to the moving camera can be obtained by <em>relative translation = static background translation due to camera – object translation</em></li>

   <li>Average all the 52 frames to obtain the blurred image.</li>

  </ul></li>

 <li>Compare and comment on the outputs of (a) and (b).</li>

 <li>Generate blurred images for object velocities: 2 pixel/s and 3 pixel/s. Compare and comment on the results.</li>

 <li>Find and plot the PSF of the blurred image in (b). If <em>x </em>is the camera translation then PSF weight at x is . Choose <em>x </em>as [0<em>.</em>1<em>,</em>1<em>,</em>2<em>,…,</em>51] and. Normalize the PSF after assigning these values.</li>

 <li>Deblur the blurred image in (b) using least squares. Use the PSF obtained in (e) to form the</li>

</ol>

blur matrix <strong>A</strong>.

<a href="#_ftnref1" name="_ftn1">[1]</a> Kindly refrain from using formats like .rar, .7z, etc