# Digitization Cost Estimator

A comprehensive web application for estimating document digitization costs, comparing cloud storage options, and analyzing uploaded documents with AI assistance.

## Overview

This Streamlit-based tool helps organizations plan and budget for document digitization projects by calculating costs across various parameters and recommending optimal storage solutions among major cloud providers (AWS, GCP, and Azure).

## Features

- **Cost Estimation Engine** - Calculate digitization expenses based on document volume, storage requirements, labor costs, and OCR processing needs
- **Cloud Provider Comparison** - Compare real-time pricing across Amazon S3, Google Cloud Storage, and Microsoft Azure
- **Interactive Visualizations** - Explore cost breakdowns and trends through intuitive charts
- **AI Document Analysis** - Summarize uploaded PDFs using LangChain and Hugging Face models
- **Export Capabilities** - Generate detailed reports in PDF or CSV format
- **Smart Recommendations** - Receive suggestions for the most cost-effective storage solution
- **Persistent Sessions** - Retain cost data and document history between sessions

## Technology Stack

| Component | Technologies |
|-----------|-------------|
| Frontend | Streamlit |
| Backend | Python, Pandas, NumPy |
| AI/ML | LangChain, Hugging Face, FAISS, sentence-transformers |
| Document Processing | PyMuPDF, PDFPlumber |
| Data Visualization | Altair, Matplotlib |
| Deployment | Docker (ARM64 + AMD64 support) |
| Cloud Integration | AWS, Azure, GCP pricing APIs |

## Application Preview

| Estimator Tab | Provider Comparison | PDF Summary Assistant |
|---------------|---------------------|----------------------|
| ![estimator](screenshots/estimator.png) | ![comparison](screenshots/comparison.png) | ![summary](screenshots/summary.png) |

## Getting Started

### Prerequisites
- Python 3.8+
- Hugging Face API token (for AI summarization features)

### Installation

1. Clone the repository
  bash
   git clone https://github.com/yourusername/digitization-cost-estimator.git
   cd digitization-cost-estimator


2. Set up environment variables
  bash
   cp .env.example .env

   Open `.env` and add your Hugging Face API token:

   HUGGINGFACEHUB_API_TOKEN=your_token_here

3. Install dependencies and run
   
   bash
   
   pip install -r requirements.txt
   
   streamlit run app.py

### Docker Deployment

For containerized deployment:

bash

docker build --platform=linux/amd64 -t digitization-cost-app .

docker run -p 8501:8501 digitization-cost-app

## Project Structure

├── app.py                    # Main Streamlit application

├── Summarize_PDF.py          # PDF analysis and LLM logic

├── requirements.txt          # Python dependencies

├── Dockerfile                # Container configuration

├── /uploads                  # PDF storage directory

├── /screenshots              # Application previews

├── /data                     # Storage for pricing data and session history

└── .env                      # Environment variables (not committed)
