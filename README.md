FlavorFinder: AI Restaurant Recommender
🍽️ Project Overview
FlavorFinder is an AI-powered web application designed to provide personalized restaurant recommendations based on user preferences and location. It utilizes a fine-tuned Large Language Model (LLM) as its backend to generate intelligent suggestions, presented through a sleek, modern, and minimalist frontend interface.

The application guides users through a series of questions about their cuisine preferences, dining atmosphere, budget, and desired minimum rating. It also supports getting the user's current location to provide nearby recommendations. Once preferences are submitted, the LLM processes the input and returns a list of tailored restaurant suggestions. Users can then view detailed information for each restaurant and simulate a booking process.

✨ Features
Personalized Recommendations: Get restaurant suggestions tailored to your specific preferences using a fine-tuned LLM.

Preference Filtering: Select desired cuisine types, dining atmospheres, and budget ranges (using a slider).
# FlavorFinder: AI Restaurant Recommender

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD43B?style=for-the-badge&logo=huggingface&logoColor=black)

## 🍽️ Project Overview

**FlavorFinder** is an AI-powered web application designed to provide personalized restaurant recommendations based on user preferences and location. It utilizes a fine-tuned Large Language Model (LLM) as its backend to generate intelligent suggestions, presented through a sleek, modern, and minimalist frontend interface.

The application guides users through a series of questions about their cuisine preferences, dining atmosphere, budget, and desired minimum rating. It also supports getting the user's current location to provide nearby recommendations. Once preferences are submitted, the LLM processes the input and returns a list of tailored restaurant suggestions. Users can then view detailed information for each restaurant and simulate a booking process.

## ✨ Features

* **Personalized Recommendations:** Get restaurant suggestions tailored to your specific preferences using a fine-tuned LLM.

* **Preference Filtering:** Select desired cuisine types, dining atmospheres, and budget ranges (using a slider).

* **Minimum Rating Selection:** Specify a minimum average rating for recommendations using interactive stars.

* **Location-Based Search:** Input a city/neighborhood or use your browser's geolocation to find restaurants nearby.

* **Elegant UI/UX:** A clean, minimalist design with a blue, grey, and white color palette inspired by modern forms, ensuring a delightful user experience.

* **Two-Panel Login:** A unique two-column layout for the login/signup page, transitioning to a single-card design for all other interactions.

* **Detailed Restaurant View:** Click on any recommendation to see a comprehensive detail page with mock information (address, hours, phone, links).

* **Simulated Booking:** A modal for simulating table bookings, allowing date, time, and guest selection.

* **Model Evaluation Script:** A utility script (`evaluate_model.py`) to programmatically test the model's output structure and qualitative aspects.

## 🛠️ Technologies Used

**Backend:**

* **Python:** Core programming language.

* **Flask:** Web framework for the REST API.

* **Hugging Face Transformers:** For loading and running the fine-tuned LLM.

* **PyTorch:** Deep learning framework (used by Transformers).

* **Flask-CORS:** For handling Cross-Origin Resource Sharing.

* **Requests:** For the evaluation script to call the Flask API.

* **Matplotlib, NumPy:** For basic model evaluation visualizations.

**Frontend:**

* **HTML5:** Structure of the web pages.

* **CSS3:** Styling, with custom CSS for the minimalist design.

* **Tailwind CSS (CDN):** Utility-first CSS framework for rapid UI development.

* **JavaScript (Vanilla JS):** For all interactive elements, dynamic content, and API calls.

* **Font Awesome (CDN):** For icons across the UI.

## 📁 Project Structure

```
FlavorFinder_ML/
├── backend/
│   ├── app.py                  # Flask API for restaurant recommendations
│   ├── evaluate_model.py       # Script to test and visualize model output accuracy
│   ├── requirements.txt        # Python dependencies for the backend
│   └── (fine_tuned_model_swiggy_colab/) # Placeholder: Model files are NOT included in Git repo
├── frontend/
│   └── index.html              # Frontend web application (HTML, CSS, JS)
├── swiggy.csv                  # Placeholder: Dataset is NOT included in Git repo
└── README.md                   # This file

```

**Note on Model and Dataset:**
Due to their large file sizes, the `fine_tuned_model_swiggy_colab/` directory (containing the LLM weights) and the `swiggy.csv` dataset are **NOT** included in this GitHub repository. This is standard practice for large machine learning assets.

