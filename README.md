# Traffic Disaster Resilience Simulation
**Stress‑Testing Bangladesh’s Transport Network with Agent‑Based Simulation for Disaster Readiness**

This repository provides an end‑to‑end workflow to evaluate **transport network resilience** under **disaster scenarios** using an **agent‑based model (ABM)** coupled with network analytics. It simulates how disruptions (e.g., flooding, blocked links, capacity loss) ripple through origin‑destination demand, route choice, and system performance, producing **KPIs for readiness and recovery**.

> Goal: give decision‑makers a transparent, scenario‑driven tool to test vulnerabilities, compare mitigation options, and communicate trade‑offs.

---

## ✨ Key Features
- **Agent‑Based Simulation** of travelers/vehicles reacting to disrupted networks.
- **Hazard Scenarios**: parameterize link/node failures, capacity degradation, or dynamic closures.
- **Network Analytics**: betweenness/criticality, disconnected demand, travel‑time inflation.
- **Policy Levers**: add hardening, re‑routing, staging, or prioritized lanes; measure effects.
- **Reproducible Runs**: configuration‑driven experiments; cached results and plots.
- **Clear Outputs**: CSVs and figures for KPIs and a compact run log.

---

## 📁 Project Structure
```
./Traffic_Disaster_Resilience_Simulation/
./__MACOSX/
Traffic_Disaster_Resilience_Simulation/.git/
Traffic_Disaster_Resilience_Simulation/graphs/
Traffic_Disaster_Resilience_Simulation/report/
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/
Traffic_Disaster_Resilience_Simulation/stage2_Base Model/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/
Traffic_Disaster_Resilience_Simulation/stage4_Network Simulation/
Traffic_Disaster_Resilience_Simulation/.DS_Store
Traffic_Disaster_Resilience_Simulation/Project Executive Summary.docx
Traffic_Disaster_Resilience_Simulation/README.md
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/img/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/.DS_Store
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/requirements.txt
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/img/Between.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/img/coincidence.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/img/delay_time.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/img/driving_time.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/img/location.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/img/scenarios_one_eight.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/.ipynb_checkpoints/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/ContinuousSpace/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/__pycache__/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/.DS_Store
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/README.md
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/batch_run.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/components.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/model.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/model_run.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/model_viz.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/ContinuousSpace/__pycache__/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/ContinuousSpace/SimpleContinuousModule.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/ContinuousSpace/simple_continuous_canvas.js
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/ContinuousSpace/__pycache__/SimpleContinuousModule.cpython-312.pyc
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/ContinuousSpace/__pycache__/SimpleContinuousModule.cpython-39.pyc
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/__pycache__/components.cpython-312.pyc
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/__pycache__/components.cpython-39.pyc
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/__pycache__/model.cpython-312.pyc
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/__pycache__/model.cpython-39.pyc
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/.ipynb_checkpoints/README-checkpoint.md
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/.ipynb_checkpoints/components-checkpoint.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/.ipynb_checkpoints/model-checkpoint.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/model/.ipynb_checkpoints/model_run-checkpoint.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/.ipynb_checkpoints/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/.DS_Store
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/Analysis_Assignment3.ipynb
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/Between.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/Model_run.ipynb
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/NetworkAnalysis.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/ShapefileProcessing.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/Subsection.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/analysis.ipynb
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/coincidence.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/delay_time.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/driving_time.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/location.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/preprocessing.ipynb
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/scenarios_one_eight.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/.ipynb_checkpoints/Analysis_Assignment3-checkpoint.ipynb
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/.ipynb_checkpoints/Bonus3-checkpoint.ipynb
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/.ipynb_checkpoints/BonusAssignment-checkpoint.ipynb
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/.ipynb_checkpoints/Data_Processing-checkpoint.ipynb
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/.ipynb_checkpoints/Model_run-checkpoint.ipynb
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/.ipynb_checkpoints/NetworkAnalysis-checkpoint.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/.ipynb_checkpoints/ShapefileProcessing-checkpoint.py
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/.ipynb_checkpoints/Subsection-checkpoint.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/.ipynb_checkpoints/coincidence-checkpoint.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/notebook/.ipynb_checkpoints/location-checkpoint.png
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/experiment/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/output/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/processed/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/raw/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/.DS_Store
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/README.md
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/output/.ipynb_checkpoints/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/output/network_intersection_metrics.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/output/network_metrics.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/output/.ipynb_checkpoints/network_intersection_metrics-checkpoint.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/output/.ipynb_checkpoints/network_metrics-checkpoint.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/experiment/.ipynb_checkpoints/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/experiment/all_scenarios.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/experiment/scenario0.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/experiment/scenario1.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/experiment/scenario2.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/experiment/scenario3.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/experiment/scenario4.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/experiment/.ipynb_checkpoints/all_scenarios-checkpoint.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/processed/.ipynb_checkpoints/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/processed/N1_N2_plus_sideroads.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/processed/NetworkG.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/processed/NetworkG.edgelist
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/processed/points_shapefile_new.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/processed/.ipynb_checkpoints/N1_N2_plus_sideroads-checkpoint.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/processed/.ipynb_checkpoints/NetworkG-checkpoint.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/processed/.ipynb_checkpoints/NetworkG-checkpoint.edgelist
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/raw/.ipynb_checkpoints/
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/raw/BMMS_overview.xlsx
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/raw/_roads3.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/raw/demo-4.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/raw/roads.shp
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/raw/roads.shx
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/raw/.ipynb_checkpoints/_roads3-checkpoint.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/raw/.ipynb_checkpoints/demo-2-checkpoint.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/raw/.ipynb_checkpoints/demo-3-checkpoint.csv
Traffic_Disaster_Resilience_Simulation/stage3_NetworkModel/data/raw/.ipynb_checkpoints/demo-4-checkpoint.csv
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/data/
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/.DS_Store
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/Bridges.ipynb
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/CleanedData.xlsx
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/DataCleaning.ipynb
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/FillingRoads.ipynb
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/Roads_LRP.ipynb
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/TCV.ipynb
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/data/processed/
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/data/.DS_Store
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/data/BMMS_overview.xlsx
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/data/Bridges.xlsx
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/data/Roads_InfoAboutEachLRP.xlsx
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/data/_roads.tcv
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/data/processed/BMMS_overview.xlsx
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/data/processed/Roads_InfoAboutEachLRP.xlsx
Traffic_Disaster_Resilience_Simulation/stage1_DataQuality/data/processed/_roads.tcv
Traffic_Disaster_Resilience_Simulation/report/figures/
Traffic_Disaster_Resilience_Simulation/report/.DS_Store
Traffic_Disaster_Resilience_Simulation/report/EPA 1352-G17-A4-Report.pdf
Traffic_Disaster_Resilience_Simulation/report/EPA1352-G17-A2-Report.pdf
Traffic_Disaster_Resilience_Simulation/report/EPA1352-G17-A3-Report.pdf
Traffic_Disaster_Resilience_Simulation/report/EPA1352-G22-A1-Report.pdf
Traffic_Disaster_Resilience_Simulation/report/figures/Location_worst3.png
Traffic_Disaster_Resilience_Simulation/report/figures/delay_time.png
Traffic_Disaster_Resilience_Simulation/report/figures/delay_time_3bridges.png
Traffic_Disaster_Resilience_Simulation/report/figures/delay_time_of_worst_bridged.png
Traffic_Disaster_Resilience_Simulation/report/figures/driving_time.png
Traffic_Disaster_Resilience_Simulation/report/figures/scenarios_one_eight.png
Traffic_Disaster_Resilience_Simulation/graphs/EPA1352_Assignment_1___Data_Quality_v2/
Traffic_Disaster_Resilience_Simulation/graphs/EPA1352_Assignment_2___Component_Building_v2/
Traffic_Disaster_Resilience_Simulation/graphs/EPA1352_Assignment_3___Network_Model_Generation_v2/
Traffic_Disaster_Resilience_Simulation/graphs/EPA1352_Assignment_4___Network_Analysis_v3/
Traffic_Disaster_Resilience_Simulation/graphs/.DS_Store
Traffic_Disaster_Resilience_Simulation/graphs/EPA1352_Assignment_4___Network_Analysis_v3/page001.png
Traffic_Disaster_Resilience_Simulation/graphs/EPA1352_Assignment_4___Network_Analysis_v3/page002.png
Traffic_Disaster_Resilience_Simulation/graphs/EPA1352_Assignment_1___Data_Quality_v2/page001.png
Traffic_Disaster_Resilience_Simulation/graphs/EPA1352_Assignment_1___Data_Quality_v2/page002.png
Traffic_Disaster_Resilience_Simulation/graphs/EPA1352_Assignment_1___Data_Quality_v2/page003.png
Traffic_Disaster_Resilience_Simulation/graphs/EPA1352_Assignment_1___Data_Quality_v2/page003_img01.png
Traffic_Disaster_Resilience_Simulation/graphs/EPA1352_Assignment_1___Data_Quality_v2/page004.png
…
```

