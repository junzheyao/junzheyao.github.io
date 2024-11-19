---
name: License Dataset Visualizations
tools: [Python, Vega-Lite, Altair, HTML]
image: assets/pngs/cars.png
description: Visualizing license data using Altair.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
---

# Licenses Visualization Project

## Analysis of Licenses Issued Over Time

- **Features Highlighted:**  
  This visualization shows the number of licenses issued over 5-year intervals to observe trends in licensing activity over time. Because the first half of the twentieth century had relatively small amount of licenses issued, the line chart includes an interactive slider that allows users to dynamically filter the starting year for the visualization, with a default set to 1910. This interactive feature helps users explore specific periods of interest while maintaining the broader trend's visibility. 
- **Design Choices - Encodings:**  
  The temporal progression is displayed on the x-axis (`YearBin`) as ordinal data, while the y-axis (`Count`) shows the number of licenses issued in each 5-year interval. Tooltips are added to provide exact values for each data point when hovered over. A line chart with points was chosen to make temporal patterns and individual intervals clear and easy to read.

- **Design Choices - Colormaps:**  
  No color encoding is used for this visualization as the focus is solely on the temporal trend, and color was not necessary to differentiate data points.

- **Data Transformations:**  
  The dataset was filtered to exclude null values in the `Original Issue Date` column. Additionally, a new column, `YearBin`, was created by grouping years into 5-year bins using integer division and then grouping by these bins to calculate the count of licenses in each interval.

- **Overlap with Homework #5:**  
  This visualization extends the analysis from Homework #5 by adding an interactive slider to allow dynamic selection of the starting year. This makes the plot more interactive and customizable compared to the static chart in Homework #5.

- **Interactivity:**  
  The slider interactivity allows users to dynamically filter the starting year, providing flexibility in focusing on specific time periods. This enhances the utility of the visualization, making it more engaging and informative for users.


<vegachart schema-url="https://github.com/junzheyao/junzheyao.github.io/blob/main/licenses_over_time.json" style="width: 100%;"></vegachart>

---

## Analysis of Licenses by Status

- **Features Highlighted:**  
  This bar chart visualizes the distribution of licenses by status, excluding 'NOT RENEWED', which dominates the data and could obscure insights into other categories. By focusing on active and inactive licenses, users can better understand the overall distribution and variability in license statuses.

- **Design Choices - Encodings:**  
  The x-axis encodes the categorical variable `License Status` as ordinal data, sorted by descending count. The y-axis encodes the number of licenses (`Count`) as quantitative data. Tooltips are added to display exact counts for each status.

- **Design Choices - Colormaps:**  
  No color encoding is used for this visualization as the focus is solely on the count of license status, and color was not necessary to differentiate the bars.

- **Data Transformations:**  
  The dataset was filtered to exclude the 'NOT RENEWED' status for clarity. A `value_counts` operation was performed to calculate the count of each remaining license status, and the results were reset into a DataFrame for plotting.

- **Overlap with Homework #5:**  
 This visualization is based on what I have done for HW5

- **Interactivity:**  
  Currently, this visualization does not include interactive elements.

<vegachart schema-url="https://github.com/junzheyao/junzheyao.github.io/blob/main/licenses_by_status.json" style="width: 100%;"></vegachart>

---

## Links to Data & Analysis

<div class="left">
{% include elements/button.html link="https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/licenses_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/junzheyao/junzheyao.github.io/blob/main/HW6_Workbook.ipynb" text="The Analysis" %}
</div>
