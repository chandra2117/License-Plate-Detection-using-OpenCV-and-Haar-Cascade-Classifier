# License-Plate-Detection-using-OpenCV-and-Haar-Cascade-Classifier

## AIM

To detect and extract vehicle license plates from digital images using Haar Cascade classifiers in Python, and improve detection accuracy using preprocessing techniques such as histogram equalization and Gaussian blur.

## METHOD / PIPELINE
Step 1: Reading and Displaying Input Images

  - Load vehicle images using OpenCV (cv2.imread).

  - Display the images using Matplotlib (plt.imshow) to verify the inputs are correct.

  - Images include multiple types: single vehicle, angled plates, multiple vehicles.

Step 2: Converting to Grayscale

  - Convert the images to grayscale using cv2.cvtColor.

  - Grayscale simplifies processing for Haar Cascade, which detects intensity-based patterns, not colors.

Step 3: Preprocessing (Optional Improvement)

  - Apply histogram equalization using cv2.equalizeHist to improve contrast.

  - Apply Gaussian blur to reduce noise and smooth the image.

  - Preprocessing improves detection, especially under poor lighting or small/angled plates.

Step 4: Applying Haar Cascade Classifier

  - Load Haar Cascade for Russian license plates:

  - haarcascade_russian_plate_number.xml

  - Use detectMultiScale() to detect plates, with parameters:

  - scaleFactor: Image scaling for multi-scale detection (default 1.1).

  - minNeighbors: Minimum neighbors for rectangle retention (default 4).

  - minSize: Minimum size of detected plate region (default 30x30).

  - Adjust these parameters to reduce false positives or detect small plates.

Step 5: Drawing Bounding Boxes

  - Draw green rectangles around detected plates using cv2.rectangle.

  - Visualizes detection results for each image.

Step 6: Cropping and Saving Plates

  - Crop the detected plate regions from the original image.

  - Save cropped plates using cv2.imwrite.

  - Cropped regions can be used for further processing, e.g., OCR.

Step 7: Display Results

  - Display the original image with bounding boxes.

  - Display each cropped license plate region separately.

## IMPROVEMENTS MADE

  - Preprocessing: Histogram equalization and Gaussian blur added for better contrast and noise reduction.

  - Parameter tuning: scaleFactor and minNeighbors can be adjusted for different image conditions.

  - Visualization: Matplotlib is used to clearly display intermediate and final results.

## RESULTS / OBSERVATIONS
Image	Plates Detected	Observations
Car1	1	Plate detected clearly, cropped successfully
Car2 (angled)	1	Plate detected after preprocessing, slight rectangle adjustment
Car3 (multiple vehicles)	2	Multiple plates detected, cropped plates saved separately

## Conclusion:

Haar Cascade successfully detects license plates in clear, frontal images.

Preprocessing significantly improves detection for low contrast or angled plates.

#### Limitations: small, rotated, or partially occluded plates may not be detected.