## 🚀 Local Setup and Running the Application

To run this project locally, you will need to manually provide the fine-tuned LLM and the dataset.

### Prerequisites

* **Python 3.8+** installed on your system.

* **pip** (Python package installer).

* **Git** for cloning the repository.

* **Node.js & npm** (optional, for Live Server extension in VS Code).

### Step 1: Clone the Repository

Open your terminal or command prompt and run:

```bash
git clone [https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git](https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git)
cd FlavorFinder_ML

```

Replace `YOUR_USERNAME` and `YOUR_REPO_NAME` with your actual GitHub username and repository name.

### Step 2: Acquire Model and Dataset

You **must** place your fine-tuned LLM and `swiggy.csv` dataset in the correct locations for the application to function.

1.  **Fine-tuned LLM:**

    * Ensure you have your `fine_tuned_model_swiggy_colab` directory (which contains files like `pytorch_model.bin`, `tokenizer.json`, etc.) from your fine-tuning process.

    * Place this entire directory directly inside the `backend/` folder:

        ```
        FlavorFinder_ML/
        └── backend/
            ├── fine_tuned_model_swiggy_colab/  <-- Place your model folder here
            │   ├── pytorch_model.bin
            │   ├── tokenizer.json
            │   └── ...other model files...
            └── app.py
            └── ...
        
        ```

    * *If you do not have this model, the backend will fail to load and run.*

2.  **`swiggy.csv` Dataset:**

    * Acquire the `swiggy.csv` dataset you used for fine-tuning.

    * Place this file directly in the root of your `FlavorFinder_ML` directory:

        ```
        FlavorFinder_ML/
        ├── swiggy.csv  <-- Place your dataset file here
        ├── backend/
        └── frontend/
        
        ```

    * *The backend may use this for context, and the evaluation script might indirectly rely on its presence for certain aspects if the model was trained on it.*

### Step 3: Backend Setup (Flask & LLM)

1.  **Create a Python Virtual Environment:**

    ```bash
    python -m venv venv
    
    ```

2.  **Activate the Virtual Environment:**

    * **On Windows:**

        ```bash
        .\venv\Scripts\activate
        
        ```

    * **On macOS/Linux:**

        ```bash
        source venv/bin/activate
        
        ```

3.  **Install Backend Dependencies:**
    Navigate into the `backend` directory and install the required Python packages.

    ```bash
    cd backend
    pip install -r requirements.txt
    
    ```

    (If `requirements.txt` is missing, you'll need to create it manually based on `app.py`'s imports, e.g., `pip install flask transformers torch flask-cors requests matplotlib numpy`).

4.  **Run the Flask Backend Server:**
    From inside the `backend` directory, start the Flask application.

    ```bash
    python app.py
    
    ```

    The server should start on `http://127.0.0.1:5000`. Keep this terminal running.

### Step 4: Frontend Setup (Web UI)

1.  **Navigate to the `frontend` directory:**

    ```bash
    cd ../frontend
    
    ```

2.  **Open `index.html`:**
    You can simply open the `index.html` file in your web browser (e.g., `file:///C:/Users/YourUser/FlavorFinder_ML/frontend/index.html`).

    **Recommended (for live reloading and proper context):** Use a local web server. If you have VS Code, the "Live Server" extension is highly recommended.

    * Install "Live Server" extension by Ritwick Dey in VS Code.

    * Right-click on `index.html` in the VS Code file explorer.

    * Select "Open with Live Server".
        This will typically open the frontend at `http://127.0.0.1:5500/index.html` (or a similar port).

## 🚀 Using the Application

1.  **Start at the Login Page:**
    The application will first present a login/signup page with a two-panel design. Create a username and password (this is for local simulation only, no actual authentication backend).

2.  **Navigate Preferences:**
    After logging in, you'll transition to the main interface where you can select your cuisine preferences, atmosphere, set a budget range using a slider, and choose a minimum rating using interactive stars.

3.  **Provide Location:**
    Enter a city/neighborhood or click "Get My Current Location" (requires browser permission) to provide location context for recommendations.

4.  **Get Recommendations:**
    Click "Get Recommendations!" to send your preferences to the Flask backend. The LLM will then generate personalized restaurant suggestions.

