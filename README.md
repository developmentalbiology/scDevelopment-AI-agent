# **scEmbryo: A Multitask Single-Cell RNA-seq Analysis Agent for Human Embryonic Development**

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

**scEmbryo** is an advanced multitask tool for single-cell RNA-seq analysis, specifically tailored for developmental biology research. It combines the power of traditional bioinformatics workflows with AI-driven automation through an integrated LLM (Large Language Model) agent, enabling seamless data processing, integration, and annotation for embryo-related datasets.

---

## **Features**

1. **Multitask Workflow**:
   - Perform multiple single-cell analysis tasks in one place.
   - Supported tasks include:
     - **Load Data**: Load `.h5ad` files or entire directories.
     - **Preprocess Data**: Normalize, log-transform, and preprocess datasets for downstream analysis.
     - **Data Integration**: Merge multiple datasets using batch correction techniques like scVI and scANVI.
     - **Automated Annotation**: Transfer labels and annotate cell types using reference models.
     - **Optimize Training Models**: Fine-tune parameters for machine learning models.
     - **Embryo Model Evaluation**: Evaluate and compare embryo-specific models systematically.

2. **LLM-Powered Automation**:
   - Built-in AI agent to guide users through tasks and handle complex input/output interactions.
   - Simplifies workflows by automating repetitive steps and providing intelligent suggestions.

3. **User-Friendly Interface**:
   - Command-line interface (CLI) for technical users.
   - Potential for web-based interfaces (e.g., Streamlit or Gradio) for non-technical users.

4. **Reproducibility**:
   - Includes a `requirements.txt` file for consistent environment setup.
   - Outputs are saved in a structured format for easy reuse in downstream analyses.

---

## **Installation**

### **Step 1: Clone the Repository**
```bash
git clone https://github.com/yourusername/scEmbryo.git
cd scEmbryo
```

### **Step 2: Set Up a Virtual Environment**
We recommend using Python 3.9 or higher. Create a virtual environment to manage dependencies:
```bash
conda create -n scembryo_env python=3.9
conda activate scembryo_env
```
**Using Pip:
```bash
python -m venv env
source env/bin/activate  # Linux/macOS
env\Scripts\activate     # Windows
```

### **Step 3:  Install Dependencies**
Install all required packages using the provided 'requirements.txt' file:
```bash
pip install -r requirements.txt
```

## **Usage**

### **Command-Line Interface**
Run the tool directly from the command line:
```bash
python user_interaction.py
```
The tool will interactively guide you through available tasks. Follow the prompts to load datasets, preprocess data, perform integration, or run annotations.

### **DeepSeek API key**
you will be asked to provide **DeepSeek API key**, Please visit the DeepSeek Platform to create API keys: https://platform.deepseek.com/api_keys

### **Input Files**
- **Single Dataset**: Provide a '.h5ad' file for individual tasks.
- **Multiple Datasets**: Provide a directory containing '.h5ad' files for integration tasks.
- **Batch Information**: Specify batch keys or use default settings ('orig.ident').

### **Output Directory**
All outputs will be saved in the './outputs' directory by default. You can specify a custom output directory during execution.


## **Supported Tasks**
### **1.Load Data**
Load '.h5ad' files into memory, check data structure and their compatibility for downstream tasks.
### **2.Preprocess Data**
Perform standard preprocessing steps:
- Normalization
- Log transformation
- Dimensionality reduction (PCA)
- Clustering (Leiden algorithm)
**Optional**: Adjust clustering resolution interactively.
### **3.Automated Annotation**
Annotate cells using our developmental reference models, query cells will be annotated on two levels using 'scPoli':
- Lineage annotation
- Cell type annotation
### **4.Data Integration**
Merge multiple datasets while correcting batch effects using:
- **scVI**: Latent space modeling for batch correction.
- **scANVI**: Semi-supervised integration for cell type annotations.
**scANVI** is the default method for performing data integration if you have completed 'Automated Annotation' in the previous step. The 'Lineage annotation' will be used to guide the integration, which typically yields better results compared to unsupervised methods. If you do not have harmonized labels available to guide the integration, **scVI** will be used instead to perform the data integration.
### **5.Optimize Training Models**
If the initial prediction is not optimal, it is highly likely that the current model has not been sufficiently trained on specific cell types in your query data. To enhance the model, verified correctly predicted cells can be selected, and the current model can be fine-tuned as part of a data iteration process to achieve higher prediction accuracy.
### **6.Stem-cell Model Evaluation**
By comparing to the in vivo cell reference atlas, the fidelity of different stem-cell models will be evaluated. We provide a series of evaluation metrics to support benchmarking.


## **Example Workflow**
### **Step1.Activate scEmbryo prompt**
```bash
python user_interaction.py
```
### **Step2.Choose tasks and follow instractions**
The agent will list avaliable tasks, reply with your answer and the agent will guide you.
The agent will ask you to provide file path, for windows user please be sure  changing "\" to "/" when you directly copied the path. 


## **Dependencies**
The tool requires the following Python packages (full list in 'requirements.txt'):
- scanpy
- numpy
- scipy
- pandas
- anndata
- scvi-tools
- matplotlib
- seaborn
- scArches


## **Citation**
If you use **scEmbryo** in your research, please cite it as follows:
```bibtex
@software{scEmbryo,
  author = {Xueying Fan},
  title  = {scEmbryo: A Multitask Single-Cell RNA-seq Analysis Agent for Human Embryonic Development},
  year   = {2025},
  url    = {https://github.com/developmentalbiology/scEmbryo}
}
```

## **Contact**
For questions or feedback, please contact:

- Xueying Fan: fanxueying@westlake.edu.cn or xueying.fan@outlook.com              
- GitHub Issues: https://github.com/developmentalbiology/scEmbryo/issues
