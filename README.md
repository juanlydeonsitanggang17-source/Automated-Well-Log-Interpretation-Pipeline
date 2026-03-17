# Automated-Well-Log-Interpretation-Pipeline
end-to-end Machine Learning pipeline capable of interpreting complex multi-facies lithologies directly from raw well log data.
# 🌍 Automated Petrophysical Well Log Interpretation using Deep Learning (BiLSTM)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![Plotly](https://img.shields.io/badge/Plotly-WebGL-brightgreen)
![Geoscience](https://img.shields.io/badge/Domain-Petrophysics-lightgrey)

An end-to-end Machine Learning pipeline designed to automatically interpret complex, multi-facies lithologies directly from raw well log data (`.las`). This project bridges traditional geophysics with modern artificial intelligence, handling the messy realities of field data while applying state-of-the-art sequential Deep Learning.

## 🚀 Key Features

1. **Physics-Constrained Data Engineering:** Includes a custom synthetic well log generator that simulates over 78,000 depth steps (~12,000 meters). It incorporates **Athy's Law of Compaction** for depth-dependent density shifts and generates 6 distinct facies (Sandstone, Shale, Shaly Sand, Limestone, Dolomite, Coal).
2. **Sequential Deep Learning (BiLSTM):** Utilizes a Bidirectional Long Short-Term Memory (BiLSTM) network with Sequence Windowing. Instead of treating each depth point independently, the model learns the spatial and vertical geological context, achieving high accuracy even on imbalanced minority classes.
3. **Automated LAS File Parsing:** A robust deployment script that automatically scans local directories for raw `.las` files, cleans the data, and applies dynamic alias-mapping (e.g., automatically recognizing Schlumberger's `RLA5` as True Resistivity `RT`).
4. **GPU-Accelerated Web Visualization:** Integrates **Plotly WebGL** to render highly interactive, GPU-accelerated dashboards capable of displaying tens of thousands of data points smoothly.

## 📁 Repository Structure

* `1_data_generator.py`: Generates the massive synthetic dataset (`MultiFacies_Petrofisika.xlsx`) based on petrophysical equations.
* `2_model_training.py`: Preprocesses the data, builds the BiLSTM architecture, trains the model, evaluates metrics (F1-Score, Confusion Matrix), and exports the trained model (`.h5`) and preprocessing tools (`.pkl`).
* `3_deploy_las.py`: The production script. Automatically detects `.las` files, loads the trained AI, predicts the facies, and launches an interactive web dashboard.

## 🛠️ Installation & Requirements

Ensure you have Python 3.8+ installed. Clone this repository and install the required dependencies:

```bash
git clone https://github.com/juanlydeonsitanggang17-source/Automated-Well-Log-Interpretation-Pipeline/edit/main/README.md)
pip install tensorflow pandas numpy matplotlib seaborn scikit-learn lasio plotly joblib openpyxl
