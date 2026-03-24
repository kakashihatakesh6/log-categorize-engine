<div align="center">
  
# 🪵 Log Classification & Analysis Framework 🚀

*A robust, hybrid log classification system leveraging Regex, Machine Learning, and Large Language Models (LLMs) to conquer log data of any complexity.*

</div>

---

## ✨ Features & Architecture Approach

This project implements a hybrid framework combining three complementary approaches to handle varying levels of complexity in log patterns. This ensures flexibility and maximum accuracy for predictable, complex, and poorly-labeled data patterns:

| Approach | Technology | Best For | Description |
| :--- | :--- | :--- | :--- |
| ⚡ **Rule-Based** | `Regular Expressions` | **Predictable Logs** | Handles simplified, recurring patterns easily captured using predefined rules. Extremely fast and lightweight. |
| 🧠 **Machine Learning** | `Sentence Transformer + LogReg` | **Complex Logs (Labeled)** | Manages complex patterns given sufficient training data. Generates embeddings using transformers, classified via Logistic Regression. |
| 🤖 **Generative AI**| `Large Language Models (LLMs)`| **Unknown/Unlabeled Logs** | A powerful fallback mechanism. Handles highly complex or altogether unseen patterns where labeled training data is scarce. |

---

## 🏗️ Architecture Flow

<div align="center">
  <img src="resources/arch.png" alt="Architecture Diagram" width="85%">
</div>

---

## 📂 Project Structure

```text
📦 classification-logs
 ┣ 📂 training/        # 🧠 Code for training Sentence Transformer & LogReg models + regex scripts
 ┣ 📂 models/          # 💾 Saved models (Transformer embeddings & Logistic Regression weights)
 ┣ 📂 resources/       # 📁 Resource files (Test CSVs, output logs, architecture images, etc.)
 ┣ 📜 server.py        # ⚡ FastAPI server code & API endpoints
 ┣ 📜 requirements.txt # 🐍 Python dependencies
 ┗ 📜 README.md        # 📖 Project documentation
```

---

## 🚀 Getting Started

Follow these simple instructions to set up the environment and run the classification server locally.

### 1️⃣ Install Dependencies
Ensure you have Python installed. Install the necessary Python packages by running:
```bash
pip install -r requirements.txt
```

### 2️⃣ Run the API Server
Start the FastAPI application using `uvicorn`:
```bash
python -m uvicorn server:app --reload
```

🌐 **Accessing the Server:**
Once the server is completely up and running, it will be available at:
- **Base Endpoint:** [http://127.0.0.1:8000/](http://127.0.0.1:8000/)
- **Swagger UI (Interactive Docs):** [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
- **ReDoc (Alternative Docs):** [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)

---

## 📊 Usage Guide

Ready to classify your logs? Interacting with the API is straightforward:

1. Upload a **CSV file** containing your raw logs to the FastAPI classification endpoint.
2. Ensure the CSV contains the following mandatory columns:
   - `source` : Specifies the origin of the log.
   - `log_message` : The raw log text string to be classified.

**Output Generation:**
The system will run the logs through its hybrid framework and yield a downloaded CSV file appended with an additional column:
- `target_label` : The mathematically identified and classified category for each given log entry.

---

## 📄 Disclaimer

**Copyrights Reserved.** 
This classification architecture is proprietary. Provide proper attribution as necessary.
