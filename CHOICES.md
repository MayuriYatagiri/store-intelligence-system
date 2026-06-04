# CHOICES.md — Engineering Trade-Offs & Schema Architecture

## 1. Model Selection & Technology Stack
* **Framework:** Chosen FastAPI over Django/Flask due to its native ASGI asynchronous support, automated OpenAPI documentation generation, and superior execution speeds matching Node.js/Go performance.
* **Data Layer:** Utilized a streaming chunked layout for JSONL processing combined with Pandas vectorization for CSV transactions to keep spatial tracking algorithms scalable.

## 2. Schema Design & Data Fusion Strategy
* **Temporal Tracking:** Customer tracking links corresponding entry/exit vectors dynamically using unique identity hashes (`id_token`).
* **Staff Filtering Logic:** Implements an absolute isolation boolean (`is_staff`) to strip operational employee foot traffic out of customer conversion metrics, preventing synthetic inflation of the store's Conversion Rate.
* **Spatial Processing:** Maps $x,y$ coordinate cartesian points strictly inside bounded zone identifiers (`zone_entered`) to preserve computation memory while maintaining layout precision.
