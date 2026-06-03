# Purplle Store Intelligence Engine 📊🛒

An end-to-end data analytics and business intelligence platform designed for modern physical retail optimization. Built using the high-performance **FastAPI** framework, this system bridges the gap between physical retail operations and digital analytics by dynamically fusing real-time **AI-powered CCTV computer vision event logs** with historical **Point-of-Sale (POS) transaction records**.

## 🚀 Core Features

### 1. Store Overview & Conversion Analytics
* **True Customer Isolation:** Filters out recognized staff members (`is_staff`) to isolate genuine customer foot traffic.
* **Dwell Time Tracking:** Maps unique tracking hashes (`id_token`) between corresponding entry and exit timestamps to compute exact average customer dwell times.
* **Conversion Rate Analytics:** Cross-references active floor traffic against unique completed purchase totals (`order_id`) from POS data to calculate the store's conversion efficiency.

### 2. Queue Performance Diagnostics
* **Friction Monitoring:** Monitors tracking events inside checkout zones categorized as `queue_completed` or `queue_abandoned`.
* **Bottleneck Metrics:** Automatically calculates average wait times, registers peak bottleneck delay durations, and tracks the **queue abandonment rate** to flag counter under-staffing.

### 3. Spatial Density & Layout Heatmapping
* **Hotspot Mapping:** Leverages spatial coordinate data ($x, y$ cartesian tracking fields) triggered during `zone_entered` events.
* **Layout Optimization:** Groups tracking densities by localized section names (e.g., specific cosmetic or apparel aisles) to eliminate floor layout dead-zones.

---

## 🛠️ Tech Stack
* **Backend Framework:** FastAPI (Asynchronous Python ASGI)
* **Data Processing Pipeline:** Pandas, NumPy, and JSON Stream Parsers
* **Interface Layer:** Interactive OpenAPI / Swagger Specification (`/docs`)

---

## 💻 Instructions to Run Locally

### Prerequisites
Ensure your datasets are placed exactly within a `data` directory at your root path:
* `C:\store-intelligence-system\data\POS - sample transactions.csv`
* `C:\store-intelligence-system\data\sample_events.jsonl`

### Execution Steps
1. Navigate into the project root directory:
   ```powershell
   cd c:\store-intelligence-system
   
### Activate your local virtual environment:
   
   .\venv\Scripts\activate

 
### Boot up the FastAPI production server using Uvicorn:
      python -m uvicorn app.app.app.main:app --reload



**Open your web browser and navigate to the interactive dashboard to test endpoints live:**
👉 http://127.0.0.1:8000/docs
