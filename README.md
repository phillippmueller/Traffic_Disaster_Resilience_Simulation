# Traffic Disaster Resilience Simulation
**Stress‑Testing Bangladesh’s Transport Network with Agent‑Based Simulation for Disaster Readiness**

This repository provides an end‑to‑end workflow to evaluate **transport network resilience** under **disaster scenarios** using an **agent‑based model (ABM)** coupled with network analytics. It simulates how disruptions (e.g., flooding, blocked links, capacity loss) ripple through origin‑destination demand, route choice, and system performance, producing **KPIs for readiness and recovery**.

> Goal: give decision‑makers a transparent, scenario‑driven tool to test vulnerabilities, compare mitigation options, and communicate trade‑offs.

---

## Executive Summary
This project builds a single, end-to-end, data-driven workflow to assess the resilience of Bangladesh’s transport network and to inform policy on where to reinforce, maintain, or monitor roads and bridges. We begin by diagnosing and repairing critical inconsistencies in the national road and bridge datasets (RMMS/BMMS)—notably coordinate errors, chainage/LRP mismatches, and misaligned bridge locations—then regenerate the canonical road and bridge files used by the modelling stack ( _roads.tcv, BMMS_Overview.xlsx). This establishes a trustworthy data foundation for all downstream analysis.  

On that foundation, we implement a modular agent-based simulation in MESA that represents sources/sinks, links, and bridges with failure-/maintenance-driven delays parameterized by bridge quality (A–D). Scenario experiments inject trucks every five minutes over a five-day horizon to quantify corridor travel-time impacts under escalating bridge-outage percentages, producing reproducible CSV outputs.      

We then scale from a single corridor to a connected network: N1, N2, and >25 km N-side roads are auto-generated, and NetworkX provides shortest-path routing between two-way SourceSink nodes; discovered paths are cached to accelerate replications. The same experiment design measures network-wide travel times under progressive degradation.      

Finally, we integrate RMMS traffic (AADT) with bridge location/quality to operationalize criticality (economic importance via truck volumes) and vulnerability (likelihood/impact of becoming impassable), producing ranked road/bridge hotspots and Python visualizations for decision support; analyses can rely on AADT alone or be coupled to simulation for N1/N2.      

---

## Key Features
- **Agent‑Based Simulation** of travelers/vehicles reacting to disrupted networks.
- **Hazard Scenarios**: parameterize link/node failures, capacity degradation, or dynamic closures.
- **Network Analytics**: betweenness/criticality, disconnected demand, travel‑time inflation.
- **Policy Levers**: add hardening, re‑routing, staging, or prioritized lanes; measure effects.
- **Reproducible Runs**: configuration‑driven experiments; cached results and plots.
- **Clear Outputs**: CSVs and figures for KPIs and a compact run log.

---

## Getting Started

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

---

## How It Works 

1. **Load network & demand** — Read a road/rail graph (edges with length, free‑flow speed/capacity) and OD demand (agents or flows).
2. **Apply disaster scenario** — Mark edges/nodes with failure states or capacity multipliers (0–100%). Optionally time‑varying.
3. **Simulate agent decisions** — Agents pick routes based on current network cost (e.g., travel time), re‑routing when links fail.
4. **Measure system KPIs** — Travel‑time inflation, unmet demand, detour ratios; criticality metrics; recovery profiles if the scenario evolves.
5. **Compare policies** — Re‑run with mitigation (hardening, traffic management), quantify benefits vs. baseline.

---

## 📊 Outputs
- `results/*.csv` — KPIs per scenario (e.g., mean travel time, % disconnected OD pairs, unmet demand).
- `results/critical_links.csv` — sorted list of links by criticality metric (if computed).
- `logs/run_*.txt` — reproducibility log (seed, config hash, git commit if available).
- `figures/*.png` — maps/plots of disruption and performance.
