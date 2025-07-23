# 🔋 Emissia

> **ACM 2025 Publication**  
> _Emissia: Modeling Carbon Footprint of Software from Static Complexity and Resource Models_  
> 📄 [ACM Publication Link – Coming Soon]

---

## ✨ Overview

**Emissia** is a static environmental modeling tool that estimates the **energy consumption** and **carbon footprint** of JavaScript/TypeScript code. It consumes output from static complexity tools like [`complexia`](https://github.com/helabenkhalfallah/complexia) and maps execution cost to **kWh and CO₂ emissions** based on regional and hardware benchmarks.

The system models:

- **Energy Use**: Estimates watt-hours (Wh) from instruction count, runtime, and memory allocation.
- **Carbon Emissions**: Computes CO₂e using electricity carbon intensity (gCO₂/kWh).
- **Regional Impact**: Allows estimation per country or cloud provider region.
- **Sustainable Insights**: Enables CI/CD checks, emission diffs, and eco-aware decisions during development.

---

## 📥 Installation

```bash
npm install -D emissia
```

### Prerequisites

- Node.js ≥ 18.x
- Output JSON file from `complexia`

---

## 🚦 CLI Usage

Run the tool with:

```bash
npx emissia estimate   --input "./reports/ComplexityOverview.json"   --region "France"   --outputDir "./emissions"
```

### Parameters:
- `--input`: Input JSON file from Complexia
- `--region`: Geographic location (e.g., `"France"`, `"us-west-2"`)
- `--outputDir`: Where to store emission estimates

---

## 🔬 Reproducing Evaluation Results

To replicate the emission modeling experiments:

```bash
git clone https://github.com/helabenkhalfallah/emissia.git
cd emissia
npm install
npm run estimate -- --input "./mock-data/ComplexityOverview.json" --region "Germany" --outputDir "./output"
```

### Output:

📂 `output/`  
- `EmissionEstimate.json`: Power use, CO₂ per module/function  
- `EmissionEstimate.html`: Dashboard view of hotspots  
- `RegionProfile.json`: Regional energy intensity (gCO₂/kWh) source

> **Note**: The included mock data approximates output from `complexia`. Real input should reflect actual time/memory cost estimates from AST-based analysis.

---

## 📦 Repository Structure

- `src/` – Carbon model, energy equations, region data
- `cli/` – Emissia command-line tool
- `mock-data/` – Sample complexity input for testing
- `output/` – Emission reports in HTML/JSON

---

## 📚 Citation

```bibtex
@inproceedings{benkhalfallah2025emissia,
  author    = {Héla Ben Khalfallah},
  title     = {Emissia: Modeling Carbon Footprint of Software from Static Complexity and Resource Models},
  booktitle = {Proceedings of the ACM Conference on Sustainable Computing (ACM e-Energy)},
  year      = {2025},
  note      = {To appear},
}
```

---

## 🧠 Use Cases

- Carbon-aware development in CI/CD pipelines
- Estimating cloud function emissions before deployment
- Refactoring decisions informed by energy/environmental cost
- Agentic systems with sustainability awareness

---

## 🤝 Contributing

```bash
git clone https://github.com/helabenkhalfallah/emissia.git
cd emissia
npm install
```

Run:

```bash
npm run estimate -- --input "./mock-data/ComplexityOverview.json" --region "Germany" --outputDir "./output"
```

---

## 📜 License

Licensed under the MIT License. See the [LICENSE](./LICENSE) file.
