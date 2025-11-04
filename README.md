# Global CO₂ Emissions Analysis Dashboard

<div align="center">

**A comprehensive data visualization platform analyzing CO₂ emissions trends and their impact on socio-economic factors**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Tableau](https://img.shields.io/badge/Tableau-Dashboard-blue.svg)](https://www.tableau.com/)

</div>

## 📋 Table of Contents
- [Overview](#overview)
- [Key Features](#key-features)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Data Sources](#data-sources)
- [Research Questions](#research-questions)
- [Visualizations](#visualizations)
- [Key Findings](#key-findings)
- [Team](#team)
- [License](#license)
- [Contact](#contact)

## 🌍 Overview

Climate change is one of the most critical challenges of our era, and CO₂ emissions are the primary contributors to this global crisis. This project provides an interactive data visualization platform that combines **Jupyter Notebook analytics** and **Tableau dashboards** to explore global CO₂ emission trends, evaluate the influence of technological advancements, and examine the roles of specific countries and sectors in contributing to emissions.

### Motivation

With the global goal to limit warming to 1.5°C, reducing CO₂ emissions is crucial. This dashboard helps:
- 🔍 Identify major emission contributors by country and sector
- 📊 Analyze relationships between emissions and socio-economic factors
- 🌱 Evaluate renewable energy adoption trends
- 💡 Inform evidence-based policy recommendations

## ✨ Key Features

### Interactive Jupyter Notebook
- **Country-level Analysis**: Comprehensive emission trends by country from 1800-2022
- **Choropleth Maps**: Interactive geographical visualizations of per capita emissions
- **Animated Visualizations**: Time-series animations showing emission evolution
- **Sectoral Breakdown**: Detailed analysis of emissions by sector (Energy, Agriculture, Industrial, etc.)
- **Population Correlation**: Statistical analysis of population vs. emissions relationships
- **Income Group Analysis**: Emissions distribution across different income levels

### Tableau Dashboard
- **Regional Comparisons**: Side-by-side renewable energy capacity analysis
- **Time-Series Trends**: Renewable energy utilization over decades
- **Policy Impact Visualization**: Visual representation of renewable energy policies
- **Interactive Filters**: Dynamic filtering by country, region, and time period

### Advanced Analytics
- Historical trend analysis (1800-2022)
- Per capita emissions calculations
- Sectoral contribution analysis
- Renewable energy capacity tracking
- Policy recommendation framework

## 📦 Installation

### Prerequisites
- Python 3.7 or higher
- Jupyter Notebook or JupyterLab
- Tableau Desktop or Tableau Reader (for `.twb` files)

### Step 1: Clone the Repository
```bash
git clone https://github.com/DATS6401/Final-Project.git
cd Final-Project
```

### Step 2: Create Virtual Environment (Recommended)
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Required Python Packages
The project uses the following dependencies:
- `pandas` - Data manipulation and analysis
- `numpy` - Numerical computing
- `matplotlib` - Static plotting and visualization
- `seaborn` - Statistical data visualization
- `plotly` - Interactive visualizations and animations

### Step 4: Launch Jupyter Notebook
```bash
jupyter notebook Visualization_Product.ipynb
```

## 🚀 Usage

### Running the Jupyter Notebook

1. **Open the notebook**:
   ```bash
   jupyter notebook Visualization_Product.ipynb
   ```

2. **Execute cells sequentially**: Run cells from top to bottom to load data, perform analysis, and generate visualizations.

3. **Example: Loading and Analyzing CO₂ Data**
   ```python
   import pandas as pd
   import plotly.express as px
   
   # Load CO2 emissions data
   co2_data = pd.read_csv('data/CO2 Consumption emissions  1800 - 2022 - Dataset - v2 - Data source.csv')
   
   # Create choropleth map
   fig = px.choropleth(co2_data,
                       locations='Country',
                       locationmode='country names',
                       color='CO2_per_capita',
                       animation_frame='Year',
                       title='Global CO₂ Emissions Per Capita')
   fig.show()
   ```

4. **Example: Sectoral Analysis**
   ```python
   # Load greenhouse gas emissions data
   ghg_data = pd.read_csv('data/ghg-emissions.csv')
   
   # Analyze emissions by sector
   sector_emissions = ghg_data.groupby('Sector')['Emissions'].sum()
   
   # Create visualization
   import matplotlib.pyplot as plt
   plt.figure(figsize=(10, 6))
   sector_emissions.plot(kind='bar')
   plt.title('CO₂ Emissions by Sector')
   plt.ylabel('Total Emissions (MtCO₂e)')
   plt.xlabel('Sector')
   plt.xticks(rotation=45)
   plt.tight_layout()
   plt.show()
   ```

### Using Tableau Dashboard

1. **Open Tableau file**:
   - Navigate to the `Tableau/` directory
   - Open `Renewable energies - policies.twb` in Tableau Desktop or Tableau Reader

2. **Interact with visualizations**:
   - Use filters to select specific countries or regions
   - Adjust time ranges to focus on specific periods
   - Hover over data points for detailed information

3. **Export visualizations**:
   - Sample visualizations are available as PNG files in the `Tableau/` directory:
     - `Regional Comparision of Renewable Energy.png`
     - `Renewable Energy Utilization Over Time.png`

### Working with Data

All datasets are located in the `data/` directory:
```python
# Load different datasets
import pandas as pd

# CO2 emissions data
co2_data = pd.read_csv('data/CO2 Consumption emissions  1800 - 2022 - Dataset - v2 - Data source.csv')

# Population data
population = pd.read_csv('data/pop.csv')

# GNI per capita data
gni_data = pd.read_csv('data/gnicap_atm_con.csv')

# Greenhouse gas emissions by sector
ghg_emissions = pd.read_csv('data/ghg-emissions.csv')

# Land-use emissions
land_use = pd.read_csv('data/co2-land-use.csv')
```

## 📁 Project Structure

```
Final-Project/
├── Visualization_Product.ipynb    # Main Jupyter notebook with analysis
├── README.md                      # Project documentation
├── requirements.txt               # Python dependencies
├── LICENSE                        # MIT License
├── renewable energies.xlsx        # Renewable energy dataset
├── data/                          # Data directory
│   ├── CO2 Consumption emissions  1800 - 2022 - Dataset - v2 - Data source.csv
│   ├── co2-land-use.csv
│   ├── ghg-emissions.csv
│   ├── gnicap_atm_con.csv
│   ├── pop.csv
│   └── share-co2-emissions-vs-population.csv
└── Tableau/                       # Tableau visualizations
    ├── Renewable energies - policies.twb
    ├── Regional Comparision of Renewable Energy.png
    └── Renewable Energy Utilization Over Time.png
```

## 📊 Data Sources

This project utilizes high-quality datasets from reputable sources:

1. **Gapminder** ([gapminder.org](https://gapminder.org))
   - CO₂ emissions by country (total and per capita)
   - Population data (historical and forecasted)
   - Gross National Income (GNI) per capita

2. **Climate Watch** ([climatewatchdata.org](https://climatewatchdata.org))
   - Sector-wise greenhouse gas emissions
   - Country-level emissions data

3. **IRENA** ([irena.org](https://irena.org))
   - Renewable energy installed capacity
   - Technology-specific renewable energy data

### Data Characteristics
- **Temporal Coverage**: 1800-2022 (historical and recent data)
- **Geographic Coverage**: Global, with country-level granularity
- **Sectoral Breakdown**: Energy, Agriculture, Industrial Processes, Waste, Land-Use Change

## 🔬 Research Questions

This project addresses seven key research questions:

1. **Which countries have contributed the most to global CO₂ emissions?**
   - Analysis of historical and cumulative emissions
   - Identification of top emitting nations

2. **Which countries have the highest per capita CO₂ emissions annually, and why?**
   - Per capita emission calculations
   - Correlation with income levels and industrialization

3. **How do CO₂ emissions vary across income groups globally?**
   - Income-based emission distribution
   - Equity analysis in global emissions

4. **Is there any relationship between population and CO₂ emissions?**
   - Statistical correlation analysis
   - Population vs. emissions scatter plots

5. **Which sector has the highest impact on CO₂ emissions?**
   - Sectoral contribution breakdown
   - Energy, Agriculture, Industrial, and other sectors

6. **How are the trends in CO₂ emissions from land-use change and forestry evolving?**
   - Land-use change analysis
   - Afforestation impact assessment

7. **What are the policy recommendations to reduce CO₂ emissions?**
   - Evidence-based policy framework
   - Renewable energy adoption strategies

## 📈 Visualizations

### Sample Visualizations from Tableau Dashboard

#### Regional Comparison of Renewable Energy
![Regional Comparison](Tableau/Regional%20Comparision%20of%20Renewable%20Energy.png)

*Interactive visualization comparing renewable energy capacity across different regions, showing the growth and adoption patterns of various renewable technologies.*

#### Renewable Energy Utilization Over Time
![Renewable Energy Over Time](Tableau/Renewable%20Energy%20Utilization%20Over%20Time.png)

*Time-series analysis demonstrating the exponential growth of renewable energy capacity globally, with breakdowns by technology type (solar, wind, hydro, etc.).*

### Jupyter Notebook Visualizations

The Jupyter notebook includes:
- **Animated Choropleth Maps**: Show CO₂ emissions evolution by country over time
- **Bar Charts**: Compare emissions across income groups and countries
- **Scatter Plots**: Visualize population vs. emissions relationships
- **Pie Charts**: Display sectoral contribution to total emissions
- **Line Graphs**: Track emission trends and renewable energy growth

## 🔍 Key Findings

### Historical Emissions
- **United States**: Largest historical emitter, contributing ~25% of cumulative global CO₂ emissions
- **China**: Highest current annual emitter, reflecting rapid industrialization
- **Top 7 Countries**: Account for majority of global emissions since the Industrial Revolution

### Per Capita Analysis
- **High-income nations** (e.g., Saudi Arabia, USA, Australia) show significantly higher per capita emissions
- **Sub-Saharan Africa**: Among the lowest per capita emissions despite population size
- **Income correlation**: Strong positive relationship between GNI per capita and emissions

### Income Group Disparities
- **High-income countries**: Contribute >80% of global emissions with smaller population share
- **Low-income countries**: Contribute only ~18% despite housing ~50% of global population
- Clear evidence of **emissions inequality** based on economic development

### Sectoral Breakdown
- **Energy sector**: Dominant contributor at 76.3% of total emissions
- **Agriculture**: Second largest at 13.4%
- **Industrial Processes, Waste, Land-Use**: Smaller but significant contributions

### Renewable Energy Trends
- **Rapid growth**: Solar and wind capacity expanding exponentially
- **Regional variation**: Europe and Asia leading in renewable adoption
- **Technology shift**: Decreasing costs driving wider deployment

### Land-Use Change
- **Net negative contribution**: Reflects global afforestation and reforestation efforts
- **Regional variation**: Some areas show emission increases, others decreases

## 📌 Policy Recommendations

Based on our analysis, we recommend:

### 1. Expand Renewable Energy Adoption
- Accelerate investment in solar, wind, and other renewable technologies
- Target 100% renewable energy in electricity generation by 2050
- Prioritize deployment in high-emission countries

### 2. Incentivize Renewable Energy Deployment
- Implement subsidies and tax breaks for renewable installations
- Create favorable regulatory frameworks
- Support public-private partnerships

### 3. Promote Research & Development
- Increase funding for emerging technologies (energy storage, green hydrogen)
- Support innovation in carbon capture and storage
- Develop next-generation renewable technologies

### 4. Support Energy Efficiency Measures
- Mandate energy audits for large facilities
- Promote adoption of energy-efficient technologies
- Implement building efficiency standards
- Encourage sustainable transportation

### 5. Address Emissions Inequality
- Support developing nations in clean energy transitions
- Establish fair carbon pricing mechanisms
- Provide technology transfer and capacity building

## 🧑‍💼 Team

This project was developed by graduate students in the DATS 6401 Data Visualization course:

- **Prudhvi Chekuri**
  - Country-level CO₂ emissions analysis
  - Interactive plots and animations
  - Choropleth map development

- **Satya Phanindra Kumar Kalaga**
  - Sectoral analysis of emissions
  - Project structuring and organization
  - Advanced visualization techniques

- **Deepika Reddygari**
  - Renewable energy analysis
  - Policy recommendations
  - Technical report writing and documentation

## 📄 Description of Data
### Dataset Details

The analysis is based on datasets sourced from Gapminder, Climate Watch, and IRENA:

1. **CO₂ Emissions by Country**: Total and per capita CO₂ emissions (Gapminder).
2. **Population by Country**: Historical and forecasted population data (Gapminder).
3. **Gross National Income (GNI) Per Capita**: Income levels for countries (Gapminder).
4. **CO₂ Emissions by Sector**: Sector-wise emissions data (Climate Watch).
5. **Renewable Energy Dataset**: Installed electricity capacity by technology (IRENA).

Key Features of the Data:
- **Temporal Coverage**: Data spans multiple decades.
- **Regional Segmentation**: Organized by country and region.
- **Sectoral Breakdown**: Detailed sector-wise emissions.

## 📊 Conclusion

CO₂ emissions drive climate change, leading to rising temperatures, extreme weather events, and biodiversity loss. This project demonstrates that addressing emissions requires:

- **Global collaboration** across nations and sectors
- **Technological innovation** in renewable energy and carbon capture
- **Equitable climate policies** that address emissions inequality
- **Data-driven decision making** informed by comprehensive analysis

The visualizations and analyses presented in this dashboard provide actionable insights for policymakers, researchers, and environmental advocates working toward a sustainable future.

## ⚠️ Limitations

- **Data gaps**: Incomplete data for certain regions and sectors, particularly in developing nations
- **Scope**: Focus limited to CO₂, excluding other greenhouse gases (methane, nitrous oxide, etc.)
- **Historical data**: Earlier periods (pre-1950) have less granular country-level data
- **Sectoral classifications**: Variations in sector definitions across data sources

## 🔮 Future Directions

- **Multi-gas analysis**: Expand to include methane, nitrous oxide, and other GHGs
- **Enhanced granularity**: Incorporate sub-national and city-level emissions data
- **Predictive modeling**: Develop forecasting models for future emissions scenarios
- **Real-time dashboards**: Integrate near-real-time emissions monitoring
- **Policy impact analysis**: Quantify effects of implemented climate policies
- **Economic modeling**: Include detailed cost-benefit analyses of mitigation strategies

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

### MIT License Summary
```
MIT License

Copyright (c) 2024 DATS6401

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

## 📞 Contact

This project was developed as part of the **DATS 6401 - Data Visualization** course at George Washington University.

### Get In Touch

- **Repository**: [DATS6401/Final-Project](https://github.com/DATS6401/Final-Project)
- **Issues**: For bugs or feature requests, please [open an issue](https://github.com/DATS6401/Final-Project/issues)
- **Contributions**: We welcome contributions! Please feel free to submit pull requests

### Team Members

For questions or collaboration opportunities, please reach out through the GitHub repository.

---

## 🙏 Acknowledgments

We would like to thank:
- **Gapminder** for providing comprehensive global development data
- **Climate Watch** for detailed emissions tracking datasets
- **IRENA** for renewable energy statistics
- **George Washington University** and the DATS 6401 instructors for guidance and support

---

## 📚 References

1. **Gapminder Foundation**: [CO₂ Emissions by Country](https://gapminder.org)
   - Historical emissions data and socio-economic indicators

2. **Climate Watch**: [Global Greenhouse Gas Emissions](https://climatewatchdata.org)
   - Comprehensive emissions data by sector and country

3. **IRENA**: [Renewable Energy Statistics](https://irena.org)
   - Global renewable energy capacity and generation data

4. **IPCC**: [Climate Change Reports](https://www.ipcc.ch/)
   - Scientific basis for climate change analysis

5. **Our World in Data**: [CO₂ and Greenhouse Gas Emissions](https://ourworldindata.org/co2-and-other-greenhouse-gas-emissions)
   - Additional context and visualization inspiration

---

<div align="center">

**⭐ If you find this project useful, please consider giving it a star!**

Made with ❤️ for a sustainable future 🌱

</div>

