# Selected Projects

A concise collection of outcome-oriented work showing how I apply data science, ML, and scientific computing to real-world problems.

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

## PhotoSorter: Image Grouping for Product Photography
**Stack:** OpenCV, scikit-learn, Pandas  
**Summary:** Built a hybrid visual + temporal clustering system to group ceramic product photos (macro and full-pot shots). Outputs a CSV mapping of image-to-group relationships, reducing manual curation time by 70%.  
**Links:** [Code](https://github.com/hghodkephd/photo-sorter) · [Notebook](https://nbviewer.org/github/hghodkephd/photo-sorter/blob/main/notebooks/01_grouping.ipynb)

---

## Protein Stability Toolkit: Kinetics & Design A/B Tests
**Stack:** NumPy, SciPy, Altair  
**Summary:** Created a lightweight analysis toolkit for kinetic fitting, thermal stability modeling, and ranking of protein variants with uncertainty estimates. Designed for high-throughput screening workflows in enzyme engineering.  
**Links:** [Code](https://github.com/hghodkephd/protein-stability-toolkit) · [Notebook](https://nbviewer.org/github/hghodkephd/protein-stability-toolkit/blob/main/examples/stability_demo.ipynb)

---

## Firebox Studio Simulator
**Stack:** Python, Pandas, Streamlit, Monte Carlo Simulation  
**Summary:** Modeled studio membership and event economics for a 5-year planning horizon. Simulates multiple revenue streams and visualizes confidence intervals for break-even and cash-flow stability.  
**Links:** [Code](https://github.com/hghodkephd/firebox-financial-model)

---

## Single-Molecule DNA Repair Data Analysis
**Stack:** Python, NumPy, SciPy, custom image analysis pipelines  
**Summary:** Built quantitative tools for single-molecule trajectory analysis, kinetic modeling, and statistical fitting of DNA-protein interactions. Extracts kinetic constants (kon, koff, KD) from time-series fluorescence data.  
**Links:** [Code](https://github.com/hghodkephd/smDNArepair) · [Publication](https://www.nature.com/articles/s41467-020-15822-9)
