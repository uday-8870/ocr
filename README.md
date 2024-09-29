PDF Image Text Extractor
Overview
This project extracts images from PDF files and utilizes Tesseract OCR to recognize text from those images. It's useful for converting image-based PDFs into editable text formats.

Features
Extract images from PDF documents.
Recognize text in images using Tesseract OCR.
Save extracted text to a text file.
Prerequisites
Python 3.x
Tesseract OCR installed. Download here.
Installation
1. Clone the Repository
bash
Copy code


git clone https://github.com/yourusername/pdf-image-text-extractor.git
cd pdf-image-text-extractor


3. Install Required Packages
Make sure you have pip installed. Run the following command to install the necessary libraries:

bash
Copy code
pip install pytesseract pymupdf opencv-python Pillow colorama
3. Set Tesseract Path
Update the path to Tesseract in your script. Open the Python file and locate the following line:

python
Copy code
input_tesseract_path = r"C:\Program Files\Tesseract-OCR\tesseract.exe"  # Adjust this path if necessary
Ensure that the path points to the Tesseract executable on your system.

Usage
1. Set PDF File Path
Modify the script to set the path to your PDF file:

python
Copy code
user_input = r"C:\path\to\your\pdf.pdf"  # Change this to your PDF path
2. Run the Script
Execute the script using Python:

bash
Copy code
python your_script.py
3. Check Output
After running the script, the images will be saved in the images directory, and the recognized text will be in the output_txt/txtResult.txt file.

Example Code Snippet
Here's a snippet of the main functionality in the script:

python
Copy code
def recognize_text():
    global scanned_text, input_tesseract_path

    pytesseract.pytesseract.tesseract_cmd = input_tesseract_path

    for img_filename in os.listdir('images'):
        image = cv2.imread(f'images/{img_filename}')
        print(Fore.YELLOW + f"[.] Scanning text from {img_filename}..." + Fore.RESET)
        text = pytesseract.image_to_string(image, lang='eng')  # Change 'eng' for other languages
        scanned_text += text + "\n"
Example Output
When you run the script, you should see output similar to this:

plaintext
Copy code
[!] Using PDF file: C:\path\to\your\pdf.pdf
[!] Directory images created or already exists.
[!] Directory output_txt created or already exists.
[+] Found 2 images on page 1.
[+] Saved image: images/image1_1.jpeg
[.] Scanning text from image1_1.jpeg...
[!] Finished scanning text.
[.] Writing txtResult.txt...
[!] File written.
License
This project is licensed under the MIT License - see the LICENSE file for details.

Acknowledgments
Tesseract OCR for text recognition.
PyMuPDF for PDF processing.
OpenCV for image manipulation.
Feel free to replace placeholders (like paths and URLs) with your specific information! This structure will help users understand how to set up and use your project effectively.