> Total files indexed: **5931**

Notable items:
- **Python modules & scripts**: Traffic_Disaster_Resilience_Simulation
- **Notebooks**: 14 detected
- **Data-related paths**: Traffic_Disaster_Resilience_Simulation
- **Configs/diagrams**: —

---

## 🚀 Getting Started

### 1) Create an environment
```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
source .venv/bin/activate
pip install --upgrade pip
```

### 2) Install dependencies
```text
argon2-cffi==20.1.0
async-generator==1.10
attrs==20.3.0
backcall==0.2.0
bleach==3.3.0
brotlipy==0.7.0
certifi==2020.12.5
cffi==1.14.4
chardet==4.0.0
colorama==0.4.4
cryptography==3.3.1
decorator==4.4.2
defusedxml==0.6.0
entrypoints==0.3
et-xmlfile==1.0.1
idna==2.10
importlib-metadata==2.0.0
ipykernel==5.3.4
ipython==7.20.0
ipython-genutils==0.2.0
jdcal==1.4.1
jedi==0.17.0
Jinja2==2.11.3
json5==0.9.5
jsonschema==3.2.0
jupyter-client==6.1.7
jupyter-core==4.7.1
jupyterlab==2.2.6
jupyterlab-pygments==0.1.2
jupyterlab-server==1.2.0
MarkupSafe==1.1.1
mistune==0.8.4
nbclient==0.5.1
nbconvert==6.0.7
nbformat==5.1.2
nest-asyncio==1.4.3
notebook==6.2.0
numpy==1.20.1
openpyxl==3.0.6
packaging==20.9
pandas==1.2.2
pandocfilters==1.4.3
parso==0.8.1
pickleshare==0.7.5
pip==20.3.3
prometheus-client==0.9.0
prompt-toolkit==3.0.8
pycparser==2.20
Pygments==2.7.4
pyOpenSSL==20.0.1
pyparsing==2.4.7
pyrsistent==0.17.3
PySocks==1.7.1
python-dateutil==2.8.1
pytz==2021.1
pywin32==227
pywinpty==0.5.7
pyzmq==20.0.0
requests==2.25.1
Send2Trash==1.5.0
setuptools==52.0.0.post20210125
six==1.15.0
tensorflow==2.12.0
terminado==0.9.2
testpath==0.4.4
tornado==6.1
traitlets==5.0.5
urllib3==1.26.3
wcwidth==0.2.5
webencodings==0.5.1
wheel==0.36.2
win-inet-pton==1.1.0
wincertstore==0.2
xlrd==2.0.1
zipp==3.4.0
```