5.  **View Restaurant Details:**
    Click on any recommendation card to view a detailed page with mock information (address, hours, phone, links) and action buttons.

6.  **Book a Table (Simulated):**
    On the restaurant detail page, click "Book Now" to open a modal for selecting a date, time, and number of guests. Confirming will show a simulated booking message.

## 📊 Model Evaluation

The `evaluate_model.py` script helps assess the model's adherence to the output format and provides some basic visualizations.

1.  **Ensure the Flask backend (`app.py`) is running.**

2.  **Open a new terminal** and navigate to `FlavorFinder_ML/backend`.

3.  **Activate your virtual environment.**

4.  **Run the evaluation script:**

    ```bash
    python evaluate_model.py
    
    ```

5.  This script will print detailed output to the console and generate `field_completeness.png` and `rating_distribution.png` in the `backend` directory, showing how well the model populated expected fields and the distribution of generated ratings.

## 🎨 UI Design Philosophy

The user interface follows a modern, minimalist design aesthetic, primarily utilizing a sophisticated palette of deep blues, various greys, and crisp whites. A subtle gold accent is used sparingly to draw attention to key interactive elements and provide a touch of elegance. The design emphasizes clean lines, clear typography, and an intuitive flow to enhance the user experience.

## 🤝 Contributing

Contributions are welcome! If you have suggestions or find issues, please feel free to open an issue or submit a pull request.

## 📝 License

This project is open-source and available under the [MIT License](LICENSE).
(Note: You might need to create a `LICENSE` file in your root directory if you want to include a formal license.)
Minimum Rating Selection: Specify a minimum average rating for recommendations using interactive stars.

Location-Based Search: Input a city/neighborhood or use your browser's geolocation to find restaurants nearby.

Elegant UI/UX: A clean, minimalist design with a blue, grey, and white color palette inspired by modern forms, ensuring a delightful user experience.

Two-Panel Login: A unique two-column layout for the login/signup page, transitioning to a single-card design for all other interactions.

Detailed Restaurant View: Click on any recommendation to see a comprehensive detail page with mock information (address, hours, phone, links).

Simulated Booking: A modal for simulating table bookings, allowing date, time, and guest selection.

Model Evaluation Script: A utility script (evaluate_model.py) to programmatically test the model's output structure and qualitative aspects.

🛠️ Technologies Used
Backend:

Python: Core programming language.

Flask: Web framework for the REST API.

Hugging Face Transformers: For loading and running the fine-tuned LLM.

PyTorch: Deep learning framework (used by Transformers).

Flask-CORS: For handling Cross-Origin Resource Sharing.

Requests: For the evaluation script to call the Flask API.

Matplotlib, NumPy: For basic model evaluation visualizations.

Frontend:

HTML5: Structure of the web pages.

CSS3: Styling, with custom CSS for the minimalist design.

Tailwind CSS (CDN): Utility-first CSS framework for rapid UI development.

JavaScript (Vanilla JS): For all interactive elements, dynamic content, and API calls.

Font Awesome (CDN): For icons across the UI.

📁 Project Structure
FlavorFinder_ML/
├── backend/
│   ├── app.py                  # Flask API for restaurant recommendations
│   ├── evaluate_model.py       # Script to test and visualize model output accuracy
│   ├── requirements.txt        # Python dependencies for the backend
│   └── (fine_tuned_model_swiggy_colab/) # Placeholder: Model files are NOT included in Git repo
├── frontend/
│   └── index.html              # Frontend web application (HTML, CSS, JS)
├── swiggy.csv                  # Placeholder: Dataset is NOT included in Git repo
└── README.md                   # This file

Note on Model and Dataset:
Due to their large file sizes, the fine_tuned_model_swiggy_colab/ directory (containing the LLM weights) and the swiggy.csv dataset are NOT included in this GitHub repository. This is standard practice for large machine learning assets.

🚀 Local Setup and Running the Application
To run this project locally, you will need to manually provide the fine-tuned LLM and the dataset.

Prerequisites
Python 3.8+ installed on your system.

pip (Python package installer).

Git for cloning the repository.

Node.js & npm (optional, for Live Server extension in VS Code).

Step 1: Clone the Repository
Open your terminal or command prompt and run:

git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd FlavorFinder_ML

Replace YOUR_USERNAME and YOUR_REPO_NAME with your actual GitHub username and repository name.

