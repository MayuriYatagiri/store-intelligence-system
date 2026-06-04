# DESIGN.md — System Architecture & Design Decisions

## 1. Architectural Overview
The Store Intelligence Engine is designed as a decoupled, high-performance asynchronous analytics system using FastAPI. The platform processes high-velocity computer vision streams alongside structured POS transactional logs to deliver immediate business intelligence.

## 2. AI-Assisted Decisions
Throughout the development cycle, AI collaboration was leveraged to ensure rapid prototyping and production-readiness:
* **Algorithmic Safety Margins:** AI was utilized to draft defensive data-parsing loops inside `engine.py`. This ensures that missing attributes or varied naming schemas (e.g., `store_id` vs `store_code`) are automatically normalized without crashing the server.
* **Asynchronous Lifespans:** Implemented FastAPI's modern startup contexts to handle dataset memory-mapping cleanly on server boot, ensuring zero latency during active API route queries.
