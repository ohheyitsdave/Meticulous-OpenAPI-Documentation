# Meticulous Backend API Guide

A beginner-friendly guide to exploring and using the Meticulous espresso machine API.

## Table of Contents

- [What is this API?](#what-is-this-api)
- [Getting Started](#getting-started)
- [Using an API Client](#using-an-API-client)
- [Exploring Endpoints](#exploring-endpoints)
- [API Tools](#api-tools)

## What is this API?

The Meticulous Backend API allows you to control and interact with your espresso machine. You can:

- Control machine actions (start, stop, purge, etc.)
- Manage espresso profiles
- View shot history and statistics
- Manage sound themes
- Update system settings

## Getting Started

### Prerequisites

- A Meticulous espresso machine
- Network access to the machine
- Basic understanding of HTTP requests (GET, POST, etc.)

### Finding Your Machine

Your machine can be accessed via:

1. **Localhost** (if running a development environment): `http://localhost:8080`
3. **IP Address**: `http://[machine-ip]` or `http://Meticulous[identifier]`

## Accessing the API

All API endpoints are prefixed with `/api/v1/`. For example:

- `http://[machine-ip]/api/v1/machine` - Get machine information
- `http://[machine-ip]/api/v1/profile/list` - List profiles
- `http://[machine-ip]/api/v1/history` - Get shot history

## Using an API Client

### Step 1: Download API Client
* https://www.postman.com/
* https://www.usebruno.com/
* https://yaak.app/

### Step 2: Import the OpenAPI Specification
1. Click the **"Import"** button
2. Select **"File"** tab
3. Click **"Upload Files"** and select `openapi.json`
4. Click **"Import"**

**Result**: All API endpoints are now imported and organized by category

#### Step 3: Set Up Environment Variables

1. Click the **"Environments"** icon
2. Click **"+"** to create a new environment
3. Name it for example "PRODUCTION"
4. Add a variable:
   - **Variable**: `base_url`
   - **Value**: `http://[machine-ip]` or `http://Meticulous[identifier]`
5. Click **"Save"**
6. Select your environment from the dropdown

#### Step 4: Explore Endpoints

1. **Browse Collections**: You'll see folders like "Actions", "History", "Profiles", etc.
2. **Click an Endpoint**: For example, "Get machine information"
3. **View Details**: 
   - See the request URL (uses `{{base_url}}` variable)
   - See required/optional parameters
   - See example responses
4. **Click "Send"**: The request is sent and you see the response!

#### Step 5: Modify Requests

**Example: Update Settings**

1. Navigate to **Settings → Update settings**
2. Click on the request
3. Change method to **POST** (if not already)
4. Go to **Body** tab
5. Select **raw** and **JSON** format
6. Enter JSON:
   ```json
   {
     "hostname_override": "my-custom-hostname"
   }
   ```
7. Click **"Send"**
8. A response should be displayed

## Endpoint Categories

The API is organized into these categories:

| Category | Base Path | Description |
|----------|-----------|-------------|
| **Actions** | `/api/v1/action/` | Control machine actions |
| **History** | `/api/v1/history` | Shot history and statistics |
| **Machine** | `/api/v1/machine` | Machine information |
| **Profiles** | `/api/v1/profile/` | Espresso profile management |
| **Settings** | `/api/v1/settings` | System configuration |
| **Sounds** | `/api/v1/sounds/` | Sound themes |


Happy exploring! 🚀
