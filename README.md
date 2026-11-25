# Acoustic Feature Clustering for Hands-Free Accessibility

An end-to-end machine learning project that explores acoustic similarities between spoken commands using audio feature extraction, unsupervised clustering, and interactive visualisation.

The project aims to identify voice commands that may sound similar and could potentially be confused in hands-free accessibility applications.

## Project Overview

Voice commands are often used to control devices without physical interaction. However, acoustically similar commands can create recognition challenges, especially in accessibility applications.

This project analyses speech recordings from the **Google Speech Commands Dataset** to:

- Extract meaningful acoustic features from audio recordings.
- Preprocess and standardise extracted features.
- Apply unsupervised clustering algorithms.
- Evaluate clustering performance using validation metrics.
- Use PCA to explore high-dimensional acoustic data.
- Identify potentially confusing voice-command pairs.
- Present findings through an interactive web application and generated reports.

## Key Features

- **Audio preprocessing:** Prepare speech recordings for feature extraction.
- **Acoustic feature extraction:** Convert audio signals into numerical representations.
- **Unsupervised clustering:** Group recordings based on acoustic similarities.
- **Model evaluation:** Compare clustering results using Silhouette Score and Davies–Bouldin Index.
- **PCA visualisation:** Explore patterns and relationships between acoustic features.
- **Interactive dashboard:** Explore clustering results and audio samples through a web interface.
- **Automated reports:** Generate HTML and PDF reports containing analysis and visualisations.

## Technology Stack

| Category | Technologies |
|---|---|
| Programming | Python |
| Data processing | NumPy, Pandas |
| Audio processing | Librosa, SoundFile |
| Machine learning | Scikit-learn, SciPy |
| Backend | FastAPI, Uvicorn |
| Frontend | HTML, CSS, JavaScript |
| Visualisation | Matplotlib, Plotly.js |
| Reporting | ReportLab, Jinja2 |

## Project Structure

```text
Speech-Clustering/
│
├── backend/
│   ├── analysis.py
│   ├── app.py
│   ├── clustering.py
│   ├── feature_extractor.py
│   ├── preprocessing.py
│   ├── report_generator.py
│   └── try_it.py
│
├── data/
│   ├── features.csv
│   ├── features_clean.csv
│   ├── clustering_metrics.csv
│   ├── feature_metadata.json
│   └── model and preprocessing artifacts
│
├── docs/
│   └── final_written_summary.md
│
├── frontend/
│   ├── index.html
│   ├── css/
│   └── js/
│
├── outputs/
│   ├── figures/
│   └── reports/
│
├── scripts/
├── run_pipeline.py
├── run_server.py
├── requirements.txt
├── pyproject.toml
└── README.md
```

## Dataset

The project uses the **Google Speech Commands Dataset**, with selected spoken-command categories.

The raw audio dataset is not included in this repository because of its size.

Download the dataset and place the required command folders inside a local `Dataset/` directory in the project root.

The expected structure is:

```text
Dataset/
├── yes/
├── no/
├── up/
├── down/
├── left/
├── right/
├── on/
├── off/
├── stop/
└── go/
```

Each folder should contain its corresponding WAV recordings.

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/lakshmi-kashyap/Speech-Clustering.git
cd Speech-Clustering
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

### 3. Activate the environment

**Windows PowerShell:**

```powershell
.venv\Scripts\Activate.ps1
```

**Windows Command Prompt:**

```cmd
.venv\Scripts\activate.bat
```

### 4. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 5. Add the dataset

Place the selected Google Speech Commands audio folders inside the `Dataset/` directory.

## Running the Project

### Option 1: Start the interactive web application

```bash
python run_server.py
```

Open the application in your browser:

```text
http://127.0.0.1:8000
```

### Option 2: Run the machine learning pipeline

```bash
python run_pipeline.py
```

Additional examples:

```bash
python run_pipeline.py --samples 200
python run_pipeline.py --seed 50
python run_pipeline.py --force
```

The pipeline supports audio loading, feature extraction, preprocessing, clustering, evaluation, dimensionality reduction, analysis, and report generation.

## Results and Visualisations

The repository includes generated analysis outputs, including:

- Feature correlation heatmap
- Clustering metrics comparison
- PCA scree plot
- PCA cluster visualisation
- PCA feature loadings
- Word-cluster heatmap
- Confusable-pair matrix
- Feature contribution analysis

Generated HTML and PDF reports are available in the `outputs/reports/` directory.

## Evaluation Metrics

The project uses the following metrics to evaluate clustering:

| Metric | Purpose |
|---|---|
| Silhouette Score | Measures how well-separated the clusters are |
| Davies–Bouldin Index | Measures similarity between clusters |
| Inertia / WCSS | Measures within-cluster variation |
| Adjusted Rand Index | Compares clustering assignments where reference labels are available |

Refer to the generated reports and `data/clustering_metrics.csv` for the experimental results.

## Project Objective

The broader goal is to understand acoustic similarities between spoken commands and explore how this information can help designers choose clearer and more distinguishable voice commands for hands-free accessibility systems.

## Collaboration

This project was developed collaboratively with **Ananya** as part of an academic project. The repository contains the project work and its associated documentation, implementation, and analysis.

## Future Improvements

- Explore additional acoustic feature representations.
- Experiment with alternative clustering approaches.
- Improve the identification of confusing command pairs.
- Expand the interactive audio-analysis experience.
- Investigate real-time voice-command evaluation.

## Author

**Lakshmi Kashyap**

GitHub: [lakshmi-kashyap](https://github.com/lakshmi-kashyap)

---

If you find this project interesting, feel free to explore the repository and its analysis outputs.
