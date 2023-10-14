# Image-Text-Extraction-using-Tesseract-and-OpenCV
# OCR Image Text Extraction

This project involves extracting text from an image using Optical Character Recognition (OCR). We use the Python libraries OpenCV and Tesseract to perform OCR on the uploaded image. The extracted text is then displayed.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Example](#example)

## Prerequisites

Before using the script, make sure you have the required libraries installed. You can install them using pip in a Colab cell:

   ```shell
    !pip install pytesseract
    !apt-get install tesseract-ocr
   ```
## Installation

To run this project, you need to install the following dependencies:

1. OpenCV (Python version without GUI support):
   ```shell
   !pip install opencv-python-headless
   ```

2. Pytesseract:
   ```shell
   !pip install pytesseract
   ```

3. Tesseract OCR:
   ```shell
   !apt-get install tesseract-ocr
   ```

## Usage

1. Upload an image file from your local machine to Colab.

2. Read the uploaded image.

3. Convert the image to grayscale for better OCR performance.

4. Perform OCR on the grayscale image.

5. Display the extracted text.


## Example

Here's an example of how to perform image text extraction using OpenCV and Tesseract:

1. **Upload an Image**: Start by uploading an image from your local machine to Colab.

2. **Read and Display the Image**:

   ```python
   import cv2
   from google.colab.patches import cv2_imshow
   from google.colab import files

   uploaded = files.upload()
   image_path = list(uploaded.keys())[0]
   image = cv2.imread(image_path)
   cv2_imshow(image)
   ```

3. **Preprocess the Image**:

   Convert the image to grayscale for better OCR performance:

   ```python
   gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
   ```

4. **Perform OCR**:

   Extract text from the image using Tesseract:

   ```python
   import pytesseract

   extracted_text = pytesseract.image_to_string(gray_image)
   ```

5. **Display the Extracted Text**:

   Print the extracted text:

   ```python
   print("Extracted Text:")
   print(extracted_text)
   ```
