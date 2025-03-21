# LCRS - Legal Citation Recommendation System

## Project Description

**Law Citation Assistant** is a system designed to streamline the legal research process by recommending relevant citations for a given case. By analyzing various case inputs—such as petitioners, respondents, case type, keywords, material facts, and relevant legal provisions—the system significantly reduces the time required for legal professionals to find pertinent citations. It enhances efficiency by enabling lawyers to quickly access applicable statutes, case laws, and judicial precedents.

## System Features

### 1. Input Analysis
- Users provide essential case details, including:
  - Petitioner & Respondent
  - Case Type
  - Keywords
  - Material Facts
  - Relevant Constitutional Articles, Laws, and Acts
  - Case Domain Brief

### 2. Legal Framework Identification
- The system identifies relevant legal frameworks, statutes, constitutional provisions, and case classifications based on the provided input data.
- Ensures all potential legal aspects of the case are considered.

### 3. Citation Recommendation
- The system recommends relevant legal citations and references that align with the case's facts and legal context.
- Provides case precedents and other legal documents crucial for supporting legal arguments.

### 4. Summarization of Judgments
- Offers a summarized overview of cited judgments.
- Helps legal professionals quickly understand the essence of past rulings and their relevance to the current case.

## Methodology

### Building Model & FAISS Vector Space
1. **Data Collection**: Kaggle (Indian Supreme Court judgments dataset).
2. **Text Extraction**: Extracting text from judgment PDFs and splitting the text into chunks.
3. **Chunking**: Categorizing text into sections (Act, Judgment, Headnote).
4. **Embedding Creation**: Converting chunks into embeddings and storing them in a FAISS vector space.

### Input Processing & Output Generation
1. **Extracting text** from the given PDF and creating chunks.
2. **Creating embeddings** of respective chunks.
3. **Finding top relevant citations** using FAISS Similarity Search.
4. **Displaying top cited judgments** on the UI.

## Technologies Used

### Text Extraction
- **pdfplumber**: Extracts text from judgment PDFs.

### Pre-processing
- **NumPy**: For array manipulation and numerical operations.
- **Pandas**: For arithmetic operations.
- **Regex**: Used for splitting text into meaningful chunks based on patterns.

### Embedding
- **LegalBERT**: Pre-trained encoder on legal texts, used for generating contextual embeddings.

### Indexing & Context Matching
- **FAISS**: A vector space database developed by Facebook, used for similarity search and retrieving the most relevant citations.

### UI & Backend
- **React**: Frontend framework for user interaction.
- **Flask**: Backend framework to process requests and return results.

## Output Demonstration

### 1. Input Case File
Users can upload a case file to the system.

### 2. Recommended Top Citations
The system returns the most relevant case citations based on the input.

### 3. Retrieving Specific Judgment Details
Users can view detailed information about a specific cited judgment.

### 4. Displaying Summaries
A concise summary of the judgment is provided for quick reference.


## Installation & Usage

### Prerequisites
Ensure you have the following installed:
- Python 3.x
- Node.js
- pip (Python package manager)
- npm (Node package manager)

### Steps to Set Up
1. Clone the repository:
   ```bash
   git clone https://github.com/ovuiproduction/Legal-Citation-Recommandation-System
   cd Legal-Citation-Recommandation-System
   ```
2. Set up the backend:
   ```bash
   cd backend
   pip install -r requirements.txt
   python app.py
   ```
3. Set up the frontend:
   ```bash
   cd frontend
   npm install
   npm start
   ```
4. Open the browser and navigate to `http://localhost:3000` to use the application.
