# Cover Crop Web Application

Interactive visualization tool for analyzing cover crop data in almond orchards using deck.gl and MapLibre GL.

## Features

- **Interactive Polygon Visualization**: Displays orchard boundaries with cluster role colors
- **Time-series Controls**: Scrub through seasons from 2017-2023
- **Filtering Options**: Filter by stratum (Young/Mid) and flipped orchards
- **Real-time Statistics**: Live counts of Active, Mixed, Baseline, and Flipped orchards
- **Individual Orchard Analysis**: Click orchards to see detailed time-series charts
- **High Performance**: Handles 3,600+ orchard polygons with smooth interaction

## Tech Stack

- **deck.gl v8.9.36**: WebGL-powered data visualization
- **MapLibre GL v3.6.2**: Interactive maps without API keys
- **PapaParse v5.4.1**: Fast CSV parsing
- **Plotly v2.35.2**: Interactive charts and plots

## Files

- `enhanced_dashboard.html`: Main application with full functionality
- `viz_table.csv`: Time-series data for orchard analysis (25,456 records)
- `FresnoAlmondOrchards.geojson`: Polygon boundaries for 3,637 orchards
- `deck_gl_cover_crop_viz_starter_index.html`: Original point-based visualization

## Getting Started

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd CoverCrop_webAPP
   ```

2. **Start a local server**
   ```bash
   python -m http.server 8000
   ```

3. **Open the application**
   Navigate to `http://localhost:8000/enhanced_dashboard.html`

## Data Structure

### CSV Data (viz_table.csv)
- **orch_id**: Unique orchard identifier
- **season**: Season label (e.g., "2017_2018") 
- **season_sort**: Numeric season identifier
- **stratum**: Age category (Young/Mid)
- **cluster_role**: Classification (Active/Mixed/Baseline)
- **best_soft_norm**: Normalized fitness score
- **cluster_role_color**: Hex color for visualization

### GeoJSON Data (FresnoAlmondOrchards.geojson)
- **Polygon geometries**: Orchard boundaries
- **orch_id**: Links to CSV data
- **ACRES, CNTY**: Property metadata

## Color Scheme

- 🟢 **Active** (#2ca25f): High-performing orchards
- 🟣 **Mixed** (#6a51a3): Variable performance
- ⚫ **Baseline** (#808080): Standard/control orchards

## Development

The application uses modern browser APIs and requires a local server due to CORS restrictions when loading local files.

## Validation

This implementation has been validated against the deck.gl documentation and knowledge base using MCP (Model Context Protocol) systems to ensure all APIs and integration patterns are legitimate.