Step 2: Acquire Model and Dataset
You must place your fine-tuned LLM and swiggy.csv dataset in the correct locations for the application to function.

Fine-tuned LLM:

Ensure you have your fine_tuned_model_swiggy_colab directory (which contains files like pytorch_model.bin, tokenizer.json, etc.) from your fine-tuning process.

Place this entire directory directly inside the backend/ folder:

FlavorFinder_ML/
└── backend/
    ├── fine_tuned_model_swiggy_colab/  <-- Place your model folder here
    │   ├── pytorch_model.bin
    │   ├── tokenizer.json
    │   └── ...other model files...
    └── app.py
    └── ...

If you do not have this model, the backend will fail to load and run.

swiggy.csv Dataset:

Acquire the swiggy.csv dataset you used for fine-tuning.

Place this file directly in the root of your FlavorFinder_ML directory:

FlavorFinder_ML/
├── swiggy.csv  <-- Place your dataset file here
├── backend/
└── frontend/

The backend may use this for context, and the evaluation script might indirectly rely on its presence for certain aspects if the model was trained on it.

Step 3: Backend Setup (Flask & LLM)
Create a Python Virtual Environment:

python -m venv venv

Activate the Virtual Environment:

On Windows:

.\venv\Scripts\activate

On macOS/Linux:

source venv/bin/activate

Install Backend Dependencies:
Navigate into the backend directory and install the required Python packages.

cd backend
pip install -r requirements.txt

(If requirements.txt is missing, you'll need to create it manually based on app.py's imports, e.g., pip install flask transformers torch flask-cors requests matplotlib numpy).

Run the Flask Backend Server:
From inside the backend directory, start the Flask application.

python app.py

The server should start on http://127.0.0.1:5000. Keep this terminal running.

Step 4: Frontend Setup (Web UI)
Navigate to the frontend directory:

cd ../frontend

Open index.html:
You can simply open the index.html file in your web browser (e.g., file:///C:/Users/YourUser/FlavorFinder_ML/frontend/index.html).

Recommended (for live reloading and proper context): Use a local web server. If you have VS Code, the "Live Server" extension is highly recommended.

Install "Live Server" extension by Ritwick Dey in VS Code.

Right-click on index.html in the VS Code file explorer.

Select "Open with Live Server".
This will typically open the frontend at http://127.0.0.1:5500/index.html (or a similar port).

🚀 Using the Application
Start at the Login Page:
The application will first present a login/signup page with a two-panel design. Create a username and password (this is for local simulation only, no actual authentication backend).

Navigate Preferences:
After logging in, you'll transition to the main interface where you can select your cuisine preferences, atmosphere, set a budget range using a slider, and choose a minimum rating using interactive stars.

Provide Location:
Enter a city/neighborhood or click "Get My Current Location" (requires browser permission) to provide location context for recommendations.

Get Recommendations:
Click "Get Recommendations!" to send your preferences to the Flask backend. The LLM will then generate personalized restaurant suggestions.

View Restaurant Details:
Click on any recommendation card to view a detailed page with mock information (address, hours, phone, links) and action buttons.

Book a Table (Simulated):
On the restaurant detail page, click "Book Now" to open a modal for selecting a date, time, and number of guests. Confirming will show a simulated booking message.

📊 Model Evaluation
The evaluate_model.py script helps assess the model's adherence to the output format and provides some basic visualizations.

Ensure the Flask backend (app.py) is running.

Open a new terminal and navigate to FlavorFinder_ML/backend.

Activate your virtual environment.

Run the evaluation script:

python evaluate_model.py

This script will print detailed output to the console and generate field_completeness.png and rating_distribution.png in the backend directory, showing how well the model populated expected fields and the distribution of generated ratings.

🎨 UI Design Philosophy
The user interface follows a modern, minimalist design aesthetic, primarily utilizing a sophisticated palette of deep blues, various greys, and crisp whites. A subtle gold accent is used sparingly to draw attention to key interactive elements and provide a touch of elegance. The design emphasizes clean lines, clear typography, and an intuitive flow to enhance the user experience.

🤝 Contributing
Contributions are welcome! If you have suggestions or find issues, please feel free to open an issue or submit a pull request.

📝 License
This project is open-source and available under the MIT License.
(Note: You might need to create a LICENSE file in your root directory if you want to include a formal license.)
