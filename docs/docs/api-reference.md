# API Reference

This document provides detailed information about the SiMuFlow API, including available endpoints, request/response formats, and authentication methods.

## Base URL

All API requests should be made to:
```
https://api.simuflow.com/v1
```

## Authentication

### API Keys

1. Generate an API key from your [Account Settings](https://app.simuflow.com/settings/api-keys)
2. Include the API key in the `Authorization` header of your requests:
   ```
   Authorization: Bearer YOUR_API_KEY
   ```

## Rate Limiting

- **Free Tier**: 100 requests per hour
- **Pro Tier**: 1,000 requests per hour
- **Enterprise**: Custom limits available

## Endpoints

### Projects

#### List Projects
```http
GET /projects
```

**Response**
```json
{
  "data": [
    {
      "id": "proj_123",
      "name": "Thermal Analysis",
      "description": "Quarterly thermal simulations",
      "created_at": "2025-01-15T10:30:00Z"
    }
  ]
}
```

#### Create Project
```http
POST /projects
Content-Type: application/json

{
  "name": "New Project",
  "description": "Project description"
}
```

### Files

#### Upload File
```http
POST /files
Content-Type: multipart/form-data
```

**Form Data**
- `file`: The file to upload
- `project_id`: (Optional) Associate with a project
- `metadata`: (Optional) JSON string of metadata

#### Get File
```http
GET /files/{file_id}
```

## Webhooks

### Events
- `file.uploaded` - When a new file is uploaded
- `simulation.completed` - When a simulation completes
- `job.failed` - When a job fails

### Example Webhook Payload
```json
{
  "event": "simulation.completed",
  "data": {
    "id": "sim_12345",
    "status": "completed",
    "project_id": "proj_123",
    "created_at": "2025-06-20T12:34:56Z",
    "completed_at": "2025-06-20T12:45:30Z"
  }
}
```

## Error Handling

### Error Response Format
```json
{
  "error": {
    "code": "invalid_request",
    "message": "Invalid request parameters",
    "details": {
      "field": "name",
      "issue": "required"
    }
  }
}
```

### Common Error Codes

| Status Code | Error Code           | Description                          |
|-------------|----------------------|--------------------------------------|
| 400         | `invalid_request`    | Invalid request parameters           |
| 401         | `unauthorized`       | Invalid or missing API key          |
| 403         | `forbidden`          | Insufficient permissions            |
| 404         | `not_found`          | Resource not found                  |
| 429         | `rate_limit_exceeded`| Too many requests                   |
| 500         | `server_error`       | Internal server error               |


## SDKs

### Python
```python
import simuflow

# Initialize client
client = simuflow.Client(api_key="YOUR_API_KEY")

# List projects
projects = client.projects.list()

# Upload a file
with open("results.csv", "rb") as f:
    file = client.files.upload(f, project_id="proj_123")
```

### Node.js
```javascript
const { Simuflow } = require('simuflow');

const client = new Simuflow({
  apiKey: 'YOUR_API_KEY'
});

// List projects
const projects = await client.projects.list();
```
