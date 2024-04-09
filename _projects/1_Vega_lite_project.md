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

## Visualization 1: Map of Sightings
<vegachart schema-url="{{ site.baseurl }}/assets/json/heatmap.json" style="width: 100%"></vegachart>
<ol>
	<li>Description</li>
  The geographical heatmap visualizes the distribution of Bigfoot sightings across the United States. Each sighting is represented as a circle on the map, positioned according to its reported latitude and longitude.
  <li>Design Choices</li>
    <ul>
      <li>Encoding Types: Latitude and longitude are encoded as quantitative fields, positioning the circles on the map. The tooltip encodes the state, county, and date of each sighting for additional context when hovering over a point.</li>
      <li>Color Scheme: The circles are uniformly colored to emphasize their distribution rather than differentiating them by any specific characteristic.</li>
      <li>Data Transformations: The dataset underwent cleaning to ensure accurate geographical plotting. This included removing entries without valid latitude or longitude data and converting the date column to datetime format for tooltip display.</li>
    </ul>
  <li>Interactivity</li>
    <ul>
      <li>Tooltips: Displaying sighting details on hover provides immediate contextual information without cluttering the visualization.</li>
      <li>Zoom and Pan: Users can explore different regions in detail, making the vast dataset more navigable and the visualization more engaging.</li>
    </ul>
</ol>



## Visualization 2: Bigfoot Sightings by State
<vegachart schema-url="{{ site.baseurl }}/assets/json/barchart.json" style="width: 100%"></vegachart>
<ol>
  <li>Description</li>
  This visualization presents the number of Bigfoot sightings over time, displayed as a bar chart. The interactive slider allows users to filter sightings by year.
  <li>Design Choices</li>
    <ul>
      <li>Encoding Types: The year is encoded on the x-axis as an ordinal field, and the count of sightings is encoded on the y-axis as a quantitative field.</li>
      <li>Color Scheme: A single color is used for the bars to maintain a clear focus on the temporal distribution. The simplicity of the color scheme aids in readability and avoids unnecessary distractions.</li>
      <li>Data Transformations: The primary transformation was extracting the year from the date column for temporal analysis. Additionally, the dataset was cleaned to remove entries with incomplete date information.</li>
    </ul>
  <li>Interactivity</li>
    <li></li>
</ol>



<div class="left">
{% include elements/button.html link="https://github.com/jca-9lmc/jca-9lmc.github.io/blob/main/assets/json/bfro_cleaned.json" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/jca-9lmc/jca-9lmc.github.io/blob/main/python_notebooks/Analysis.ipynb" text="The Analysis" %}
</div>

