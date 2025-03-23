# Invoice-extraction-system-for-ML-assignment-2
Invoice Data Extraction System
This project aims to automate the extraction of data from invoice images using a combination of YOLOv8 for object detection and Optical Character Recognition (OCR) for text extraction. The system can identify specific fields such as invoice ID, total amount, address, etc., and convert the extracted information into an Excel sheet with appropriate headings.

Table of Contents
Features
Installation
Usage
Model Training
OCR Integration
Output
Screenshots
Contributing
License
Features
Train YOLOv8 on annotated invoice images.
Detect specific fields on new invoice images.
Extract text from detected fields using OCR.
Export extracted data to an Excel sheet.
Installation
Clone the repository:
git clone https://github.com/jawadshahid07/Invoice-Data-Extraction-System.git
cd invoice-data-extraction
Set up a Python virtual environment:
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
Install required packages:
pip install -r requirements.txt
Download, install, and setup Tesseract OCR. Here is the documentation: https://tesseract-ocr.github.io/
Usage
(OPTIONAL) There is already a trained model present with the file name "yolov8n.pt". You may train your own model, with your own code or by modifying the code. The code for training the model is in the file "yolov8_model_training_for_invoices.ipynb".
(OPTIONAL) To visualize how the model works on invoice images, you may use the code in the file "yolov8 predict.ipynb", which outputs in an image with annotated results.
To use the project, we first run the code in "yolov8 extraction.ipynb", which takes an image, identifies labels on it, and extracts each label as it's own image file. The name of the image indicates the label. The extracted data in form of images is saved in "savedimages" directory.
We then run the "ocr to excel.ipynb". This code uses Tesseract OCR to convert each of the images, which contain one label, to text and stores it in an excel sheet under the correct heading. The output is your excel sheet.
Model Training
Annotate your invoice images with fields such as invoice ID, total amount, address, etc.
Use the YOLOv8 framework to train the model with these annotated images.
Save the trained model weights.
OCR Integration
Use Tesseract OCR library to extract text from the detected fields.
Map the detected fields to the corresponding text extracted by the OCR.
Output
The final output will be an Excel sheet with the extracted data, organized with appropriate headings.

Screenshots
YOLOv8 Detection
Caption: YOLOv8 detecting fields on an invoice.

Label 1 Label 2 Label 3 Label 4
Caption: Results of the prediction code, separating each label into it's own image

Excel Output
Caption: Extracted data saved in an Excel sheet.



