# Face RGB Extractor

This project detects faces in uploaded images, extracts RGB values from key facial regions (forehead, left cheek, right cheek), annotates those regions on the image, and generates a styled Excel file containing the RGB values and embedded annotated images.

---

## Run in Colab(Recomended)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/samarth-9900/Face-RGB-Extractor/blob/main/face_rgb_extractor.ipynb)

---

## Run Instructions

- Run the script in Google Colab
- Upload aligned face images in JPG or PNG format to get proper RGB values
- The final Excel file will be saved and downloaded (in Colab) or stored locally
- The script will:
  - Detect faces  
  - Extract RGB values from forehead, left cheek, and right cheek  
  - Annotate the image with rectangles and points  
  - Generate a styled Excel file (`face_rgb_with_images.xlsx`)  
  - Embed the annotated image beside each RGB table

---

## Implementation

### Face Detection
Used OpenCV’s `haarcascade_frontalface_default.xml` to detect frontal faces quickly and with minimal setup.

### RGB Sampling
Selected three fixed facial points:
- **Forehead** (upper central region)
- **Left cheek** and **Right cheek** (lower side regions)

### Color Format
OpenCV reads images in BGR format, which is converted to RGB before writing to Excel.

### Excel Output
- `openpyxl` is used for creating the Excel workbook
- Styles include bold headers, borders, fills, and alignment
- Annotated images are resized using Pillow and embedded into the corresponding Excel row

---

## Challenges Encountered

- **Face detection reliability**: Haar cascades often fail for non-frontal or poorly lit images.
- **Pixel sampling variability**: RGB values taken from a single pixel can be highly sensitive to noise and lighting conditions.
- **BGR-RGB conversion**: OpenCV uses BGR color format, while most other libraries (like Pillow and Excel tools) expect RGB, requiring manual conversion.

---


