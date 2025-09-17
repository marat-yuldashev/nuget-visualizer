# NuGet Package Visualizer

A web-based dashboard for visualizing NuGet package analytics from your company's Artifactory repository. Built for GitHub Pages deployment with interactive charts and modern responsive design.

## Features

- 📊 **Package Statistics**: Overview of total packages, downloads, and version metrics
- 📈 **Interactive Charts**: Bar charts for download distribution and doughnut charts for version analysis
- 📋 **Detailed Package Table**: Sortable table with package information including downloads and last update dates
- 🎨 **Modern UI**: Responsive design with gradient backgrounds and hover effects
- 📱 **Mobile Friendly**: Optimized for desktop and mobile viewing

## Quick Start

1. **Clone or download** this repository
2. **Enable GitHub Pages** in your repository settings
3. **Access your dashboard** at `https://yourusername.github.io/your-repo-name`

## File Structure

```
nuget-visualizer/
├── index.html          # Main dashboard page
├── packages.json       # Sample NuGet package data
└── README.md          # This file
```

## Data Format

The dashboard expects JSON data in the following format:

```json
[
  {
    "name": "Package.Name",
    "version": "1.2.3",
    "downloads": 15420,
    "lastUpdated": "2024-03-15",
    "description": "Package description"
  }
]
```

## Connecting to Artifactory

To connect to your actual Artifactory repository:

1. **Update the data source** in `index.html`:
   ```javascript
   // Replace this line:
   const response = await fetch('packages.json');
   
   // With your Artifactory API endpoint:
   const response = await fetch('https://your-artifactory.com/api/packages');
   ```

2. **Configure authentication** if required (add headers to the fetch request)

3. **Modify data mapping** in the `displayData()` function if your API response structure differs

## Customization

### Styling
- Colors and themes can be modified in the `<style>` section of `index.html`
- Chart colors are defined in the `createCharts()` functions

### Charts
- Chart types and configurations use Chart.js
- Modify chart options in `createDownloadsChart()` and `createVersionsChart()` functions

### Data Display
- Table columns can be modified in the `populateTable()` function
- Statistics cards can be customized in the `updateStats()` function

## Dependencies

- **Chart.js**: Loaded via CDN for data visualization
- **Modern browsers**: Supports ES6+ features (async/await, fetch API)

## GitHub Pages Deployment

1. Push your files to a GitHub repository
2. Go to **Settings** → **Pages**
3. Select **Deploy from a branch** → **main** → **/ (root)**
4. Your site will be available at `https://yourusername.github.io/repository-name`

## Browser Compatibility

- Chrome 60+
- Firefox 55+
- Safari 11+
- Edge 79+

## License

This project is open source and available under the [MIT License](LICENSE).