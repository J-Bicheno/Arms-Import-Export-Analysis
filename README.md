# Global Arms Trade Analysis

**Global Arms Trade Analysis** is a comprehensive data analytics project that investigates the intricate trading relationships between countries in the global arms market. Focusing on military vehicles and armaments, this tool leverages data science techniques to uncover patterns, trends, and influences that shape international security dynamics.


# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

---

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset Description](#dataset-description)
- [Business Requirements](#business-requirements)
- [Hypotheses](#hypotheses)
- [Project Plan & Methodology](#project-plan--methodology)
- [Data Visualisation Mapping](#data-visualisation-mapping)
- [Analysis Techniques](#analysis-techniques)
- [Ethical Considerations](#ethical-considerations)
- [Dashboard Design](#dashboard-design)
- [Known Issues & Limitations](#known-issues--limitations)
- [Development Roadmap & Reflection](#development-roadmap--reflection)
- [Deployment Instructions](#deployment-instructions)
- [Core Libraries Used](#core-libraries-used)
- [Credits](#credits)
- [Acknowledgements](#acknowledgements)

---

## Project Overview

This project aims to analyze and visualize global arms trading data to help answer questions such as:
- Which countries exert the most influence on global conflicts via arms exports/imports?
- How do trade patterns evolve over time?
- Are there distinct clusters of nations based on their trading profiles?

The dashboard provides interactive visualizations to communicate complex insights to both technical and non-technical audiences, supporting decision-making for researchers, analysts, and policymakers.

---

## Dataset Description

**Source:** [SIPRI Arms Transfers Database](https://www.sipri.org/databases/armstransfers)
The data is from the Stockholm International Peace Research Institute (SIPRI) Arms Transfers Database (https://doi.org/10.55163/SAFC1241). The data remains the sole intellectual property of SIPRI and cannot be used for any commercial purposes without licensed authorization from SIPRI. For further information please see the SIPRI website: https://www.sipri.org/about/terms-and-conditions.

The SIPRI Trade Register dataset was chosen for its:
- **Manageable size:** Medium-sized, enabling deep analysis without memory issues.
- **Well-structured format:** Although some flaws exist, they provide opportunities to apply and showcase robust ETL and data cleaning techniques.
- **Richness:** Contains 13 core columns (excluding 3 empty ones), suitable for feature engineering and advanced analytics.
- **Credibility:** SIPRI is independent, reducing bias risk.

## TIV (Trend Indicator Value)
- **Important Note:** This dataset measures each order and piece of equipment by it's TIV as opposed to it's monetary value
- This value is calculated by comparing several different factors
- For more inofrmation on TIV and how it's applied and calculated refer to this report/fact sheet: (https://www.sipri.org/sites/default/files/files/FS/SIPRIFS1212.pdf)

## Key Columns

| Column Name         | Description                                                                                  |
|---------------------|---------------------------------------------------------------------------------------------|
| Year of Order            | Calendar year when the arms transfer or deal occurred.                                      |
| Supplier     | Country or entity that supplied the military equipment; used for export analysis.            |
| Recipient   | Country or entity that received the equipment; used for import analysis and trade mapping.   |
| Weapon Description         | General category of military equipment, such as aircraft, naval vessels, or vehicles.        |
| Weapon Designation  | Detailed specification of the weapon system, including model, subtype, and capabilities.     |
| SIPRI TIV for Total Order     | standardized value assigned to the transfer, allowing for deal magnitude analysis.|
| Number Delivered  | Total number of units or items delivered per deal; helps quantify overall volume of transfers.|
| Status      | Comments on quality of units delivered, e.g. Second Hand but modernized |
| Comments               | Additional remarks, clarifications, or context provided by the dataset for certain records.  |
---

## Business Requirements

- **Core Objective:** Demonstrate which countries most influence global conflict via arms trading.
- **Focus Areas:**
    - Highlight nations with disproportionate influence.
    - Reveal trade imbalances and clusters.
    - Enable exploration of trends over time and deal sizes.

---

## Hypotheses

1. **Stability in Low-Value Deals:** Lower value arms deals are stable over time, while large orders fluctuate.
    - *Validation:* KDE plots, probability heatmaps.
2. **Country Clustering:** Countries fall primarily into Importer, Exporter, or Balanced Trader clusters.
    - *Validation:* K-means clustering, visual cluster analysis.
3. **Dominant Exporters:** The United States is hypothesized to be the largest exporter.
    - *Validation:* Feature engineering, bar/lollipop charts.

---

## Project Plan and Methodology

### High-Level Steps

1. **Data Acquisition:** Download and validate dataset integrity.
2. **ETL:** Clean, transform, and enrich data via Pandas and custom scripts.
3. **Exploratory Analysis:** Use descriptive statistics and initial visualizations to identify trends.
4. **Feature Engineering:** Create metrics such as trade balance, deal magnitude, cluster assignment.
5. **Clustering & Advanced Analysis:** Apply k-means and other unsupervised learning methods.
6. **Visualization:** Build interactive dashboard using Power BI.
7. **Interpretation:** Summarize findings for both technical and non-technical audiences.

### Research Methodologies

- **Quantitative Analysis:** Statistical summaries, regression, clustering.
- **Visual Analytics:** Time series plots, heatmaps.

---

## Data Visualisation Mapping

| Business Requirement | Visualization Type                    | Rationale                                                        |
|----------------------|--------------------------------------|------------------------------------------------------------------|
| Influence Analysis   | Bar chart, interactive map           | Highlight top exporters/importers and their trading networks     |
| Trend Analysis       | Line/KDE plot, heatmap               | Show deal stability and fluctuations over time                   |
| Clustering           | Cluster scatterplot, silhouette plot  | Visually communicate country groupings and their characteristics |

---

## Analysis Techniques

- **ETL & Data Cleaning:** Remove nulls, correct outliers, standardize country names, handle missing columns.
- **Feature Engineering:** Calculate trade balances, deal values, normalize quantities.
- **Scaling** Log scaling applied 
- **Clustering:** K-means, visual and quantitive cluster analysis.
- **Visualization:** Plotly/Matplotlib/Seaborn for charts, geopandas for mapping.
- **Dashboarding:** Dash/Streamlit for interactive exploration.
- **Generative AI Tools:** Used for ideation, code optimization, and documentation drafting.

### Limitations and Alternatives

- **Data Gaps:** Some deals lack full details—imputed values or aggregate trends used as fallback.
- **Bias Risk:** SIPRI is independent, but reporting from some countries may be inconsistent.
- **Method Alternatives:** Where clustering may have failed, binary classification was considered.

---

## Ethical Considerations

- **Data Privacy:** Dataset is aggregate and public; no personal data involved, followed SIPRI fair use policy.
- **Bias and Fairness:** Monitored for representation or reporting gaps. Results interpreted with context.
- **Societal Impact:** The tool is for academic and policy analysis, not for promoting arms trading.

---

## Dashboard Design

### Pages and Widgets

1. **Global Overview:** Top trading countries, interactive world map, summary stats.
2. **Time Series Explorer:** Arms deals over years, filter by country/type.
3. **Cluster Analysis:** Visualize clusters, export/import balances.
4. **Deal Details:** Searchable table of individual deals.
5. **Insights & Download:** Summary, downloadable graphs/data.

**Widgets:** Dropdowns, checkboxes (country/type filters), interactive maps, export buttons, images, tooltips.

### Communication Approach

- **Technical Audiences:** Detailed stats, downloadable datasets, advanced filters.
- **Non-Technical Audiences:** Simplified insights, key takeaways, annotated visuals.

---

## Known Issues and Limitations

- **Knowledge Gaps:** Initial unfamiliarity with advanced clustering—addressed via tutorials

---

## Development Roadmap and Reflection

- **Challenges:** Handling missing data, optimizing dashboard responsiveness, learning new libraries.
- **Strategies:** Incremental development, peer code reviews, use of open-source resources.
- **Next Steps:** Deeper geospatial analysis, expand to other datasets.

---

## Deployment Instructions

### Heroku

1. Fork/clone the repo.
2. Set `runtime.txt` to a [supported Python version](https://devcenter.heroku.com/articles/python-support#supported-runtimes).
3. Ensure `requirements.txt` is up to date.
4. [Create an app on Heroku](https://heroku.com), connect to GitHub, and deploy.
5. Handle slug size issues with `.slugignore` as needed.
6. App live link: https://YOUR_APP_NAME.herokuapp.com/

---

## Core Libraries Used

- **Pandas:** Data cleaning, transformation, aggregation.
- **NumPy:** Numerical computation.
- **SciPy** Statistical analysis.
- **Matplotlib/Seaborn/Plotly:** Visualizations.
- **Scikit-learn:** Clustering, feature scaling.
   
  
---

## Credits

### Content

- SIPRI Arms Transfers Database for core dataset.
- Wikipedia for contextual background.

### Media

- Icons: [Font Awesome](https://fontawesome.com/)
- Images: [Open-source photo sites], [Code Institute CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

### Tutorials & Examples

- Form validation: [Specific YouTube Tutorial](https://www.youtube.com/)
- Dashboard inspiration: [ATT Monitor](https://attmonitor.org/en/att-arms-dashboard)

---

## Acknowledgements

Special thanks to my peers and my facilitator Vasi for feedback and support throughout this project.

---

