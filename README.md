An intelligent mobile application that analyzes MRI brain scans to detect brain tumors with high accuracy using advanced machine learning techniques.

📑 Table of Contents

Overview
Features
Tech Stack
Model Performance
Installation
Usage
API Documentation
Contributing
Research Paper

🎯 Overview
BrainScan AI is a revolutionary mobile application that democratizes brain tumor diagnosis by providing instant, accurate analysis of MRI scans. Using state-of-the-art machine learning models, the app can detect brain tumors with up to 97% accuracy, making preliminary diagnosis accessible to healthcare professionals worldwide.
✨ Features

🔬 High Accuracy Detection: 97% accuracy using optimized SVM model
📱 Cross-Platform: Available on both iOS and Android
⚡ Real-time Processing: Instant analysis of uploaded MRI scans
🏥 Medical Grade: Suitable for preliminary diagnosis assistance
☁️ Cloud Integration: Secure storage and processing via Firebase
📊 Detailed Reports: Comprehensive analysis with confidence scores
🔒 HIPAA Compliant: Secure handling of medical data
📈 Model Comparison: SVM, CNN, Random Forest, and VGG16 implementations

🛠️ Tech Stack
Mobile Development

Flutter - Cross-platform mobile framework
Dart - Programming language

Machine Learning

Python - Core ML development
Scikit-learn - SVM implementation
TensorFlow/Keras - CNN and VGG16 models
OpenCV - Image preprocessing
NumPy & Pandas - Data manipulation

Backend & Cloud

Firebase - Authentication, storage, and hosting
Flask - ML model API service
Google Cloud Platform - Model deployment

Data & Training

Brain MRI Dataset - 3000+ labeled images
Data Augmentation - Enhanced training dataset
Cross-validation - 5-fold validation for model reliability


Model Selection Rationale
SVM chosen for production due to:

Highest accuracy and reliability
Better performance on limited dataset
Faster inference time for mobile deployment
Lower computational requirements



🚀 Installation
Prerequisites

Flutter SDK (>=2.0.0)
Python 3.8+
Firebase account
Android Studio / Xcode

Mobile App Setup
bash# Clone the repository
git clone https://github.com/Dhiren-Sidhwani/BrainScan-AI.git
cd BrainScan-AI

# Install Flutter dependencies
flutter pub get

# Run the app
flutter run
ML Model Setup
bash# Navigate to ML directory
cd ml_models

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Download trained models
python download_models.py

# Run the Flask API
python app.py
Firebase Configuration

Create a new Firebase project
Add your google-services.json (Android) and GoogleService-Info.plist (iOS)
Enable Authentication and Cloud Storage
Update Firebase configuration in lib/config/firebase_config.dart

💻 Usage
For Healthcare Professionals

Login/Register - Secure authentication
Upload MRI Scan - Select image from gallery or camera
Processing - AI model analyzes the scan
Results - View detailed analysis with confidence score
Save/Share - Store results or share with colleagues

For Developers
dart// Example: Using the brain scan service
import 'package:brainscan_ai/services/brain_scan_service.dart';

final BrainScanService _scanService = BrainScanService();

Future<ScanResult> analyzeMRI(File imageFile) async {
  try {
    final result = await _scanService.analyzeBrainScan(imageFile);
    return result;
  } catch (e) {
    throw Exception('Analysis failed: $e');
  }
}
📋 API Documentation
Analyze Brain Scan
httpPOST /api/analyze
Content-Type: multipart/form-data

Parameters:
- image: MRI scan image file
- patient_id: (optional) Patient identifier
Response:
json{
  "success": true,
  "prediction": "tumor_detected",
  "confidence": 0.972,
  "model_used": "svm",
  "processing_time": 2.3,
  "timestamp": "2025-01-15T10:30:00Z"
}
🔬 Research Paper
This project has been accepted for publication at WCONF 2024:
"Precision Diagnostics in Neuroimaging: SVM-Based Approaches for Brain Tumor Identification"
Abstract: This paper presents a comprehensive study on applying Support Vector Machine (SVM) algorithms for automated brain tumor detection in MRI images, achieving 97.2% accuracy through optimized feature extraction and preprocessing techniques.
🤝 Contributing
We welcome contributions! Please see our Contributing Guidelines for details.
Development Setup

Fork the repository
Create a feature branch (git checkout -b feature/AmazingFeature)
Commit changes (git commit -m 'Add AmazingFeature')
Push to branch (git push origin feature/AmazingFeature)
Open a Pull Request

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.
🙏 Acknowledgments

Dataset: Brain MRI Images for Brain Tumor Detection
Research Guidance: VESIT Faculty and IEEE Conference Reviewers
Open Source Libraries: Scikit-learn, Flutter, Firebase communities

📞 Contact
Dhiren Sidhwani

📧 Email: dhirusidhwani@gmail.com
💼 LinkedIn: dhiren-sidhwani
🐙 GitHub: @Dhiren-Sidhwani


⭐ If this project helped you, please give it a star! ⭐
