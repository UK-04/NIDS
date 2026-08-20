# Network Intrusion Detection System (NIDS)

## Project Overview
A machine learning-based binary classification system designed to detect denial-of-service (DoS) attacks from network traffic. This project implements an end-to-end data engineering and ML pipeline to distinguish between benign and malicious network flows using the CIC-IDS2017 dataset.

## Team Members
- Usman Khan
- Raihaan Cooper
- Luciana Pinel

## Dataset
**CIC-IDS2017** - Canadian Institute for Cybersecurity Intrusion Detection System Dataset
- **Total Samples**: 63,129 network traffic flows
- **Features**: 78 engineered flow features
- **File Formats**: CSV, JSON, and Parquet
- **Attack Types Analyzed**:
  - DoS GoldenEye
  - DoS Hulk
  - DoS slowhttptest
  - DoS slowloris
  - Benign traffic

## Project Methodology

### 1. Data Engineering Pipeline (ETL)
- **Extract**: Load data from multiple file formats (CSV, JSON, Parquet)
- **Transform**: Clean, preprocess, and combine datasets into unified dataframe
- **Load**: Prepare data for model training

### 2. Data Preprocessing
- **Encoding**: OneHotEncoder and OrdinalEncoder for categorical features
- **Scaling**: StandardScaler for feature normalization
- **Feature Selection**: SelectKBest with f_classif for top feature extraction
- **Train-Test Split**: 80-20 split for model evaluation

### 3. Machine Learning Models Evaluated
1. **Logistic Regression** - Linear classification baseline
2. **Decision Tree** - Non-linear tree-based classifier
3. **Random Forest** - Ensemble tree-based classifier
4. **K-Nearest Neighbors (KNN)** - Distance-based classifier

### 4. Model Evaluation Metrics
- Accuracy Score
- Precision Score
- Recall Score
- F1-Score
- ROC-AUC Score (Area Under Curve)
- Confusion Matrix
- Classification Report

## Results

### Best Performing Model: K-Nearest Neighbors (KNN)
- **AUC Score**: 0.9988 (99.88%)
- **Near-Perfect Classification**: High precision and recall metrics
- Successfully distinguishes DoS attacks from benign traffic with minimal false positives/negatives

## Technologies & Libraries

### Programming
- **Language**: Python 3.11.14
- **Notebook**: Jupyter Notebook (.ipynb)

### Data Processing & Engineering
- **Pandas**: Data manipulation and ETL operations
- **NumPy**: Numerical computations
- **Glob**: File system operations for batch data loading

### Machine Learning
- **Scikit-Learn (sklearn)**:
  - Classification algorithms
  - Data preprocessing and scaling
  - Feature selection
  - Model evaluation and metrics
  - Pipeline construction

### Data Visualization & Analysis
- **Matplotlib**: Plotting and chart generation
- **Seaborn**: Statistical data visualization
- **ConfusionMatrixDisplay**: Visualize classification confusion matrices

### File Format Support
- CSV (Comma-Separated Values)
- JSON (JavaScript Object Notation)
- Parquet (Columnar storage format)

## Installation & Requirements

### Prerequisites
```bash
Python 3.11.14 (or higher)
pip or conda package manager
```

### Required Libraries
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Optional Libraries
```bash
pip install xgboost  # For additional ensemble methods
pip install fastparquet  # For Parquet file support
```

## Project Structure
```
network-intrusion-detection/
├── final-project-complete_code.ipynb  # Main Jupyter notebook
├── final_project_data_sp2026_L/       # Data directory (CSV, JSON, Parquet)
├── README.md                           # This file
└── results/                            # Model outputs and visualizations
```

## Usage

### Running the Project
1. Clone or download the project repository
2. Ensure all data files are in the `final_project_data_sp2026_L/` directory
3. Install required libraries (see Requirements section)
4. Open and run the Jupyter notebook:
   ```bash
   jupyter notebook final-project-complete_code.ipynb
   ```
5. Execute cells sequentially to:
   - Load and combine datasets
   - Preprocess and engineer features
   - Train ML models
   - Evaluate model performance
   - Visualize results

## Key Findings

### Data Insights
- Successfully processed 63,129 network traffic samples from multiple file formats
- Identified and engineered 78 discriminative features for classification
- Balanced binary classification task: DoS attacks vs. benign traffic

### Model Performance
- KNN classifier achieved industry-leading 99.88% AUC
- Minimal false positives/negatives in attack detection
- Robust performance across all evaluation metrics (precision, recall, F1-score)

### Lessons Learned
- Feature engineering and selection critically impact model performance
- Ensemble methods (Random Forest) provide strong baseline performance
- Distance-based methods (KNN) excel with well-normalized, engineered features
- Cross-validation and multiple evaluation metrics essential for reliable assessment

## Future Improvements
- Implement multi-class classification for individual attack type identification
- Explore deep learning approaches (neural networks, LSTM)
- Test on real-world network traffic data
- Deploy model as web service or API for real-time intrusion detection
- Optimize hyperparameters using GridSearchCV or RandomizedSearchCV

## References
- CIC-IDS2017 Dataset: https://www.unb.ca/cic/datasets/ids-2017.html
- Scikit-Learn Documentation: https://scikit-learn.org/
- Pandas Documentation: https://pandas.pydata.org/

## License
Academic project for educational purposes.

## Contact
For questions or inquiries about this project, please contact the team members listed above.
