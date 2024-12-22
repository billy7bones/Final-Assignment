# Final-Assignment
# Final Project: Survey Tool for Income Spending Analysis

## Overview
This project involves creating a survey tool to collect data on income and spending habits. The data collected is stored in MongoDB, processed in Python, and visualized to support insights for a healthcare product launch. The project also includes hosting the survey tool on AWS Elastic Beanstalk.

## Features
1. **Flask Web Application**: A simple survey form to collect user data including:
   - Age
   - Gender
   - Total Income
   - Expenses in categories: utilities, entertainment, school fees, shopping, healthcare

2. **Data Storage**: User data is stored in MongoDB for processing and analysis.

3. **Data Processing**:
   - Data from MongoDB is exported to a CSV file.
   - Charts created include:
     - Age-Income Distribution
     - Gender Spending Distribution

4. **Visualizations**:
   - Age groups with the highest income.
   - Gender distribution across spending categories.

5. **AWS Hosting**: Attempted to host the application on AWS Elastic Beanstalk.

---

## File Structure
```
FinalProject/
├── app.py                 # Flask application
├── process_data.py        # Data processing and visualization script
├── requirements.txt       # Dependencies
├── survey_data.csv        # Exported survey data
├── templates/
│   └── form.html          # HTML template for the survey form
├── static/
│   └── charts/            # Folder for generated charts
└── README.md              # Project documentation
```

---

## Prerequisites
- **Python 3.8**
- **Flask**
- **MongoDB**
- **AWS Elastic Beanstalk CLI**
- **Pandas, Matplotlib**

---

## How to Run the Project

### Step 1: Set Up the Environment
1. Clone the repository and navigate to the project folder:
   ```bash
   cd FinalProject
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate      # Mac/Linux
   venv\Scripts\activate       # Windows
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Step 2: Run the Flask Application
1. Start the Flask application:
   ```bash
   python app.py
   ```
2. Open the web application in your browser:
   - URL: `http://127.0.0.1:5000`

3. Fill out the survey form and submit the data.

---

## Data Processing
1. Run the `process_data.py` script to process data and generate visualizations:
   ```bash
   python process_data.py
   ```

2. Outputs:
   - `survey_data.csv`: Exported survey data.
   - `age_income_chart.png`: Age-Income distribution.
   - `gender_spending_chart.png`: Gender-Spending distribution.

---

## Hosting on AWS Elastic Beanstalk
1. Initialize Elastic Beanstalk:
   ```bash
   eb init
   ```
2. Create an environment and deploy the application:
   ```bash
   eb create finalproject-env
   eb deploy
   ```
3. Access the hosted application via the provided URL.

---

## Challenges and Resolutions
### 1. **Python Version and Environment Configuration**
   - **Problem**: Import errors and conflicts between Python 3.8 and 3.13.
   - **Resolution**:
     - Installed Python 3.8 and set it as the default version for the project.
     - Configured the correct Python environment in VS Code.

### 2. **AWS Elastic Beanstalk Deployment**
   - **Problem**: Deployment failed due to platform deprecation and Auto Scaling errors.
   - **Resolution**:
     - Attempted multiple platform versions.
     - Investigated logs and terminated failed environments.
     - Documented unresolved AWS issues for transparency.

### 3. **Visualization Errors**
   - **Problem**: Errors while generating Gender Spending charts.
   - **Resolution**:
     - Converted non-numeric data and aggregated correctly in `process_data.py`.

### 4. **Import Errors in VS Code**
   - **Problem**: Pylance errors (`Import "flask" could not be resolved`).
   - **Resolution**:
     - Configured Python interpreter to use the correct virtual environment.
     - Ignored unresolved imports as the script runs in the terminal.

---

## Limitations
- Deployment on AWS Elastic Beanstalk remains incomplete due to platform deprecation and Auto Scaling issues.

---

This project demonstrates proficiency in Flask development, MongoDB integration, data visualization, and AWS deployment, despite deployment challenges.

