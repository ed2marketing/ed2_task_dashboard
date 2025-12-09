<p align="center">
  <img src="assets/banner.png" alt="Ed2-Marketing Logo" width="100%"/>
</p>

<h1 align="center">Ed2-Marketing Task Dashboard</h1>
<p align="center"><b>Official Task Management System for Ed2-Marketing Account Intel Team</b></p>

---

**Ed2-Marketing Task Dashboard** is a dynamic client task management interface designed for the Ed2-Marketing Account Intel team. It streamlines the process of tracking meeting tasks, assigning owners, and syncing updates via n8n webhooks.

## 🚀 Key Features

- **Dynamic Data Loading**: Automatically initializes the dashboard with meeting details and task lists parsed directly from URL parameters.
- **Task Management**:
  - Add new tasks with assigned owners.
  - Delete completed or irrelevant tasks.
  - Edit task names and owners inline.
- **Meeting Context**:
  - Displays the specific meeting title.
  - Allows selection of meeting types (Internal, External, Updates).
- **Real-time Sync**: "Save All Changes" button pushes the current state to an n8n webhook for backend processing.
- **Responsive UI**: Clean, modern interface built with vanilla CSS and JavaScript.

## 🛠️ Technology Stack

| Layer | Technology |
|--------|-----------|
| Frontend | HTML5, CSS3, JavaScript |
| Fonts | Google Fonts (Inter) |
| Backend Sync | n8n Webhook |
| Hosting | Local / Cloud |

---
## 📖 Usage

### 1. Opening the Dashboard
The dashboard is designed to be opened with data passed in the URL. Open `index.html` in your browser.

### 2. URL Parameter Format
The application expects a `data` query parameter containing a URL-encoded JSON object.

**Structure:**
```json
{
  "meeting_title": "Weekly Sync",
  "tasks": [
    { "task": "Review Q3 Report", "owner": "john" },
    { "task": "Update Client List", "owner": "Mike" }
  ]
}
```

### 3. Saving Changes
Clicking the **Save All Changes** button sends a POST request to the configured n8n endpoint with the updated task list and meeting metadata.

## 📂 Project Structure

- `index.html`: Main application structure.
- `script.js`: Logic for parsing URL data, managing state, and handling API requests.
- `style.css`: Styling for the dashboard, including responsive design and animations.
- `assets/`: Directory for images and static resources.

## 🔗 API Integration

The dashboard communicates with the following endpoint:
- **URL**: `https://Ed2-Marketing-n8n-cloud-url/webhook/v1/client-tasks`
- **Method**: `POST`
- **Payload**:
  ```json
  {
    "meeting_title": "...",
    "meetingType": "Internal",
    "tasks": [ ... ]
  }
  ```
