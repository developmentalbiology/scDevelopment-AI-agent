# **scDevelopment Agent: A Multitask Single-Cell RNA-seq Analysis Agent for Human Embryonic Development**

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

Welcome to **scDevelopment Agent** — an AI-powered, multitask analysis framework designed to streamline and standardize single-cell RNA-seq workflows in human embryonic development research.

Built on the LangChain framework and powered by large language models (LLM), scDevelopment integrates domain-specific knowledge, automated analytical tools, and real-time literature access to guide users through end-to-end single-cell data analysis — from raw `.h5ad` files to comprehensive, publication-ready reports.

## 🌟 Key Features

### 🔬 **Developmental Biology–Focused Analysis**
- Specialized for studying **human peri-implantation development, gastrulation, and early organogenesis**
- Leverages a curated internal knowledge base integrating single-cell transcriptomic datasets and developmental biology literatures from human embryos

### ⚙️ **Integrated Analysis Tools**
Each step of the analysis pipeline is wrapped into modular, reproducible tasks:
- `load_data`: Load `.h5ad` datasets with metadata inspection
- `preprocess_data`: Normalize and QC single-cell data
- `data_visualization`: Generate UMAPs, violin plots, and dot plots
- `label_transfer`: Annotate query datasets using reference atlases
- `cytotrace_analysis`: Infer developmental potential and trajectories
- `model_evaluation` & `lineage_evaluation`: Benchmark embryo models for fidelity, coverage, and consistency
- `data_integration`: Harmonize datasets using scVI/scANVI
- `add_columns`: Enrich metadata with custom annotations or scores

  ### 📚 **Literature-Integrated Interpretation**
- Real-time access to scientific literature via `google_scholar_search`
- Biological context generation with AI-enhanced summaries
- Automatic citation and reference validation for key markers and pathways

  ### 📄 **Automated Reporting**
- `generate_evaluation_report`: Create structured markdown summaries
- `generate_comprehensive_academic_report`: Produce **publication-ready reports** (in both Markdown and PDF) including:
  - Abstract, Methods, Results, Discussion
  - Literature-backed biological interpretation
  - Model performance evaluation
  - Protocol optimization recommendations
  - Full references and appendices

### 💻 **Flexible Execution Modes**
- **Conversational AI**: Natural language interaction for intuitive guidance
- **Point-and-click interface** (web app integration ready)
- **Code-backed transparency**: All analyses are executable via Python, with full auditability
  
---

## 🌐 Accessing the Web Application

The **scDevelopment Agent** is available as an interactive online platform, designed for intuitive, user-friendly single-cell RNA-seq analysis in developmental biology. To get started:

1. Access the hosted web application (URL available soon).
2. Upload your `.h5ad` single-cell dataset using the built-in file interface.
3. Navigate the sidebar to choose your preferred mode:
   - **Tools**: Use the **point-and-click interface** for guided, step-by-step analysis.
   - **Conversation**: Interact with the AI agent via natural language to perform flexible, conversational analysis.

The platform seamlessly integrates data processing, visualization, annotation, and reporting — empowering researchers to explore embryonic development models without requiring coding expertise.

---

## ⚠️ Important Usage Notes

- **Dataset Size Limit**: The online application supports dataset uploads of up to **5 GB**. 
  
- **Limited Support for Memory-Intensive Tasks**: Due to computational limitations, **data integration** (e.g., scVI/scANVI) and **Cytotrace developmental trajectory analysis** may not complete successfully for large or highly complex datasets in the web version.

- **Local Deployment Option**: For advanced use cases involving large-scale data, full pipeline execution, or custom workflows, please contact the team to obtain the standalone Python package for local use.

- **Ongoing Development**: The platform is under active development, with continuous improvements to the internal knowledge base, expanded analytical capabilities, and enhanced user experience. All updates, new features, and release notes will be regularly shared in this repository.


## **Contact**
For questions or feedback, please contact:

- Xueying Fan: fanxueying@westlake.edu.cn             
- GitHub Issues: https://github.com/developmentalbiology/scEmbryo/issues
