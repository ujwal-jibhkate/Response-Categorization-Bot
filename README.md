# Complaint Classifier Using Generative AI

This repository demonstrates a complaint and response classification system built using Large Language Models (LLMs) and a hierarchical categorization approach. The solution integrates **watsonx.ai** and **Azure OpenAI** models to efficiently classify bulk responses into predefined categories and subcategories.

## Table of Contents
- [Overview](#overview)
- [Problem Statement](#problem-statement)
- [Solution](#solution)
- [Technical Implementation](#technical-implementation)
  - [Single Response Handling](#single-response-handling)
  - [Multiple Response Handling](#multiple-response-handling)
- [Implementation Steps](#implementation-steps)
  - [Prerequisites](#prerequisites)
  - [Configuration](#configuration)
  - [Execution](#execution)
- [Acknowledgments](#acknowledgments)

## Overview
The project leverages Generative AI models to classify customer responses into a hierarchical structure of categories and subcategories. By automating this process, the system reduces manual effort and ensures accurate and efficient response management.

## Problem Statement
Manually categorizing customer responses into relevant categories and subcategories can be time-consuming and error-prone. This project addresses the challenge by introducing a scalable, automated classification solution using Generative AI.

## Solution
The classification system uses a JSON structure to define the hierarchy of categories and subcategories. Responses are classified based on:
1. **Category ID**: Identifies the main category.
2. **Subcategory ID**: Identifies the subcategory within the category.

The system supports two modes:
- **Single Response Classification**: Handles one response at a time.
- **Bulk Classification**: Processes multiple responses from a CSV file.

## Technical Implementation
### Single Response Handling
- The JSON structure of categories and subcategories is fed into the LLM as context.
- The model generates a classification result in the form `[category_id, subcategory_id]`.
- This output is converted into actionable data for downstream processing.

### Multiple Response Handling
- Input responses are provided in a CSV file with a single column (`responses`).
- Each response is classified iteratively, and the results are visualized using dashboards and pie charts to display trends.

## Implementation Steps
### Prerequisites
1. **Python Environment**:
   - Python 3.10 or 3.11.
   - Install required libraries listed in `requirements.txt`.

2. **Generative AI Models**:
   - **watsonx.ai**: Uses the `FLAN_T5_XXL` model.
   - **Azure OpenAI**: Uses the `GPT-35-TURBO` model.

3. **Tools**:
   - Visual Studio Code or any Python IDE.

### Configuration
1. Clone the repository:
   ```bash
   git clone <repository-link>
   cd <repository-name>

2. Install dependencies:

   ```bash
   pip install -r requirements.txt

3. Update utils.py with the appropriate API keys and configurations:

- watsonx.ai:
  - PROJECT_ID: Your project ID for watsonx.ai.
  - API_KEY: Your watsonx.ai API key.

- Azure OpenAI:
  - API_KEY: Azure OpenAI subscription key.
  - API_VERSION: API version being used.
  - ENDPOINT: Azure endpoint URL.
 
### Execution

1. Run the script:

   ```bash
   streamlit run main.py

2. A browser tab will open displaying the interface. If it does not, follow the local link in the terminal to open the application.

3. Input responses for classification:

  - For single response classification, enter one response in the input field.
  - For bulk classification, upload a CSV file containing responses.

## Acknowledgments
This project leverages advanced LLMs and frameworks such as watsonx.ai and Azure OpenAI to demonstrate the power of Generative AI in automating customer response classification.
