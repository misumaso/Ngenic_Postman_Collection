# 🔧 Ngenic Postman Collection

This repository contains a complete **Postman Collection** and **Environment** setup for interacting with the **Ngenic API (v3)**.  
It is designed to simplify testing, development, and integration with Ngenic’s smart energy management services.

---

## 📦 Contents

| File | Description |
|------|--------------|
| `Ngenic.postman_collection.json` | The API collection containing predefined endpoints, methods, headers, and sample bodies. |
| `Ngenic.postman_environment.json` | The environment configuration containing key variables such as `api_key`, `tuneUuid`, and base URLs. |

---

## 🚀 Getting Started

### 1. Import into Postman

1. Open **Postman**.  
2. Click **Import** (top left corner).  
3. Choose the **Files** tab and select:  
   - `Ngenic.postman_collection.json`  
   - `Ngenic.postman_environment.json`  
4. After importing, both should appear in your workspace.

---

### 2. Configure Environment Variables

Before sending requests, make sure your environment variables are properly configured:

| Variable | Example | Description |
|-----------|----------|-------------|
| `api_key` | `your_api_token_here` | Your Ngenic API token used for authentication (Bearer Token). |
| `tuneUuid` | `123e4567-e89b-12d3-a456-426614174000` | The UUID of the Tune you want to interact with. |
| `nodeUuid` | `abcdef12-3456-7890-abcd-ef1234567890` | The UUID of a specific node (optional). |
| `roomUuid` | `fedcba98-7654-3210-fedc-ba9876543210` | UUID of a room (optional). |
| `userAccountUuid` | `user-uuid` | Identifier for a user account (optional). |

> ⚠️ **Do not commit environment files containing API keys or tokens to source control.**

---

### 3. Authentication

All requests use **Bearer Token authentication** via the `api_key` environment variable.  
Ensure your token is valid; otherwise, requests will return `401 Unauthorized`.

If your token is expired, retrieve a new one from your Ngenic account or API management console.

---

### 4. API Overview

This collection covers a broad range of Ngenic API endpoints:

| Category | Description |
|-----------|-------------|
| **Tunes** | List all Tunes or fetch details for a specific Tune. |
| **ControlSettings** | Get or update Tune control settings (e.g., spot price factor, control mode). |
| **Node** | List all gateway nodes or fetch details for a specific node. |
| **Measurements** | Retrieve measurement data for nodes (historical, latest, or by type). |
| **Status** | Check node status for a Tune. |
| **TuneUsers** | Manage or list Tune users. |
| **Room** | Retrieve or modify room information and temperature targets. |
| **SetpointSchedule** | Manage heating/cooling schedules for Tunes. |
| **UserAccount** | Get or update user account details. |

Each request is pre-configured with required parameters, URL templates, and example request bodies.

---

### 5. Example Requests

#### List all Tunes
```http
GET https://app.ngenic.se/api/v3/tunes
Authorization: Bearer {{api_key}}
