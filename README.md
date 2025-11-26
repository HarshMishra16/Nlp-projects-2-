🌟 Zero-Shot Text Classification Using Hugging Face Transformers
📌 NLP Assignment — Project 2

Submitted by: Harsh Kumar

📖 Project Overview

This project demonstrates Zero-Shot Text Classification using the Hugging Face Transformers library.
Zero-shot learning allows a model to classify text without training on the specific categories, making it extremely powerful for:

Topic Classification

Intent Detection

Content Categorization

Quick NLP Prototyping

This project uses the facebook/bart-large-mnli model, one of the most widely used models for zero-shot tasks.

🧠 Objectives

✔ Understand Zero-Shot Classification
✔ Use the pipeline() API from Hugging Face
✔ Provide a text input and custom labels
✔ Allow the model to classify without training
✔ View prediction labels & confidence scores

🌐 What Is Zero-Shot Classification?

In zero-shot classification, the model uses natural language inference (NLI) to decide how well a given label fits the text—
even if it has never been trained on those labels.

Example:
Input: “I want to learn deep learning and neural networks.”
Candidate labels: ["education", "sports", "technology"]
Model will infer which label fits best.

🗂️ Project Structure
📁 ZeroShot-Classification/
│── zero_shot_classifier.ipynb   # Main notebook/script
│── README.md                    # Documentation

📦 Install Dependencies

Run in Google Colab or Terminal:

pip install transformers accelerate -q

🧩 Code Used in This Project
🔹 Import Pipeline
from transformers import pipeline

🔹 Load Zero-Shot Classification Model
classifier = pipeline(
    "zero-shot-classification",
    model="facebook/bart-large-mnli"
)

🔹 Input Text and Labels
text = "I want to learn deep learning and neural networks."

candidate_labels = ["education", "sports", "technology", "politics"]

🔹 Run Classifier
result = classifier(text, candidate_labels)
result

🔹 Print Final Predictions
print("Text:", result["sequence"])
print("\nPredictions:")
for label, score in zip(result["labels"], result["scores"]):
    print(f"{label}: {score:.4f}")

📊 Sample Output
Text: I want to learn deep learning and neural networks.

Predictions:
education: 0.8521
technology: 0.1472
politics: 0.0003
sports: 0.0002

🏁 Key Features of This Project

✔ No need to train a model
✔ Works with any label you give
✔ BART MNLI provides strong zero-shot accuracy
✔ Simple, fast, and ideal for experimentation

🚀 Possible Extensions

Add multiple sentences for batch classification

Compare BART with RoBERTa MNLI

Deploy the pipeline using FastAPI

Convert the script into a function-based Python module

🎉 Conclusion

This project showcases how easy and powerful Zero-Shot Classification can be using Hugging Face Transformers.
It helps classify any text into any custom categories without training — making it perfect for real-world NLP applications.
