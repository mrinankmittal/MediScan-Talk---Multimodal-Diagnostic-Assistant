🩺 MediScan & Talk: Multimodal Diagnostic Assistant
🚀 Overview

MediScan & Talk is an AI-powered Multimodal Diagnostic Assistant designed to assist healthcare professionals by analyzing chest X-ray images and providing intelligent, evidence-based medical explanations through conversational AI.

The system combines:

🖼️ Computer Vision for disease detection
🤖 Large Language Models (LLMs)
📚 Corrective Retrieval-Augmented Generation (CRAG)
⚡ FastAPI Backend
🌐 Streamlit Frontend

The platform allows users to upload a chest X-ray, receive disease predictions, ask medical questions using text, and obtain contextual explanations supported by retrieved medical knowledge.

Problem Statement

Radiologists and healthcare practitioners often spend significant time reviewing medical images and consulting references before making diagnostic decisions.

MediScan & Talk aims to:

Detect thoracic diseases from chest X-rays
Provide contextual disease explanations
Enable natural language 
Reduce information retrieval time
Improve accessibility to medical insights

Key Features
🫁 Chest X-Ray Disease Detection
Multi-label classification of chest X-ray images
Detects 14 thoracic diseases
Powered by DenseNet121 transfer learning

📚 Corrective RAG (CRAG)
Retrieves relevant medical information
Verifies and refines retrieved context
Reduces hallucinations in generated responses

🤖 AI Medical Assistant
Conversational healthcare assistant
Answers disease-related questions
Provides diagnostic explanations

🌐 Interactive Web Application
User-friendly Streamlit interface
FastAPI backend services
Real-time inference and responses

🩻 Diseases Detected

The model can identify:

Atelectasis
Cardiomegaly
Effusion
Infiltration
Mass
Nodule
Pneumonia
Pneumothorax
Consolidation
Edema
Emphysema
Fibrosis
Pleural Thickening
Hernia

These labels are derived from the NIH Chest X-Ray dataset.

Dataset
NIH Chest X-Ray Dataset
Over 50,000 labeled chest X-ray images used after preprocessing and filtering.
Multi-label disease annotations
Medical image classification benchmark dataset

Dataset Source:

https://www.kaggle.com/datasets/khanfashee/nih-chest-x-ray-14-224x224-resized

🔄 Image Preprocessing Pipeline

To improve image quality and model performance:

CLAHE

Enhances local contrast and highlights subtle abnormalities.

Gaussian Blur

Removes image noise while preserving important structures.

Normalization

Scales pixel values between 0 and 1.

RGB Conversion

Converts grayscale X-rays into 3-channel format for deep learning models.

🔀 Data Augmentation

The following augmentation techniques are applied:

Random Rotation
Horizontal Flip
Random Zoom
Random Resized Crop
Brightness Adjustment
Contrast Adjustment

These techniques improve model generalization and reduce overfitting.

🧠 Deep Learning Model
DenseNet121

The project uses a pretrained DenseNet121 architecture for multi-label disease classification.

Why DenseNet121?
Efficient feature reuse
Strong medical imaging performance
Reduced vanishing gradient issues
Lower parameter count than traditional CNNs

Training Configuration:

Parameter	Value
Architecture	DenseNet121
Input Size	224 × 224
Epochs	12
Batch Size	16
Learning Rate	8e-4
Loss Function	BCEWithLogitsLoss
Optimizer	AdamW
📈 Model Performance
Validation Results
Metric	Value
Validation AUC	0.8266
Validation Loss	0.2391

Best model checkpoint saved automatically during training.

📚 Corrective Retrieval-Augmented Generation (CRAG)

Traditional RAG systems may retrieve irrelevant or incomplete information.

Our Corrective RAG pipeline:

Retrieves medical context
Evaluates retrieval quality
Corrects weak retrievals
Generates grounded responses
Reduces hallucinations

Benefits:

More accurate answers
Evidence-based explanations
Improved reliability for healthcare use cases

Future Enhancements
Medical report generation
Multi-modal LLM integration
Explainable AI visualizations (Grad-CAM)
Real-time doctor consultation support
Multi-language voice interaction
Electronic Health Record (EHR) integration
⚠️ Disclaimer

This project is intended for educational and research purposes only.

MediScan & Talk is not a substitute for professional medical diagnosis, treatment, or clinical decision-making. Always consult qualified healthcare professionals for medical advice.
