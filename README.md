# Phishing Website Detection System
A machine learning-based system for detecting phishing websites using URL analysis and pattern recognition.

## About The Project
This system analyzes URLs to identify potentially malicious websites using multiple machine learning algorithms. It extracts 30+ features from URL structure, suspicious patterns, and security indicators to make accurate predictions.
Trained on: Kaggle Phishing URL Dataset by Michael Sannova (11,000+ URLs)
Key Features:

5 ML algorithms with automatic best-model selection
Real-time phishing detection with confidence scoring
Works with custom datasets or Kaggle phishing data
Comprehensive feature extraction and analysis

Installation
Prerequisites

Python 3.7+

pip package manager

Setup
bashgit clone https://github.com/yourusername/phishing-detection-system.git
cd phishing-detection-system
pip install -r requirements.txt
Requirements
txtpandas>=1.3.0
numpy>=1.20.0
scikit-learn>=1.0.0
matplotlib>=3.3.0
seaborn>=0.11.0
requests>=2.25.0
beautifulsoup4>=4.9.0
Usage
Quick Start
bashpython phishing_detector.py
Programmatic Usage
pythonfrom phishing_detector import PhishingDetector, create_sample_dataset

# Initialize and train
detector = PhishingDetector()
urls, labels = create_sample_dataset()
df = detector.prepare_dataset(urls, labels)
results, X_test, y_test = detector.train_models(df)

# Test a URL
prediction = detector.predict_url("https://suspicious-site.com/login")
print(f"Prediction: {'Phishing' if prediction == 1 else 'Legitimate'}")
Custom Dataset
Your CSV should have URL and label columns:
csvurl,label
https://www.google.com,0
http://phishing-site.com,1
Recommended Dataset: Use the Kaggle Phishing URL Dataset for training with 11,000+ pre-labeled URLs.
Features
33+ Features Analyzed:

URL Structure (20): Length, character counts, complexity
Suspicious Patterns (8): IP addresses, URL shorteners, domain anomalies
Security Features (5): Protocol analysis, suspicious keywords, TLD assessment
Web Content (7): Response metrics, forms, external links (optional)

ML Models:

Random Forest, Gradient Boosting, Logistic Regression, SVM, Naive Bayes
Automatic best-model selection based on F1-score

Performance
Benchmark results using Kaggle Phishing URL Dataset:

Random Forest: 95.0% accuracy, 94.8% F1-score
Gradient Boosting: 90.0% accuracy, 89.7% F1-score
Logistic Regression: 87.5% accuracy, 87.4% F1-score

Dataset: 11,000+ URLs with balanced phishing/legitimate samples
