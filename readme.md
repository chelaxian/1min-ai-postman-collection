# 1min.ai API Postman Collection

This Postman collection provides a comprehensive set of API endpoints for interacting with the 1min.ai API services.

## Getting Started

1. Import the collection into Postman
2. Set up your environment variable:
   - `api_key`: Your 1min.ai API key

## Available Endpoints

### Chat Features

#### Chat with AI
- **Method:** POST
- **Endpoint:** `https://api.1min.ai/api/features`
- **Headers:**
  - Content-Type: application/json
  - API-KEY: {{api_key}}
- **Query Parameters:**
  - isStreaming: true/false
- **Request Body:**
```json
{
    "type": "CHAT_WITH_AI",
    "model": "gpt-4o-mini",
    "promptObject": {
        "prompt": "Your message here"
    }
}
```

#### Chat with Image
- **Method:** POST
- **Endpoint:** `https://api.1min.ai/api/features`
- **Headers:**
  - Content-Type: application/json
  - API-KEY: {{api_key}}
- **Query Parameters:**
  - isStreaming: true/false
- **Request Body:**
```json
{
    "type": "CHAT_WITH_IMAGE",
    "model": "gpt-4o-mini",
    "promptObject": {
        "prompt": "Your question about the image",
        "imageList": ["image_key"]
    }
}
```

### Image Features

#### Generate Image
- **Method:** POST
- **Endpoint:** `https://api.1min.ai/api/features`
- **Headers:**
  - Content-Type: application/json
  - API-KEY: {{api_key}}
- **Request Body:**
```json
{
    "type": "IMAGE_GENERATOR",
    "model": "midjourney",
    "promptObject": {
        "prompt": "Your image description",
        "num_outputs": 1,
        "aspect_ratio": "1:1"
    }
}
```

### Asset Management

#### Upload Asset
- **Method:** POST
- **Endpoint:** `https://api.1min.ai/api/assets`
- **Headers:**
  - API-KEY: {{api_key}}
- **Body:** form-data
  - Key: asset
  - Value: [file]

## Authentication

All requests require an API key to be sent in the header as `API-KEY`. Set this up in your Postman environment variables for easier management.

## Response Format

The API returns JSON responses. For streaming endpoints (where `isStreaming=true`), the response will be delivered as a stream of data.

## Error Handling

Ensure your API key is properly set in the environment variables. If you encounter any errors, verify your request format and authentication headers. 
