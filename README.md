# 🍽️ FlavorFinder_ML

**FlavorFinder_ML** is an intelligent backend API that provides food recommendations based on flavor profiles. It's powered by machine learning and designed to interact with a frontend interface or be used standalone for recommendation tasks.

---

## 🚀 Features

- FastAPI/Flask-based backend (`app.py`)
- Trained on Swiggy-style dataset (`swiggy.csv`)
- Ready-to-use `/recommend` API endpoint
- Easily extendable with LLMs or fine-tuned models

---

## 📂 Project Structure

FlavorFinder_ML/
│
├── backend/
│ ├── app.py # Flask backend API
│ ├── swiggy.csv # Dataset
│ ├── fine_tuned_model/ # Model & tokenizer configs
│ └── ... # Preprocessing, config, tokenizer
│
├── frontend/
│ └── index.html # UI placeholder
│
└── README.md


---

## 🛠️ How to Run the Backend

```bash
# Step 1: Install dependencies
pip install flask pandas

# Step 2: Run the app
python backend/app.py
Then visit http://localhost:5000 or use the /recommend endpoint.

📦 Requirements
Python 3.8+

Flask

Pandas

🔮 Future Enhancements
Add LLM-based explanations

Integrate frontend search and filters

Deploy on Render / HuggingFace Spaces

📬 Contact
Feel free to connect if you want to collaborate or learn more!

