# AI-Augmented Thematic Analysis (AATA) Workflow

This repository contains the official code and sample data for the methodology presented in the paper:

> **"An Approach to AI-Augmented Thematic Analysis for Large-Scale Systematic Literature Reviews in Management Science"**  
> *Wisu Suntoyo, Yos Sunitiyoso, Manahan P. Siallagan*  

This workflow provides a transparent, replicable "glass-box" method for conducting large-scale Systematic Literature Reviews (SLRs) by programmatically using Generative AI.

## Description

The traditional SLR process faces significant challenges of scale and semantic ambiguity (the "keyword problem"). This AATA workflow addresses these issues by using a Python script within a Google Colab environment to interact with the Google Gemini API. The method transforms the ad-hoc, "black-box" use of conversational AI into a documented, auditable, and academically rigorous process.

The core of the method is the `aata_workflow.ipynb` notebook, which performs two main functions:
1.  **Programmatic Analysis:** Iterates through a corpus of literature (stored in a Google Sheet), sending each paper's title and abstract to the Gemini API against a detailed, structured prompt. It then parses the AI's JSON response and saves the structured classifications back to a new Google Sheet.
2.  **Funnel Statistics:** Reads the enriched dataset and applies a sequential screening funnel to quantitatively demonstrate the paper selection process, directly supporting the creation of a PRISMA flow diagram.

## Getting Started

Follow these steps to set up and run the workflow.

### Prerequisites

*   A Google Account (for Colab and Google Sheets).
*   A Google AI API Key for the Gemini model. You can get one from [Google AI Studio](https://aistudio.google.com/app/apikey).

### Setup and Configuration

1.  **Clone or Download the Repository:** Get a local copy of all the files.

2.  **Open in Google Colab:** The easiest way to run the notebook is to click the "Open in Colab" badge at the top of this README. This will open the notebook directly in your Google Colab environment.

3.  **Configure Secrets:** Before running, you must provide your authentication keys to the Colab notebook. In the left-hand sidebar, click the **Key (🔑)** icon to open the "Secrets" tab. Add the following three secrets:
    *   `GOOGLE_API_KEY`: Paste your API key from Google AI Studio.
    *   `SOURCE_SPREADSHEET_KEY`: The key for your Google Sheet containing the source literature data. You can find this key in the sheet's URL (the long string of characters between `/d/` and `/edit`).
    *   `DESTINATION_SPREADSHEET_KEY`: The key for the blank Google Sheet where the results will be written.

4.  **Prepare Your Data:**
    *   This repository includes `sample_data.csv` to show the required format.
    *   For your own project, create a Google Sheet with your literature corpus. It must contain the columns: `Title`, `Abstract`, and `Index Keywords`.
    *   Share this Google Sheet with the service account email you use for Colab authentication to grant the script read access.

### How to Run

Once the setup is complete, you can run the notebook by executing the cells sequentially from top to bottom. The notebook is clearly commented to guide you through the process.

## File Manifest

*   **`aata_workflow.ipynb`**: The main Google Colab notebook containing the AATA script and funnel analysis.
*   **`README.md`**: This file, providing an overview and instructions.
*   **`requirements.txt`**: A list of the required Python packages for the notebook.
*   **`sample_data.csv`**: A sample of 100 records to demonstrate the required data format for the source Google Sheet.