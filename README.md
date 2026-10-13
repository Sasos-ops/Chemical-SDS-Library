# Chemical-SDS-Library
Chemical inventory repository containing Safety Data Sheets (SDS), Material Safety Data Sheets (MSDS), and Technical Data Sheets (TDS) for operational and maintenance chemicals.

## GitHub Pages Library & Viewer
Access the online searchable chemical library and interactive document viewer:
- **Site URL:** [https://sasos-ops.github.io/Chemical-SDS-Library/](https://sasos-ops.github.io/Chemical-SDS-Library/)

## Repository Structure
- `docs/`: GitHub Pages root directory.
  - `docs/index.html`: Searchable chemical library home page with filtering by name, type, and category.
  - `docs/viewer.html`: In-site document viewer embedding the PDF with document metadata, quick actions (open new tab, download, print), and category navigation.
  - `docs/catalog.js`: Shared document catalog and metadata definitions used by both the index and viewer.
  - `docs/pdfs/`: PDF document storage containing all SDS, MSDS, and TDS files served directly by GitHub Pages.
  - `docs/.nojekyll`: Disables Jekyll static site processing on GitHub Pages so all static assets and subdirectories are served directly.

