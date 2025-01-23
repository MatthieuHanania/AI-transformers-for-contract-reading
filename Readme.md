# PDF Field Extraction with Transformers
Matthieu Hanania

This project leverages Transformer models to automatically identify fields in PDF files, such as titles, names, or dates. It is designed to extract valuable information from complex documents by combining the power of NLP models and PDF preprocessing.

## Features
- Text extraction from PDF files.
- Generation of sample sentences
- Configurable model to adapt to various document types.

## Requirements and Installation

This project mainly needs theses requirements
- Python 3.8 or higher
- The following libraries (installable via `pip`):
  - `transformers`
  - `torch`
  - `PyPDF2`
  - `pandas`
  - `numpy`

Installation with
```bash
pip install -r requirements.txt
```


## Project Structure

- `main.ipynb`: The main notebook that handles field identification and classification using Transformers. 
- `jsonGenerer.ipynb`: Generates JSON outputs for the extracted information. Used to train the model
- `Pdf2Text.py`: A module to convert PDF files into plain text.

## Explanation of Code Files

### `Pdf2Text.py`
This script handles the conversion of PDF files into plain text using the `PyPDF2` library. It reads the PDF, extracts text from each page, and combines the content into a single string. Example usage:


### `main.ipynb`
This notebook is the core of the project. It:
1. Loads and preprocesses text
2. Uses the Transformers model `Camenbert` pre-trained on several French sentences, from the Hugging Face `transformers` library to analyze and classify key fields within the text.

#### About Transformers:
Transformers are state-of-the-art models for natural language processing (NLP). They use attention mechanisms to understand the context and relationships between words in a sentence. In this project, the pre-trained model is fine-tuned or adapted to identify specific fields in the text, such as titles, dates, and names.

#### How Transformers Work in the Code:
- **Input:** The text is tokenized into smaller units (tokens) using a tokenizer provided by the Transformer model.
- **Model Application:** The tokenized input is passed through the Transformer model to extract features and context-aware representations of the text.
- **Classification:** A classification head (e.g., a feedforward neural network) is used on top of the Transformer to categorize text segments into predefined field types.

### `jsonGenerer.ipynb`
This notebook takes the extracted and classified information and structures it into a JSON format for easy integration with other applications. It ensures that the data is organized and accessible.

---

Created with ❤️ by Matthieu Hanania.
