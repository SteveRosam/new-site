# Configuration

Customize your experience with our platform's flexible configuration options.

## Basic Configuration

Create a `config.yaml` file in your project root with the following structure:

```yaml
# Core Settings
site_name: My Awesome Site
description: A description of your site
theme: 
  name: material
  palette:
    primary: indigo
    accent: blue

# Features
features:
  - navigation.tabs
  - navigation.sections
  - search.suggest
  - content.code.copy

# Extensions
markdown_extensions:
  - pymdownx.highlight
  - pymdownx.superfences
  - pymdownx.emoji
```

## Environment Variables

You can also configure the application using environment variables:

```bash
export API_KEY=your_api_key
export ENVIRONMENT=production
export DEBUG=false
```

## Configuration Options

### Theme Settings

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `primary` | String | `indigo` | Primary color theme |
| `accent` | String | `blue` | Accent color |
| `font` | Object | `{ text: Roboto, code: Roboto Mono }` | Font settings |

### Features

Enable or disable specific features:

- `navigation.tabs`: Show tabs in the navigation
- `search.suggest`: Enable search suggestions
- `content.code.copy`: Add copy button to code blocks

## Advanced Configuration

For more advanced configuration options, please refer to the [MkDocs documentation](https://www.mkdocs.org/user-guide/configuration/).

## Next Steps

- [Learn about writing documentation](../guide/writing.md)
- [Explore the API reference](../reference/commands.md)
- [Customize the styling](../guide/styling.md)
