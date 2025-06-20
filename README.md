# SimuFlow Documentation

This repository contains the source code for the SimuFlow documentation website, built with MkDocs and the Material for MkDocs theme.

## Getting Started

### Prerequisites

- Python 3.8 or higher
- pip (Python package installer)

### Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/SteveRosam/new-site.git
   cd new-site
   ```

2. Create and activate a virtual environment (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: .\venv\Scripts\activate
   ```

3. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

4. Start the development server:
   ```bash
   mkdocs serve
   ```
   The site will be available at http://127.0.0.1:8000/

## Building the Site

To build the site locally:

```bash
mkdocs build
```

The built files will be in the `site/` directory.

## Deployment

This site is automatically deployed to GitHub Pages via GitHub Actions. The workflow is triggered on every push to the `master` branch.

### Manual Deployment

If you need to deploy manually:

1. Build the site:
   ```bash
   mkdocs build --clean
   ```

2. Deploy to GitHub Pages:
   ```bash
   mkdocs gh-deploy --force
   ```

## Project Structure

- `docs/` - Source files for the documentation
  - `img/` - Image assets
  - `styles/` - Custom CSS styles
- `overrides/` - MkDocs template overrides
- `.github/workflows/` - GitHub Actions workflows
- `mkdocs.yml` - MkDocs configuration file

## Customization

### Adding a New Page

1. Create a new Markdown file in the `docs/` directory or a subdirectory
2. Add the page to the navigation in `mkdocs.yml`

### Styling

Custom CSS can be added to `docs/styles/extra.css`.

## License

This project is proprietary and confidential.
