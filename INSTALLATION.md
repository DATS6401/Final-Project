# Installation and Usage Guide

This guide provides detailed instructions for setting up and using the Global CO₂ Emissions Analysis Dashboard.

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
├── INSTALLATION.md                # Installation and usage guide
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
