# Selected Projects

A collection of computational, analytical, and mechanistic modeling projects spanning scientific computing, process simulation, experimental infrastructure, and quantitative data analysis. These projects focus on building practical systems and modeling frameworks that connect experimental observables to real-world operational decision-making.

---
## Themes

Across these projects, common themes include mechanistic modeling, operational systems design, scientific computing, workflow automation, and quantitative decision-making under real-world experimental and infrastructure constraints.

---

## De Novo Mini Binder Design Against PD-L1

**Stack:** RFdiffusion, ProteinMPNN, ESMFold, PyMOL, BioPython, Python, Google Colab

**Summary:** Built an end-to-end computational protein design workflow for de novo mini binders targeting the PD-1 binding surface of PD-L1. The project uses RFdiffusion for backbone generation, ProteinMPNN for sequence design, and ESMFold-based structural validation to rank candidate binders by fold confidence and design recapitulation. Includes interactive visualization, candidate filtering, entropy-guided library design logic, and discussion of experimental validation requirements.

**Links:** [De novo mini binder design](/hg-portfolio/projects/pdl1-mini-binder/Page1_denovo_minibinder_design) · [Parameter Sensitivity](/hg-portfolio/projects/pdl1-mini-binder/Page2_parameter_sensitivity) · [Interaction Fingerprinting](/hg-portfolio/blob/main/docs/projects/pdl1-mini-binder/Page3_interaction_fingerprinting/) · [Code](https://github.com/hghodkephd/pdl1-mini-binder-design)

---

## Mechanistic PETase Process Simulator

**Stack:** Python, NumPy, SciPy, ODE Modeling, Scientific Computing  

**Summary:** Developed a mechanistic simulation framework for enzymatic PET depolymerization under industrially relevant conditions, integrating heterogeneous surface catalysis, enzyme adsorption/inactivation dynamics, particle-size effects, crystallinity evolution, and pH-stat process observables into a unified reactor-scale ODE model. Designed as a hypothesis-generation and parameter-fitting scaffold to support experimental design and process reasoning in enzymatic plastic biorecycling workflows. Explores how competing mechanisms — including surface accessibility, thermal enzyme decay, and substrate recrystallization — shape conversion dynamics and process performance.

**Links:** [Code](#) · [Technical Documentation](#)

---

## Govee-monitor
**Stack:** Python, Bleak (BLE), SQLite, Pandas, Streamlit, Altair, psutil  
**Summary:** Engineered a production-grade environmental monitoring platform that turns low-cost Govee H5075 Bluetooth sensors into a 24/7 self-healing data collection service, suitable for home, lab, or greenhouse use.  A multi-page Streamlit dashboard orchestrates a dedicated BLE scanner process and watchdog thread that detect silent Bluetooth failures, automatically restart the service, and stream decoded readings into a time-series SQLite store (WAL mode) with configurable, gzip-compressed archiving to bound database growth.  Users can discover and name sensors, configure per-sensor temperature, battery, and offline alerts, and explore live and historical conditions via Altair-based charts that support multi-sensor comparison and overlay external Open-Meteo weather data for context.  Designed for lightweight deployment on devices like Raspberry Pi or a home NAS, the system cleanly separates UI, process management, BLE decoding, and storage, showcasing full-stack data engineering and reliability-focused systems design.   
**Links:** [Demo](https://govee-monitor.streamlit.app/)

---

## Potteryverse: Studio Economics Analytics
**Stack:** Python, Pandas, Streamlit  
**Summary:** Developed a complete analytics workflow for modeling revenue and membership growth in community ceramics studios. Implemented Monte Carlo simulations to estimate break-even points, churn effects, and confidence bands for studio financial self-sufficiency.  
**Links:** [Demo](https://huggingface.co/spaces/potteryverse/potteryverse-survey)

---
## PhotoSorter: Image Grouping for Product Photography (coming soon)
**Stack:** OpenCV, scikit-learn, Pandas  
**Summary:** Built a hybrid visual + temporal clustering system to group ceramic product photos (macro and full-pot shots). Outputs a CSV mapping of image-to-group relationships, reducing manual curation time by 70%.  
**Links:** [Code](https://github.com/hghodkephd/photo-sorter) · [Notebook](https://nbviewer.org/github/hghodkephd/photo-sorter/blob/main/notebooks/01_grouping.ipynb)

---
## Protein Stability Toolkit: Kinetics & Variant Analysis (coming soon)
**Stack:** NumPy, SciPy, Altair  
**Summary:** Developed a lightweight computational toolkit for analyzing enzyme kinetics, thermal stability, and variant performance across high-throughput protein engineering campaigns. Includes nonlinear kinetic fitting, thermal denaturation modeling, uncertainty estimation, and comparative ranking workflows designed for rapid interpretation of screening and characterization datasets.
**Links:** [Code](https://github.com/hghodkephd/protein-stability-toolkit) · [Notebook](https://nbviewer.org/github/hghodkephd/protein-stability-toolkit/blob/main/examples/stability_demo.ipynb)

---

## Membership-based Ceramics Studio Finances Simulator (coming soon)
**Stack:** Python, Pandas, Streamlit, Monte Carlo Simulation  
**Summary:** Modeled studio membership and event economics for a 5-year planning horizon. Simulates multiple revenue streams and visualizes confidence intervals for break-even and cash-flow stability.  
**Links:** [Code](https://github.com/hghodkephd/firebox-financial-model)

---

## Single-Molecule DNA Repair Data Analysis
**Stack:** Python, NumPy, SciPy, custom image analysis pipelines  
**Summary:** Built quantitative tools for single-molecule trajectory analysis, kinetic modeling, and statistical fitting of DNA-protein interactions. Extracts kinetic constants (kon, koff, KD) from time-series fluorescence data.  
**Links:** [Code](https://github.com/hghodkephd/smDNArepair) · [Publication](https://www.nature.com/articles/s41467-020-15822-9)