> If GeoPandas is used, you may need OS packages for GEOS/PROJ. See GeoPandas docs for your platform.

### 3) Prepare data
Place required input files under the appropriate folders (see **Project Structure**). If sample data are included, you can run the defaults out‑of‑the‑box.

---

## 🧩 How It Works (Conceptual)

1. **Load network & demand** — Read a road/rail graph (edges with length, free‑flow speed/capacity) and OD demand (agents or flows).
2. **Apply disaster scenario** — Mark edges/nodes with failure states or capacity multipliers (0–100%). Optionally time‑varying.
3. **Simulate agent decisions** — Agents pick routes based on current network cost (e.g., travel time), re‑routing when links fail.
4. **Measure system KPIs** — Travel‑time inflation, unmet demand, detour ratios; criticality metrics; recovery profiles if the scenario evolves.
5. **Compare policies** — Re‑run with mitigation (hardening, traffic management), quantify benefits vs. baseline.

---

## ⚙️ Configuration
Adjust scenario and model parameters via config files or script constants. Typical controls include:
- **Hazard intensity & footprint**
- **Failure probability per link / capacity scalars**
- **OD demand scaling**
- **Agent routing logic & replanning frequency**
- **KPIs to compute and save**

---

## 🏃 Run the Simulation
```bash
python run_simulation.py  # or open notebooks under `notebooks/` and run top‑down
```

Outputs are typically written under `results/` or `outputs/`. Plots (PNG/SVG) go to `figures/` or `plots/`.

---

## 📊 Outputs
- `results/*.csv` — KPIs per scenario (e.g., mean travel time, % disconnected OD pairs, unmet demand).
- `results/critical_links.csv` — sorted list of links by criticality metric (if computed).
- `logs/run_*.txt` — reproducibility log (seed, config hash, git commit if available).
- `figures/*.png` — maps/plots of disruption and performance.

---

## 🧪 Reproducibility
- **Random seeds**: set via config or env var `SIM_SEED` for deterministic runs.
- **Config hashing**: include a run ID combining datetime + config hash in filenames.
- **Environment**: export `pip freeze > requirements-lock.txt` or use `environment.yml`.

---

## 🧱 Extending
- Plug in alternative routing (A*, Dijkstra, multi‑criteria).
- Add time‑dependent failures & staged recovery.
- Integrate empirical mobility traces or dynamic OD matrices.
- Compute additional metrics (reliability, accessibility to critical services, equity).

---

## 📎 Citation
If you use this repository, please cite it as:
```bibtex
@software{tdrs,
  title = {Traffic Disaster Resilience Simulation},
  author = {Your Name},
  year = {2025},
  url = {REPO_URL}
}
```

---

## 📜 License
Add a license (e.g., MIT, Apache-2.0) in `LICENSE`.

---

## 🙏 Acknowledgements
Thanks to open‑source libraries that made this project possible: **NumPy**, **Pandas**, **NetworkX**, **Mesa**, **Matplotlib**, **SciPy**, and geospatial libraries if used.
