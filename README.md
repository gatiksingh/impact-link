# ImpactLink | Intelligent Volunteer & Crisis Coordination

**ImpactLink** is a centralized web platform designed to bridge the gap between local NGOs and skilled volunteers during emergencies. While traditional coordination often suffers from fragmented communication and manual delays, ImpactLink uses **Predictive Urgency Triage** to match and route the right volunteers to the most critical needs in real-time.

---

## 🚀 Key Features

* **Predictive Urgency Triage**: A Machine Learning engine (XGBoost) combined with an Urgency Matrix ranks volunteers based on skill relevance and geospatial proximity.
* **Volunteer Portal**: A personalized dashboard where volunteers can view high-priority emergencies, accept tasks, and manage their status.
* **NGO Dashboard**: An intuitive interface for crisis centers to broadcast requirements, assign urgency levels, and track task resolution.
* **Live Needs Heatmap**: A real-time geospatial visualization of community needs, highlighting critical zones and emergency density.
* **Automated Synchronization**: Real-time updates lock volunteer availability when engaged and remove completed tasks to keep the platform data current.

---

## 🛠️ Technology Stack

| Category | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend** | HTML5, CSS3, Vanilla JS | Lightweight glassmorphic UI with native Fetch API. |
| **Backend** | FastAPI (Python) | High-performance asynchronous REST API engine. |
| **Intelligence** | XGBoost, Scikit-learn | Powers the `volunteer_matcher` predictive model. |
| **Geospatial** | Leaflet.js, Geopy | Renders live heatmaps and calculates geodesic distances. |
| **Hosting** | Railway & Netlify | Backend and frontend deployment platforms. |

---

## 🏗️ System Architecture

The system operates in a seamless, automated loop from crisis signal to resolution:

1.  **Signal (NGO Input)**: NGOs post requirements; the system captures location and timestamps instantly.
2.  **Match (ML Engine)**: The backend ranks optimal matches based on the `volunteer_matcher.pkl` model.
3.  **Engage (Live Sync)**: Volunteers accept tasks, triggering a dual-state status update ("Engaged" / "In Progress").
4.  **Resolve (Cleanup)**: Once finished, the task is archived, and the volunteer returns to "Available" status.

---

## ⚙️ Installation & Setup

### Prerequisites
* Python 3.8+
* FastAPI & Uvicorn
* Required Libraries: `pandas`, `joblib`, `geopy`, `xgboost`, `scikit-learn`

### Backend Setup
1. Clone the repository and navigate to the project folder.
2. Install dependencies:
   ```bash
   pip install fastapi uvicorn pandas joblib geopy xgboost scikit-learn
