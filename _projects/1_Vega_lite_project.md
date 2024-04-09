---
name: Vega Lite Project
tools: [Python, HTML, vega-lite]
description: This is a project that uses vega-lite for interactive viz
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---
# BFRO Reports

## Visualization 1: Bigfoot Sightings by State
<vegachart schema-url="{{ site.baseurl }}/assets/json/barchart.json" style="width: 100%"></vegachart>
<ol>
  <li>Description</li>
  This visualization presents the number of Bigfoot sightings over time, displayed as a bar chart. The interactive slider allows users to filter sightings by year.
  <li>Design Choices</li>
    <ul>
      <li>Encoding Types: The year is encoded on the x-axis as an ordinal field, and the count of sightings is encoded on the y-axis as a quantitative field.</li>
      <li>Color Scheme: Color is used for the bars to maintain a clear focus on the temporal distribution. The simplicity of the color scheme aids in readability and avoids unnecessary distractions.</li>
      <li>Data Transformations: The primary transformation was extracting the year from the date column for temporal analysis. Additionally, the dataset was cleaned to remove entries with incomplete date information.</li>
    </ul>
  <li>Interactivity</li>
    <ul>
      <li>Tooltips: Displaying sighting details on hover.</li>
    </ul>
</ol>

## Visualization 2: Seasonal Bigfoot Sightings Trend Over Years
<vegachart schema-url="{{ site.baseurl }}/assets/json/areachart_season.json" style="width: 100%"></vegachart>
<ol>
	<li>Description</li>
  The visualization shows the trend of Bigfoot sightings across different seasons over the years. The overall number of sightings is shown in the region graphic, which also shows how the frequency of reports varies seasonally and over time.
  <li>Design Choices</li>
    <ul>
      <li>Encoding Types: The year of sightings is encoded along the x-axis, representing time as an ordered series. The count of sightings is encoded on the y-axis, quantifying the sightings. The 'season' is a nominal categorical variable and is represented as different colors in the chart.</li>
      <li>Color Scheme: To make the transitions between seasons evident, a color palette with several hues was used. The use of discrete hues for every season aids in distinguishing the data layers inside the area chart and simplifies comparison.</li>
      <li>The dataset underwent a grouping operation where sightings were grouped by 'year' and 'season'. The 'date' column was parsed to extract the 'year' information if not already present in integer format.</li>
    </ul>
  <li>Interactivity</li>
    <ul>
      <li>Tooltip Interactivity: As users hover over different parts of the area chart, tooltips provide specific information about the number of sightings for a given year and season.</li>
      <li>Zoom and Pan: Users can explore different regions in detail, making the vast dataset more navigable and the visualization more engaging.</li>
    </ul>
</ol>


<div class="left">
{% include elements/button.html link="https://github.com/jca-9lmc/jca-9lmc.github.io/blob/main/assets/json/bfro_cleaned.json" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/jca-9lmc/jca-9lmc.github.io/blob/main/python_notebooks/Analysis.ipynb" text="The Analysis" %}
</div>

