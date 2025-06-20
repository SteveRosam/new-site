# Configuration

This guide covers all configuration options available in SiMuFlow, including both web interface settings and configuration files.

## Web Interface Settings

### User Preferences

Access your user preferences by clicking on your profile picture in the top-right corner and selecting "Preferences".

#### General
- **Language**: Set your preferred language
- **Time Zone**: Configure your local time zone
- **Theme**: Choose between light, dark, or system default

#### Notifications
- **Email Notifications**: Enable/disable email notifications
- **In-App Notifications**: Configure which events trigger notifications
- **Daily Digest**: Receive a daily summary of activity

### Project Settings

Each project has its own settings that can be configured by project administrators.

#### General
- **Project Name**: Display name for the project
- **Description**: Detailed description of the project
- **Visibility**: Public, Private, or Organization

#### Permissions
- **Team Members**: Manage who has access
- **Roles**: Define custom roles and permissions

## Configuration Files

### Project Configuration (`.simuflow/config.yml`)

```yaml
# Project configuration
project:
  name: "My Project"
  description: "Project description"
  version: "1.0.0"

# Simulation settings
simulation:
  solver:
    type: "thermal"
    precision: 1e-6
    max_iterations: 1000
  
  # Output settings
  output:
    format: "csv"
    directory: "./results"
    save_interval: 100

# Data management
data:
  inputs:
    - name: "geometry"
      type: "step"
      required: true
    - name: "material_properties"
      type: "json"
      default: "default_materials.json"
  
  outputs:
    - name: "temperature_field"
      type: "vtu"
    - name: "summary"
      type: "csv"

# Execution environment
environment:
  docker_image: "simuflow/solver:latest"
  resources:
    cpus: 4
    memory_gb: 16
    gpu: false

# Integration settings
integrations:
  git:
    enabled: true
    branch: "main"
  
  webhooks:
    - url: "https://api.example.com/webhook"
      events:
        - "simulation.completed"
        - "simulation.failed"

# Custom parameters
parameters:
  temperature:
    type: "number"
    default: 293.15
    min: 0
    max: 1000
    unit: "K"
    description: "Initial temperature"

  pressure:
    type: "number"
    default: 101325
    unit: "Pa"
    description: "Atmospheric pressure"
```

### Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `SIMUFLOW_API_KEY` | Your API key for authentication | - |
| `SIMUFLOW_API_URL` | Base URL for API requests | `https://api.simuflow.com/v1` |
| `SIMUFLOW_CACHE_DIR` | Directory for cached data | `~/.simuflow/cache` |
| `SIMUFLOW_DEBUG` | Enable debug logging | `false` |

## CLI Configuration

The SiMuFlow CLI can be configured using a configuration file at `~/.simuflow/config` or via environment variables.

### Example CLI Config

```ini
[default]
api_key = your_api_key_here
api_url = https://api.simuflow.com/v1
output = json
color = auto

[projects]
default = proj_12345

[features]
preview = true
experimental = false
```

## Best Practices

1. **Version Control**
   - Commit your configuration files to version control
   - Use environment variables for sensitive information
   - Document all required parameters

2. **Performance**
   - Adjust solver settings based on your hardware
   - Use appropriate output formats for your data
   - Consider using checkpoints for long-running simulations

3. **Security**
   - Never commit API keys or credentials
   - Use the principle of least privilege for API keys
   - Regularly rotate your API keys

## Troubleshooting

### Common Issues

1. **Configuration Errors**
   - Check for YAML syntax errors
   - Verify all required fields are present
   - Ensure correct data types for all values

2. **Connection Issues**
   - Verify your API key is correct
   - Check your internet connection
   - Verify the API URL is correct

3. **Performance Problems**
   - Check system resource usage
   - Review simulation parameters
   - Consider simplifying your model

## Getting Help

For additional assistance, please refer to:
- [Documentation](https://docs.simuflow.com)
- [Community Forum](https://community.simuflow.com)
- [Support](mailto:support@simuflow.com)
