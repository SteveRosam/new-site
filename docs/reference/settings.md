# Settings Reference

This document provides a comprehensive reference for all available configuration settings in `mkdocs.yml`.

## Site Information

### `site_name`

- **Type**: String
- **Required**: Yes
- **Default**: None
- **Description**: The title of the site, displayed in the page title and navigation bar.

### `site_url`

- **Type**: String (URL)
- **Required**: No
- **Default**: None
- **Description**: The full URL where the site will be published.

### `site_description`

- **Type**: String
- **Required**: No
- **Default**: None
- **Description**: A brief description of your site, used for meta tags.

## Navigation

### `nav`

- **Type**: List of items
- **Required**: No
- **Default**: Auto-generated from the directory structure
- **Description**: Defines the structure of the navigation menu.

Example:
```yaml
nav:
  - Home: index.md
  - User Guide:
    - Installation: user-guide/installation.md
    - Configuration: user-guide/configuration.md
  - API Reference:
    - Commands: reference/commands.md
    - Settings: reference/settings.md
```

## Theme Configuration

### `theme`

- **Type**: Dictionary
- **Required**: No
- **Default**: `mkdocs`
- **Description**: Theme configuration.

Example:
```yaml
theme:
  name: material
  palette:
    - scheme: default
      primary: indigo
      accent: blue
    - scheme: slate
      primary: indigo
      accent: blue
  features:
    - navigation.tabs
    - navigation.sections
    - search.suggest
```

## Build Options

### `site_dir`

- **Type**: String (path)
- **Required**: No
- **Default**: `site`
- **Description**: The directory where the output HTML and other files are written to.

### `docs_dir`

- **Type**: String (path)
- **Required**: No
- **Default**: `docs`
- **Description**: The directory containing the documentation source markdown files.

## Extensions

### `markdown_extensions`

- **Type**: List of strings or dictionaries
- **Required**: No
- **Default**: See MkDocs documentation
- **Description**: List of Markdown extensions to use.

Example:
```yaml
markdown_extensions:
  - pymdownx.highlight
  - pymdownx.superfences
  - pymdownx.emoji:
      emoji_index: !!python/name:materialx.emoji.twemoji
      emoji_generator: !!python/name:materialx.emoji.to_svg
```

## Plugins

### `plugins`

- **Type**: List of strings or dictionaries
- **Required**: No
- **Default**: `['search']`
- **Description**: List of plugins to use.

Example:
```yaml
plugins:
  - search
  - minify:
      minify_html: true
      minify_js: true
      minify_css: true
```

## Advanced Configuration

### `extra`

- **Type**: Dictionary
- **Required**: No
- **Default**: `{}`
- **Description**: A set of configuration options that will be passed to the template.

Example:
```yaml
extra:
  social:
    - icon: fontawesome/brands/github
      link: https://github.com/your-username
    - icon: fontawesome/brands/twitter
      link: https://twitter.com/your-username
```

### `extra_css`

- **Type**: List of strings (file paths)
- **Required**: No
- **Default**: `[]`
- **Description**: A list of CSS files to include in the HTML header.

### `extra_javascript`

- **Type**: List of strings (file paths)
- **Required**: No
- **Default**: `[]`
- **Description**: A list of JavaScript files to include in the HTML footer.

## Complete Example

```yaml
site_name: My Awesome Site
site_url: https://example.com
site_author: Your Name
site_description: A description of your site

theme:
  name: material
  palette:
    - scheme: default
      primary: indigo
      accent: blue
    - scheme: slate
      primary: indigo
      accent: blue
  features:
    - navigation.tabs
    - navigation.sections
    - search.suggest

markdown_extensions:
  - pymdownx.highlight
  - pymdownx.superfences
  - pymdownx.emoji

plugins:
  - search
  - minify:
      minify_html: true
      minify_js: true
      minify_css: true

extra:
  social:
    - icon: fontawesome/brands/github
      link: https://github.com/your-username
    - icon: fontawesome/brands/twitter
      link: https://twitter.com/your-username

nav:
  - Home: index.md
  - User Guide:
    - Installation: user-guide/installation.md
    - Configuration: user-guide/configuration.md
  - API Reference:
    - Commands: reference/commands.md
    - Settings: reference/settings.md
```

## Next Steps

- [Getting Started](../getting-started/installation.md)
- [Configuration Guide](../getting-started/configuration.md)
- [Writing Documentation](../guide/writing.md)
