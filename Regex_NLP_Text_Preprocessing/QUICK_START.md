# 🚀 Quick Start Guide - NLP Learning

## 5-Minute Setup

### 1. Install Python Packages
```bash
pip install -r requirements.txt
```

### 2. Download spaCy Model (needed for advanced preprocessing)
```bash
python -m spacy download en_core_web_sm
```

### 3. Download NLTK Data (needed for tokenization, stopwords, etc.)
```bash
python -c "import nltk; nltk.download('punkt'); nltk.download('stopwords'); nltk.download('wordnet'); nltk.download('averaged_perceptron_tagger')"
```

### 4. Start Learning
```bash
jupyter notebook Module__regex.ipynb
```

---

## 📚 Learning Path

### **Day 1: Regex Basics**
- Open `Module__regex.ipynb`
- Learn pattern matching
- Practice with real examples

### **Day 2-3: Text Cleanup**
- Remove URLs, HTML tags, emojis
- Handle special characters
- Clean your first dataset

### **Day 4-5: Basic Preprocessing**
- Tokenization
- Lowercasing
- Stopword removal
- Stemming & Lemmatization

### **Day 6-7: Advanced Preprocessing**
- Named Entity Recognition (NER)
- Part-of-Speech (POS) Tagging
- Dependency Parsing

### **Day 8: Feature Engineering**
- Bag of Words
- TF-IDF
- Word Embeddings

### **Day 9-10: Machine Learning**
- Train classifiers
- Evaluate models
- Make predictions

---

## 💡 Common Tasks

### Clean Text with Regex
```python
import re

text = "Visit https://example.com! 😍 Contact: abc@gmail.com"

# Remove URLs
text = re.sub(r"http\S+", "", text)

# Remove emojis
text = re.sub(r"[^\w\s]", "", text)

print(text)  # "Contact: abc@gmail.com"
```

### Tokenize & Preprocess
```python
from nltk.tokenize import word_tokenize
from nltk.corpus import stopwords
from nltk.stem import WordNetLemmatizer

text = "This phone is amazing and excellent!"

# Tokenize
tokens = word_tokenize(text.lower())

# Remove stopwords
stop_words = set(stopwords.words('english'))
tokens = [w for w in tokens if w not in stop_words]

# Lemmatize
lemmatizer = WordNetLemmatizer()
tokens = [lemmatizer.lemmatize(w) for w in tokens]

print(tokens)  # ['phone', 'amazing', 'excellent']
```

### Extract Named Entities
```python
import spacy

nlp = spacy.load("en_core_web_sm")
text = "Apple Inc. is in Cupertino, California"

doc = nlp(text)
for ent in doc.ents:
    print(f"{ent.text} -> {ent.label_}")

# Output:
# Apple Inc. -> ORG
# Cupertino -> GPE
# California -> GPE
```

### TF-IDF Vectorization
```python
from sklearn.feature_extraction.text import TfidfVectorizer

documents = [
    "This phone is amazing",
    "I love this phone",
    "Battery life is excellent"
]

vectorizer = TfidfVectorizer()
vectors = vectorizer.fit_transform(documents)

print(vectors.toarray())
```

### Train a Simple Classifier
```python
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.linear_model import LogisticRegression

# Training data
texts = ["amazing", "excellent", "great", "terrible", "awful", "horrible"]
labels = [1, 1, 1, 0, 0, 0]  # 1=positive, 0=negative

# Vectorize
vectorizer = TfidfVectorizer()
X_train = vectorizer.fit_transform(texts)

# Train model
model = LogisticRegression()
model.fit(X_train, labels)

# Predict
new_text = vectorizer.transform(["amazing"])
prediction = model.predict(new_text)

print(f"Prediction: {prediction[0]}")  # 1 (Positive)
```

---

## 🎯 Project Ideas

### Beginner Projects
1. **Email Classifier** - Spam vs Legitimate
2. **Sentiment Analyzer** - Positive/Negative reviews
3. **Text Summarizer** - Extract key sentences
4. **Keyword Extractor** - Find important words

### Intermediate Projects
1. **Intent Classifier** - Understand user intent in chatbots
2. **Text Classification** - Multi-class document categorization
3. **Entity Extraction** - Extract names, places, organizations
4. **Language Detector** - Identify text language

### Advanced Projects
1. **Question Answering System** - Answer user questions
2. **Machine Translation** - Translate between languages
3. **Text Generation** - Generate new text
4. **Chatbot** - Conversational AI

---

## 🐛 Troubleshooting

### Issue: "ModuleNotFoundError: No module named 'nltk'"
**Solution**: 
```bash
pip install nltk
```

### Issue: "OSError: [E050] Can't find model 'en_core_web_sm'"
**Solution**:
```bash
python -m spacy download en_core_web_sm
```

### Issue: "Resource punkt not found"
**Solution**:
```python
import nltk
nltk.download('punkt')
```

### Issue: Jupyter kernel crashes
**Solution**:
```bash
pip install --upgrade jupyter
jupyter kernelspec list
```

---

## 📊 Useful Commands

```bash
# List installed packages
pip list

# Check Python version
python --version

# Activate virtual environment
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate

# Deactivate virtual environment
deactivate

# Start Jupyter Lab (more features than notebook)
jupyter lab

# Run specific notebook
jupyter notebook Module__regex.ipynb
```

---

## 📖 Recommended Reading Order

1. 📄 [What is NLP?](What%20is%20%20NLP.pdf)
2. 📄 [What is Regular Expression?](What%20is%20regular%20Expression.pdf)
3. 📄 [NLP Pipeline Overview](NLP%20pipeline.pdf)
4. 📓 Module__regex.ipynb
5. Continue with each module in order

---

## 🔗 Additional Resources

### YouTube Channels
- Corey Schafer's Python Tutorials
- Sentdex NLP with Python
- StatQuest with Josh Starmer

### Online Courses
- Fast.ai NLP Course
- Coursera NLP Specialization
- Udemy NLP courses

### Documentation
- NLTK: https://www.nltk.org/
- spaCy: https://spacy.io/
- Transformers: https://huggingface.co/

---

## ✅ Checklist Before Starting

- [ ] Python 3.8+ installed
- [ ] Virtual environment created
- [ ] requirements.txt installed
- [ ] spaCy model downloaded
- [ ] NLTK data downloaded
- [ ] Jupyter notebook running
- [ ] Sample datasets ready
- [ ] Excited to learn NLP! 🎉

---

## 💬 Need Help?

1. Check the PDF guides included in the project
2. Review error messages carefully
3. Search error messages on Google
4. Check NLTK/spaCy documentation
5. Open an issue in the repository

---

**Ready to become an NLP expert? Let's go! 🚀**
