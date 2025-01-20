# Find New Clients for Your Business by Monitoring Crunchbase

This project is designed to help businesses identify potential clients by monitoring Crunchbase for company data. It leverages web scraping, data analysis, and machine learning techniques to predict which companies are likely to raise funding.

## Features
- **Web Scraping:** Uses Selenium and BeautifulSoup to collect company data from Crunchbase.
- **Sample Data Generation:** Generates synthetic data for testing purposes if scraping fails.
- **Exploratory Data Analysis (EDA):** Provides visual insights into collected data.
- **Machine Learning Model:** Uses Random Forest to predict potential leads.
- **Lead Identification:** Identifies high-potential companies based on model predictions.

## Prerequisites
Ensure you have the following installed:
- Python 3.x
- Required Python libraries:
  - `pandas`
  - `numpy`
  - `selenium`
  - `beautifulsoup4`
  - `seaborn`
  - `matplotlib`
  - `scikit-learn`

Install dependencies using:
```bash
pip install pandas numpy selenium beautifulsoup4 seaborn matplotlib scikit-learn
```

## Project Structure
```
.
├── lead_generator.py  # Main Python script
├── README.md          # Project documentation
```

## Usage

1. **Clone the repository:**
```bash
git clone https://github.com/yourusername/crunchbase-lead-generator.git
cd crunchbase-lead-generator
```

2. **Run the script:**
```bash
python lead_generator.py
```

3. **Provide Crunchbase access:**
   - Ensure you have appropriate permissions to scrape Crunchbase.
   - Modify the `scrape_crunchbase` function for authentication if needed.

4. **Output:**
   - Data collected from Crunchbase will be displayed.
   - Potential leads with high probabilities will be identified and shown.

## Code Overview

### 1. `CrunchbaseLeadGenerator` Class
- **`__init__()`**: Initializes the scraper and data structures.
- **`generate_sample_data(n_samples)`**: Generates sample data if scraping fails.
- **`setup_selenium()`**: Sets up the Selenium WebDriver.
- **`scrape_crunchbase(num_pages)`**: Scrapes company data from Crunchbase.
- **`perform_eda()`**: Visualizes the data for analysis.
- **`prepare_data_for_modeling()`**: Prepares data for training.
- **`train_model()`**: Trains the Random Forest model.
- **`get_potential_leads(threshold)`**: Identifies companies likely to raise funding.

### 2. `main()` Function
- Instantiates `CrunchbaseLeadGenerator`.
- Scrapes data or falls back to sample data.
- Trains the prediction model.
- Displays potential leads.
- Performs exploratory data analysis.

## Example Output
```
Attempting to scrape Crunchbase data...
Collected data for 100 companies.

Training the model...
Model Performance:
              precision    recall  f1-score   support

         0       0.82      0.85      0.83       60
         1       0.88      0.84      0.86       40

    accuracy                           0.84      100

Identifying potential leads...
          name   industry    location  funding_amount  probability
 0    CodeCraft   Software  San Francisco     5000000.0         0.89
 1      FinFlow    Fintech      New York     3000000.0         0.76

Performing Exploratory Data Analysis...
```
