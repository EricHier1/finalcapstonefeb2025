---
title: Netflix Recommendation App
emoji: 🍿
colorFrom: red
colorTo: black
sdk: docker
sdk_version: "{{sdkVersion}}"
app_file: recommend_app.py
pinned: false
app_port: 7860
---
# Netflix Content-Based Recommender

A Flask-based web application that provides personalized recommendations for Netflix content using a content-based filtering approach.

## Features
- Content-based recommendations based on TF-IDF and cosine similarity
- Search and autocomplete functionality
- Visualizations of Netflix content distribution
- Works on both macOS and Windows

## Prerequisites
Ensure you have the following installed:
- **Python 3.12+** (Check with `python --version` or `python3 --version`)
- **Node.js and npm** (Check with `node -v` and `npm -v`)
- **pip** (Python package manager)

## Installation

### 1. Clone the Repository
```sh
git clone https://github.com/yourusername/flick_picker.git
cd flick_picker
```

### 2. Set Up a Virtual Environment

#### macOS & Linux
```sh
python3 -m venv venv
source venv/bin/activate
```

#### Windows (Command Prompt)
```sh
python -m venv venv
venv\Scripts\activate
```

#### Windows (PowerShell)
```powershell
python -m venv venv
venv\Scripts\Activate.ps1
```

### 3. Install Dependencies

```sh
pip install -r requirements.txt
npm install
```

### 4. Download Dataset
Ensure `netflix_titles.csv` is placed in the project root directory.

### 5. Build or Load Model
Run the following command to preprocess the dataset and generate a similarity model:

```sh
python recommend_app.py
```

This will load the Netflix dataset, process it, and save a cached similarity model (`cosine_sim_cache.pkl`).

## Running the Application

Once setup is complete, start the Flask server:

```sh
python recommend_app.py
```

The app will be available at:  
[http://127.0.0.1:5020](http://127.0.0.1:5020)

## Frontend Development
If making changes to the frontend, ensure Node.js dependencies are installed. Run:

```sh
npm run dev
```

## File Structure

```
flick_picker/
│── recommend_app.py          # Flask API entry point
│── recommendation_engine.py  # Content-based filtering logic
│── netflix_titles.csv        # Dataset file
│── requirements.txt          # Python dependencies
│── package.json              # Frontend dependencies
│── static/
│   ├── index.html            # Main frontend page
│   ├── js/                   # Frontend scripts
│   ├── styles.css            # Stylesheet
│── venv/                     # Python virtual environment
```

## Stopping the Server
To stop the Flask server, press **Ctrl + C** in the terminal.

To deactivate the virtual environment:

#### macOS & Linux
```sh
deactivate
```

#### Windows
```sh
venv\Scripts\deactivate
```
#### DOCKER Deployment (EASY MODE)

```sh
docker build -t my-recommend-app .
docker run -p 7860:7860 my-recommend-app
```

access app at http://0.0.0.0:7860