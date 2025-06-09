# Section 899 Educational Tool

A dynamic, single-page web application designed to provide an educational overview of Section 899 of the Internal Revenue Code. All content is loaded dynamically from JSON files, allowing for easy updates and maintenance.

## Live Site

**The application is hosted on GitHub Pages and can be accessed here: [https://Dukes0O.github.io/IRC-899-pages/](https://Dukes0O.github.io/IRC-899-pages/)**

## Features

- **Dynamic Content Loading**: All informational pages (Home, Key Provisions, Legislation, FAQ) load their content from respective JSON files in the `data/` directory.
- **Interactive Navigation**: Smooth single-page application (SPA) style navigation using URL hash fragments.
- **Key Provisions Page**: Dynamically renders structured content including paragraphs, lists, definition lists, and Mermaid.js flowcharts from `data/key_provisions.json`.
- **Legislation Page**: Displays legislative text from `data/legislation.json`.
- **Glossary Integration**: Terms marked with the class `glossary-term` in the content will automatically display tooltips with definitions fetched from `data/glossary.json`. This functionality works for both statically and dynamically loaded content.
- **Impact Estimator**: A basic calculator and flowchart to estimate potential tax impacts.
- **FAQ Page**: Dynamically loads frequently asked questions from `data/faq.json`.

## Project Structure

The application files are located at the root of the `IRC-899-pages` repository:
- `index.html`: The main entry point for the single-page application.
- `css/`: Contains stylesheets.
- `js/`: Contains JavaScript modules for navigation, page-specific logic, and utilities (e.g., `navigation.js`, `home.js`, `key_provisions.js`, `glossary-links.js`).
- `data/`: Contains JSON files that drive the content of the application (e.g., `home_content.json`, `key_provisions.json`, `legislation.json`, `glossary.json`, `faq.json`).
- `pages/`: Contains HTML partials for each section, which are loaded into `index.html` by the navigation script.

## Running the Application Locally

1.  **Ensure you have Python installed.** This is used to run a simple HTTP server.
2.  **Navigate to the project root directory** in your terminal (e.g., `C:\Users\kyleb\CascadeProjects\IRC-899-pages`):
    ```bash
    cd path/to/your/IRC-899-pages
    ```
3.  **Start the Python HTTP server** from the project root:
    ```bash
    python -m http.server 8000
    ```
4.  **Open your web browser** and go to `http://localhost:8000/index.html` (or just `http://localhost:8000/`).

## Deployment

This application is deployed using **GitHub Pages**.
- The site is served from the `main` branch of the `Dukes0O/IRC-899-pages` repository.
- Content is served from the root of the repository.
- Relative paths are used for all assets (CSS, JS, images, data files) to ensure compatibility with GitHub Pages hosting.

## Development Notes

- The application relies heavily on JavaScript for dynamic content rendering and navigation.
- Key JavaScript modules include:
    - `js/navigation.js`: Handles routing and loading page content and scripts.
    - `js/key_provisions.js`: Manages fetching and rendering content for the Key Provisions page, including Mermaid diagrams and Chart.js charts.
    - `js/glossary-links.js`: Provides the global `window.applyGlossaryTooltips` function for adding interactive glossary term definitions.
- Ensure consistency in URL hash strings (e.g., `#key-provisions`) across routing definitions, link generation, and conditional script execution.
- When fetching data (e.g., JSON files), use paths relative to `index.html` (e.g., `data/filename.json`) to ensure they work both locally and on GitHub Pages. Avoid root-relative paths (e.g., `/data/filename.json`) or complex `../` paths where simpler relative paths suffice.

## Recent Accomplishments (June 2025)

- **GitHub Pages Deployment:**
  - Successfully deployed the entire site to GitHub Pages.
  - Resolved various pathing issues for JSON data files (`home_content.json`, `glossary.json`) to ensure correct loading on the live site.
  - Configured the repository for GitHub Pages deployment from the `main` branch root.

- **Key Provisions Page Enhancements:**
  - Replaced a static Mermaid diagram with a dynamic Chart.js bar chart for "Applicable Percentage Points."
  - Restructured `key_provisions.json` for deeply nested content.
  - Updated `key_provisions.js` for recursive rendering of nested content.
  - Adjusted Chart.js styles and reorganized content sections.
  - Fixed JSON syntax errors and restored a Mermaid flowchart.

- **Impact Estimator Flowchart Implementation:**
  - Created `data/impact_estimator.json` and `js/impact_estimator.js`.
  - Integrated the page into site navigation.

## Contributing

(To be defined - for now, focus on local development and testing.)
