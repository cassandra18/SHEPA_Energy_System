# ☀️ SHEPA Energy System

**Sustainable Hybrid Energy Project for Agriculture** — A solar-battery-hydrogen microgrid system designed to power cold storage, hydrogen production, water treatment, and borehole pumping in Merti, Isiolo County, Kenya.

> 🚧 **Status:** Active development — Phase 1 (Central Hub simulation) complete. Borehole models in progress.

---

## 📌 Project Overview

SHEPA is an off-grid hybrid renewable energy system designed to serve a central agricultural hub and five independent borehole pumping stations in a semi-arid region of northern Kenya. The system integrates:

- 🌞 **Solar PV** as the primary generation source
- 🔋 **Second-life Li-Ion battery storage** for overnight critical loads
- 💧 **Green hydrogen production** via an electrolyzer, supporting energy storage and agricultural applications
- ❄️ **Cold storage** for post-harvest produce (vegetables, dairy, meat)
- 🌧️ **Atmospheric Water Generation (AWG)** during rainy seasons
- 🚰 **Reverse osmosis water treatment** for electrolysis and site use
- 🔩 **Five independent solar-powered borehole systems** for groundwater extraction

---

## 🗂️ Repository Structure

```
shepa-energy-system/
│
├── docs/                          # Project documentation
│   ├── Shepa_System_Equipment_And_Energy_Summary.docx
│   ├── Shepa_HOMER_Pro_Data_Import_Reference.docx
│   ├── Shepa_HOMER_Pro_Design_Guide.docx
│   └── Shepa_HOMER_Results_Report.docx
│
├── homer/                         # HOMER Pro model files
│   ├── SHEPA_CentralHub_v1.homer
│   ├── SHEPA_CentralHub_v2.homer  (in progress)
│   └── SHEPA_Borehole_01.homer    (in progress)
│
├── presentations/                 # Presentation decks
│   └── Shepa_HOMER_Results_Presentation.pptx
│
├── data/                          # Load profiles and input data
│   ├── load_profiles/
│   └── solar_resource/
│
├── results/                       # Simulation outputs and screenshots
│   └── v1_simulation/
│
└── README.md
```

---

## ⚡ System Architecture

### Central Hub

| Component | Specification | Role |
|---|---|---|
| Solar PV | 200 kW (flat plate) | Primary generation |
| Li-Ion Battery | 100 kWh · 3 strings | Overnight storage |
| Bidirectional Converter | 50 kW | AC/DC coupling |
| Electrolyzer | 30 kW | Green H₂ production |
| Hydrogen Tank | 20 kg | H₂ storage |
| Diesel Generator | 50 kW | Backup / reliability |

**Dispatch Strategy:** HOMER Cycle Charging  
**Design Life:** 25 years  
**Location:** Merti, Isiolo County, Kenya · `1°4.0'N, 38°40.0'E`

### Borehole Systems (× 5)

Each borehole is modelled as an independent solar-direct pumping system:

| Component | Specification |
|---|---|
| Submersible Pump | 5 kW |
| Pump Controller (VFD) | 0.2 kW |
| Monitoring Sensors | 0.05 kW |
| **Total per borehole** | **~27 kWh/day** |

---

## 📊 Key Design Parameters

| Parameter | Value |
|---|---|
| Solar Peak Hours (PSH) | 5.5 hrs/day |
| Battery Round-Trip Efficiency | 85% |
| Inverter Efficiency | 95% |
| H₂ Production Target | ~5 kg/day |
| Total Daily Head (TDH) | ~100 m |
| Night Storage Requirement | ~180–200 kWh |
| Grand Total System Energy | ~685–735 kWh/day |

---

## 📈 Simulation Results — v1 (Central Hub)

> **Model file:** `SHEPA_CentralHub_v1.homer` · **Tool:** HOMER Pro 3.14.2

| Metric | Value |
|---|---|
| Total Net Present Cost (NPC) | $760,330 |
| Levelised Cost of Energy (LCOE) | $0.4424 / kWh |
| Annual Operating Cost | $23,297 / year |
| Total Capital Cost | $424,000 |
| Renewable Fraction | To be confirmed (v2) |

### ⚠️ Known Issues (v1 → v2 fixes in progress)

- [ ] PV search space was too narrow (capped at 200 kW) — expanding to 100–500 kW
- [ ] Converter search space insufficient (50 kW cap) — expanding to 50–150 kW
- [ ] Gen50 fuel curve incomplete — updating efficiency curve
- [ ] Electrolyzer dispatch intermittent — revising to controlled dispatch strategy

---

## 🗺️ Roadmap

### ✅ Completed
- [x] System equipment and energy summary
- [x] HOMER Pro data import reference document
- [x] HOMER Pro step-by-step design guide
- [x] Central Hub v1 simulation (SHEPA_CentralHub_v1.homer)
- [x] v1 results report and presentation

### 🔄 In Progress
- [ ] Central Hub v2 simulation (expanded search spaces + corrected parameters)
- [ ] Borehole system HOMER model (single reference model)
- [ ] Sensitivity analysis (solar resource, battery cost, diesel price)

### 📋 Planned
- [ ] Borehole models × 5 (duplicate and run)
- [ ] Seasonal validation (AWG against Merti rainfall calendar)
- [ ] Full system economic deep-dive and proposal documentation
- [ ] Stakeholder presentation — Phase 2

---

## 🛠️ Tools & Software

| Tool | Purpose |
|---|---|
| [HOMER Pro](https://www.homerenergy.com/) | Microgrid simulation and optimisation |
| Microsoft Word / Excel | Documentation and data management |
| Microsoft PowerPoint | Stakeholder presentations |
| GitHub | Version control and project visibility |

---

## 📁 Key Documents

| Document | Description |
|---|---|
| [System Equipment & Energy Summary](docs/) | Equipment list, load data, and design assumptions |
| [HOMER Pro Data Import Reference](docs/) | Load tables and parameters formatted for HOMER Pro input |
| [HOMER Pro Step-by-Step Design Guide](docs/) | 9-phase HOMER modelling workflow |
| [v1 Simulation Results Report](docs/) | Detailed analysis of first HOMER simulation |
| [v1 Results Presentation](presentations/) | Slide deck presented to project stakeholders |

---

## 👩‍💻 Author

**Cassandra Lelei**  
SHEPA Project — Merti, Isiolo County, Kenya

---

## 📄 License

This project is currently undeclared. Please contact the author before reproducing or building upon this work.

---

*Last updated: April 2026*
