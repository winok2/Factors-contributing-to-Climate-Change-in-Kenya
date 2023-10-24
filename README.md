# Factors-contributing-to-Climate-Change-in-Kenya (1960-2022)


## Overview
This repository contains data and code for analyzing climate change trends in Kenya from 1960 to 2022 using Power BI. The project aims to provide insights into temperature and precipitation patterns, helping to understand the impact of climate change in the region over the past six decades.

## Data Sources
- The climate data for Kenya was obtained from [Humanitarian Data Exchange](https://data.humdata.org/dataset/08847ef3-da1c-4be4-8674-9707fe84128b/resource/4620d328-a2d2-4b5f-9eeb-f07e5bf95c9b/download/climate-change_ken.csv).
- Data file: climate_change_Kenya.csv
  
## Power BI Analysis
The analysis was performed using Power BI. You can access the analysis results and visualizations in the following ways:

1. **View the Power BI Report Online:** [Link to the online Power BI report]
2. **Download the Power BI Desktop File:** If you have Power BI Desktop, you can download the Power BI project file from the `power_bi_analysis` directory and open it locally for more in-depth exploration.

## Results
The Power BI analysis has revealed significant trends in climate change indicators in Kenya from 1960 to 2022:

- **CO2 Emissions:** The analysis indicates that CO2 emissions have shown an overall increase over the years. This suggests a growing concern for the country's carbon footprint.

- **Urban Population:** The data also reveals a consistent growth in the urban population of Kenya, signifying ongoing urbanization trends.

- **Forest Cover:** Contrary to expectations, forest cover has experienced a decline over the years, which may have implications for environmental conservation efforts.

- **Renewable Energy Consumption:** The analysis highlights a decrease in renewable energy consumption, possibly indicating the need for increased sustainable energy practices.

For a more detailed overview of these findings, you can explore the Power BI report or the Power BI Desktop file provided.


## Usage
To replicate or build upon this analysis using Power BI, follow these steps:
1. [Download and Install Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/).
2. Download the Power BI project file from the ` directory and open it in Power BI Desktop.
3. ## Power Query Code for Data Preparation
To prepare the data for analysis in Power BI, you can use the following Power Query code. This code loads the data, cleans it, and transforms it into a suitable format for your analysis.

```M
let
    Source = Csv.Document(File.Contents("C:\Users\kowin\Downloads\climate-change_ken.csv"),[Delimiter=",", Encoding=1252]),
    #"Promoted Headers" = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    #"Removed Empty Columns" = Table.SelectColumns(#"Promoted Headers", {"Year", "Indicator Name", "Value"}),
    #"Pivoted Column" = Table.Pivot(#"Removed Empty Columns", List.Distinct(#"Removed Empty Columns"[#"Indicator Name"]), "Indicator Name", "Value"),
    #"Changed Type" = Table.TransformColumnTypes(#"Pivoted Column",{
        {"Year", type text}, {"Agricultural land (sq. km)", type number}, {"Agricultural land (% of land area)", type number},
        {"Arable land (% of land area)", type number}, {"Rural land area where elevation is below 5 meters (sq. km)", type number},
        {"Rural land area where elevation is below 5 meters (% of total land area)", type number},
        {"Urban land area where elevation is below 5 meters (sq. km)", type number},
        {"Urban land area where elevation is below 5 meters (% of total land area)", type number},
        {"Land area where elevation is below 5 meters (% of total land area)", type number},
        {"Forest area (sq. km)", type number}, {"Forest area (% of land area)", type number},
        {"Average precipitation in depth (mm per year)", type number}, {"Cereal yield (kg per hectare)", type number},
        {"Foreign direct investment, net inflows (% of GDP)", type number}, {"Access to electricity (% of population)", type number},
        {"Renewable energy consumption (% of total final energy consumption)", type number},
        {"CO2 intensity (kg per kg of oil equivalent energy use)", type number},
        {"CO2 emissions from gaseous fuel consumption (kt)", type number},
        {"CO2 emissions from gaseous fuel consumption (% of total)", type number},
        {"CO2 emissions (kg per 2015 US$ of GDP)", type number}, {"CO2 emissions (kt)", type number},
        {"CO2 emissions from liquid fuel consumption (kt)", type number},
        {"CO2 emissions from liquid fuel consumption (% of total)", type number},
        {"CO2 emissions (metric tons per capita)", type number},
        {"CO2 emissions (kg per PPP $ of GDP)", type number}, {"CO2 emissions (kg per 2017 PPP $ of GDP)", type number},
        {"CO2 emissions from solid fuel consumption (kt)", type number},
        {"CO2 emissions from solid fuel consumption (% of total)", type number},
        {"Other greenhouse gas emissions, HFC, PFC and SF6 (thousand metric tons of CO2 equivalent)", type number},
        {"Other greenhouse gas emissions (% change from 1990)", type number},
        {"Total greenhouse gas emissions (kt of CO2 equivalent)", type number},
        {"Total greenhouse gas emissions (% change from 1990)", type number},
        {"HFC gas emissions (thousand metric tons of CO2 equivalent)", type number},
        {"Methane emissions (kt of CO2 equivalent)", type number},
        {"Methane emissions (% change from 1990)", type number},
        {"Nitrous oxide emissions (thousand metric tons of CO2 equivalent)", type number},
        {"Nitrous oxide emissions (% change from 1990)", type number},
        {"PFC gas emissions (thousand metric tons of CO2 equivalent)", type number},
        {"SF6 gas emissions (thousand metric tons of CO2 equivalent)", type number},
        {"Disaster risk reduction progress score (1-5 scale; 5=best)", type number},
        {"GHG net emissions/removals by LUCF (Mt of CO2 equivalent)", type number},
        {"Droughts, floods, extreme temperatures (% of population, average 1990-2009)", type number},
        {"Rural population living in areas where elevation is below 5 meters (% of total population)", type number},
        {"Urban population living in areas where elevation is below 5 meters (% of total population)", type number},
        {"Population living in areas where elevation is below 5 meters (% of total population)", type number},
        {"Population in urban agglomerations of more than 1 million (% of total population)", type number},
        {"Annual freshwater withdrawals, total (billion cubic meters)", type number},
        {"Annual freshwater withdrawals, total (% of internal resources)", type number},
        {"Terrestrial protected areas (% of total land area)", type number},
        {"Marine protected areas (% of territorial waters)", type number},
        {"Terrestrial and marine protected areas (% of total territorial area)", type number},
        {"Ease of doing business rank (1=most business-friendly regulations)", type number},
        {"CPIA public sector management and institutions cluster average (1=low to 6=high)", type number},
        {"Agriculture, forestry, and fishing, value added (% of GDP)", type number},
        {"School enrollment, primary and secondary (gross), gender parity index (GPI)", type number},
        {"Primary completion rate, total (% of relevant age group)", type number},
        {"Mortality rate, under-5 (per 1,000 live births)", type number},
        {"Prevalence of underweight, weight for age (% of children under 5)", type number},
        {"Poverty headcount ratio at $2.15 a day (2017 PPP) (% of population)", type number},
        {"Population growth (annual %)", type number},
        {"Population, total", type number},
        {"Urban population growth (annual %)", type number},
        {"Urban population", type number},
        {"Urban population (% of total population)", type number},
        {"Roads, paved (% of total roads)", type number}
    }),
    #"Filtered Rows" = Table.SelectRows(#"Changed Type", each true


## Contributing
Contributions to this project are welcome. If you have ideas for improvements or additional analyses using Power BI or other tools, please open an issue or submit a pull request.

## License
This project is open-source and available under the [MIT License](LICENSE). You are free to use, modify, and distribute the data and analysis results, but please give appropriate credit.

## Contact
For questions or inquiries, feel free to contact [Your Name] at [your@email.com].

---
[Optional: Add badges, acknowledgments, or any other relevant information here]
