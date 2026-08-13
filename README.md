# ML Problem Capstone

A capstone assignment demonstrating the machine learning lifecycle on an Airbnb NYC listing prediction problem. The project includes data exploration, feature engineering, model selection, and model evaluation — with a Streamlit app to interactively explore model predictions.

## Table of Contents
- [Features](#features)
- [Dataset](#dataset)
- [Results](#results)
- [Getting Started](#getting-started)
  - [Requirements](#requirements)
  - [Installation](#installation)
  - [Run the Streamlit App](#run-the-streamlit-app)
- [Project Structure](#project-structure)
- [How to Reproduce Experiments](#how-to-reproduce-experiments)
- [Notes and Improvements](#notes-and-improvements)
- [License](#license)
- [Contact](#contact)

## Features
- Logistic Regression baseline
- Data exploration & visualization
- Feature engineering and model selection
- Hyperparameter tuning
- Binary classification pipeline
- Streamlit app for interactive demonstration

## Dataset
This project uses the InsideAirbnb dataset for New York City (December 2021).

Source: https://insideairbnb.com/get-the-data/

Recommended dataset file (example): listings for New York City for December 2021. InsideAirbnb typically provides compressed CSV files (listings.csv.gz). Instead of committing this large file to the repository, this project includes a small downloader script that fetches the dataset and places it into the `data/` folder.

Expected local path after download: `data/listings_dec_2021.csv`

## Results
Summarize key results and metrics here (accuracy, precision, recall, F1, ROC-AUC), and add a brief interpretation. Example placeholder:
- Logistic Regression (best): Accuracy: 0.82 | F1-score: 0.79 | ROC-AUC: 0.87
Add a screenshot or table of final evaluation if available.

## Getting Started

### Requirements
- Python 3.8+ (specify exact version you used)
- See `requirements.txt` for full dependency list

### Installation
1. Clone the repo:
   git clone https://github.com/aflusser/ML-problem-capstone.git
2. Create and activate a virtual environment:
   python -m venv venv
   source venv/bin/activate  # macOS/Linux
   venv\Scripts\activate     # Windows
3. Install dependencies:
   pip install -r requirements.txt

4. Set required environment variables (if used):
   - `OPENAI_API_KEY` (if any notebook or script uses OpenAI services)

### Download the dataset (recommended)
Instead of committing the large .xlsx/.csv file to the repo, use the included downloader script to fetch the InsideAirbnb dataset for New York City (Dec 2021):

From the project root, run:

python scripts/download_insideairbnb.py \
  --url "<INSIDE_AIRBNB_LISTINGS_URL>" \
  --output data/listings_dec_2021.csv

How to find the correct URL on InsideAirbnb:
1. Go to https://insideairbnb.com/get-the-data/
2. Find the United States → New York → New York City section and locate the listing date `2021-12-01` (or December 2021).
3. Copy the `listings.csv.gz` asset link and paste it into `--url` above. Example (pattern):
   https://data.insideairbnb.com/united-states/ny/new-york-city/2021-12-01/data/listings.csv.gz

The downloader will decompress `.gz` files automatically and write a CSV at the path you give with `--output`.

### Run the Streamlit App
From the project root:

streamlit run app.py

The app will open in your browser (usually at http://localhost:8501).

## Project Structure
List the most important files:
- `app.py` — Streamlit application
- `notebooks/` — exploratory analysis and modeling notebooks
- `data/` — (not included) dataset files or scripts to download datasets
- `scripts/` — helper scripts (data download, preprocessing)
- `models/` — saved model artifacts (if any)
- `requirements.txt` — Python dependencies
- `README.md` — this file

## How to Reproduce Experiments
1. Ensure the dataset is placed at `data/listings_dec_2021.csv` (use the downloader script above).
2. Run preprocessing and feature engineering notebooks or scripts:
   - `notebooks/01_data_cleaning.ipynb`
   - `notebooks/02_feature_engineering.ipynb`
3. Train models and run hyperparameter tuning (notebook or script):
   - `notebooks/03_modeling.ipynb`
4. Evaluate models and produce metrics:
   - `notebooks/04_evaluation.ipynb`

Note: Document exact random seeds, train/test splits, and cross-validation setup for reproducibility.

## Notes and Improvements
- Add dataset link and citation.
- Note the computing resources and runtime for training.
- Provide examples of input/output for the Streamlit app.
- Consider adding unit tests for preprocessing functions and a CI workflow.
- If using OpenAI APIs, note why and where they are used; otherwise remove the env var requirement.

## License
Add a license (e.g., MIT). If you want, add `LICENSE` file and badge.

## Contact
Your Name — aflusser
Project link: https://github.com/aflusser/ML-problem-capstone
