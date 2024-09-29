Image Text OCR using GOT (General OCR Theory)
This repository contains a Streamlit application that performs Optical Character Recognition (OCR) using the GOT (General OCR Theory) model. The application allows users to upload images, extract text from them, and search within the extracted text for specific words or phrases. The OCR functionality is powered by the GOT_CPU model hosted on Hugging Face.

Demo
Try the live demo on Hugging Face: GOT-OCR-Space

Setup
To set up the project locally, follow these steps:

Clone this repository to your local machine:

bash
Copy code
git clone https://github.com/your-username/your-repo.git
cd your-repo
Make sure you have Python 3.7+ installed.

Install the required dependencies:

bash
Copy code
pip install -r requirements.txt
Usage
To run the application locally:

Start the Streamlit application:

bash
Copy code
streamlit run app.py
Open your web browser and navigate to the URL provided by Streamlit (usually http://localhost:8501).

Features
Image Upload: Supports JPG, PNG, and JPEG formats.
Text Extraction: Leverages the GOT model to extract text from uploaded images.
Search Functionality: Users can search for specific words or phrases in the extracted text, and the application will highlight the matching results.
Model Information
The application uses the CPU version of the GOT (General OCR Theory) model for OCR tasks. Both the model and tokenizer are loaded from the Hugging Face Model Hub:

Model: srimanth-d/GOT_CPU
Tokenizer: srimanth-d/GOT_CPU
Although the code includes functions for initializing a GPU model, the deployed version of this application uses the CPU model due to limitations in the Hugging Face deployment environment. This may result in slower processing times but ensures compatibility across a broader range of systems.

Performance and Limitations
Performance
The use of the CPU model may lead to slower processing compared to a GPU-accelerated version. However, this approach guarantees that the application runs smoothly in environments without GPU support, such as the Hugging Face deployment platform.

Text Recognition Limitations
While the GOT model works well for extracting text in English, the OCR results for Hindi text are currently not optimal and may produce inaccurate or incomplete extractions. This limitation is important to note when uploading images containing Hindi or other non-Latin script content. Future improvements to the model or using a model optimized for Hindi text may help mitigate this issue.

Additional Information
Uploaded images are temporarily stored in the images directory.
The search functionality is case-insensitive and highlights all occurrences of the search term in the extracted text.
