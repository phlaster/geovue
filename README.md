# geovue

A single-page web application for visualizing geospatial CSV data on an interactive world map. Built with vanilla JS, Leaflet, and Tailwind CSS.

## Features

- **Interactive Map**: Pan and zoom world map with dark mode styling.
- **CSV Parsing**: Drag-and-drop or click to upload CSV files.
- **Dynamic Groupings**: Visualize data dimensions via Color, Shape, and Size.
- **Smart Type Detection**: Automatically detects numeric vs. categorical columns.
- **Interactive Tooltips**: Hover over markers to see detailed row data.
- **Dynamic Legend**: Automatically updates to reflect current visual encodings.

## CSV File Requirements

The application accepts standard CSV files (comma-separated values).

### Mandatory Columns
The CSV **must** contain the following exact column names (case-sensitive):
- `lat`: Latitude values (numeric).
- `lon`: Longitude values (numeric).

### Optional Columns
You may include any number of additional columns for grouping or information display.

### Example Format
```csv
id,lat,lon,city,population,category
1,48.8566,2.3522,Paris,2161000,Capital
2,51.5074,-0.1278,London,8982000,Capital
3,45.4642,9.1900,Milan,1352000,Metropolis
```

## Grouping Logic

You can add up to **3 groupings** total to visualize different dimensions of your data. The visual encoding (aesthetic) applied depends on the data type and the order in which groupings are added.

### Constraints
- **Maximum 2 Factor (Categorical) Groupings**
- **Maximum 1 Numeric Grouping**

### Visual Encoding

| Order | Data Type | Visual Encoding | Description |
| :--- | :--- | :--- | :--- |
| **1st Factor** | Categorical | **Color** | Assigns a unique color to each category. |
| **2nd Factor** | Categorical | **Shape** | Assigns a unique shape to each category. |
| **1st Numeric** | Numeric | **Size** | Scales marker size proportionally to the value. |


## How to Use

1.  Open `geovue.html` in a modern web browser.
2.  Drag and drop a `.csv` file onto the upload zone (or click to browse).
3.  Once loaded, click **"Add grouping"**.
4.  Select a column from the list. The system will automatically determine if it is Numeric (Size) or Factor (Color/Shape).
5.  Repeat for additional dimensions (e.g., add a second Factor for shapes, or a Numeric column for size).

## Technical Stack

- **Map Engine**: [Leaflet.js](https://leafletjs.com/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **Fonts**: Google Fonts (Space Grotesk, IBM Plex Mono)
- **Architecture**: Single-file HTML/JS application (no build step required).

> This project is made with assistance of GLM-5 by [Z.ai](https://chat.z.ai)