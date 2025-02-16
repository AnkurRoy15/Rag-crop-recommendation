# 🌾 RAG-Based Crop Recommendation System 🚀  
_A Machine Learning-Powered Agricultural Assistant Using Retrieval-Augmented Generation (RAG)_

![ChromaDB](https://img.shields.io/badge/ChromaDB-VectorDB-blue?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge)
![Gemini API](https://img.shields.io/badge/Gemini-API-red?style=for-the-badge)

---

## 📌 **Project Overview**  
The **RAG-Based Crop Recommendation System** is an intelligent **AI-powered assistant** that suggests the best crops to cultivate based on **location (state, district)** and **season**.  
This system integrates **Retrieval-Augmented Generation (RAG)** with **ChromaDB**, **FastAPI**, and **Google's Gemini API** for natural language-based recommendations.  

### **🔹 Why Use RAG for Crop Recommendation?**
- ✅ **Retrieves past crop data** based on location and season.
- ✅ **Generates accurate recommendations** using AI-powered reasoning.
- ✅ **Efficient vector search** using ChromaDB.
- ✅ **Scalable and flexible** for future enhancements.

---

## 🔧 **Tech Stack**
| Component        | Technology Used |
|-----------------|----------------|
| **Backend** | FastAPI |
| **Database** | ChromaDB (Vector Database) |
| **AI Model** | Gemini API |
| **Embedding Model** | `paraphrase-MiniLM-L3-v2` (SentenceTransformer) |
| **Programming Language** | Python |
| **Environment** | Virtual Environment (venv) |
| **Deployment** | Localhost |

---

## 🌊 **Project Architecture**
```
📚 RAG-Crop-Recommendation
│── 📂 crop_db/                  # ChromaDB storage
│── 📄 RAGcr.ipynb               # Jupyter Notebook
│── 📄 requirements.txt          # Dependencies
│── 📄 README.md                 # Documentation
│── 📄 preprocessed2.csv         # Dataset
```

---

## 📊 **Dataset**
The dataset used contains **crop information across various states and districts** in India, sourced from **public government records**.  
📌 **Columns Included:**
- **State** 🏢  
- **District** 📌  
- **Season** 🌦 (Kharif, Rabi, Whole Year)  
- **Crop** 🌱 (Wheat, Rice, Sugarcane, etc.)  

---

## ⚙ **Installation Guide**
### 🔹 **1. Clone the Repository**
```sh
git clone https://github.com/AnkurRoy15/Rag-crop-recommendation.git
cd Rag-crop-recommendation
```

### 🔹 **2. Create a Virtual Environment**
```sh
python -m venv venv
source venv/bin/activate  # For macOS/Linux
venv\Scripts\activate     # For Windows
```

### 🔹 **3. Install Dependencies**
```sh
pip install -r requirements.txt
```

---

## 🚀 **How It Works**
### **① Generate Embeddings**
The dataset is **converted into vector embeddings** using `paraphrase-MiniLM-L3-v2` from SentenceTransformers.

```python
from sentence_transformers import SentenceTransformer

model = SentenceTransformer("paraphrase-MiniLM-L3-v2")
text = "State: Punjab, District: Amritsar, Season: Kharif"
embedding = model.encode(text)
```

### **② Store Data in ChromaDB**
ChromaDB is used for **vector storage and retrieval**.


### **③ Query for Recommendations**
The user provides `state`, `district`, and `season`, and the model **retrieves the best crops**.

```python
def recommend_crop(state, district, season):
    query = f"State: {state}, District: {district}, Season: {season}"
    embedding = model.encode(query)
    results = collection.query(query_embeddings=[embedding], n_results=5)
    return results["metadatas"]
```

---

## 👀 **Future Enhancements**
🔹 **Improve Accuracy** using better NLP embeddings  
🔹 **Expand Crop Data** to include soil type & weather  
🔹 **Integrate GPT Models** for better reasoning  
🔹 **Deploy on Cloud** (AWS/GCP/Azure)  

---

## 🌟 **Contributions**
Contributions are **welcome**! If you have improvements, **fork** this repo, make changes, and submit a **pull request**.

📩 **Contact Me:** [Ankur Roy](https://www.linkedin.com/in/ankur-roy-87824427b)  
📧 **Email:** rpritam2003@gmail.com
🚀 **GitHub:** [@AnkurRoy15](https://github.com/AnkurRoy15)  

---

🔥 **Star this repo** ⭐ if you found it useful! Happy coding! 🚀

## 🌟 **RESULTS**
![Screenshot from 2025-02-11 23-11-18](https://github.com/user-attachments/assets/31d64173-65a9-4294-9fd5-dd76f717ebeb)
![Screenshot from 2025-02-11 23-15-50](https://github.com/user-attachments/assets/c2713fba-bb28-4d6f-be7d-efcbf45de24a)

