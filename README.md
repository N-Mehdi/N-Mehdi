# Mehdi Neji

Data science and data engineering student at ENSAI, Rennes.

---

# Projects

### ML & Deep Learning

**[receipt-vlm](https://github.com/N-Mehdi/receipt-vlm)** - LLM fine-tuning for invoices extraction with VLM
Small vision-language models read documents well but do not follow a fixed output schema. I fine-tuned Qwen3-VL-2B with QLoRA (4-bit NF4, 0.8% trainable parameters) on a single T4, using CORD and 1,000 synthetic French invoices with consistent labels. Against the base model: field F1 from 0.35 to 0.83 on CORD, exact match from 0.13 to 0.63 on invoices, and 0.54 on unseen layouts. Served through a Dockerized FastAPI service with a [demo on Hugging Face](https://huggingface.co/spaces/N-Mehdi/receipt-vlm). `PyTorch` `Qwen3-VL` `QLoRA` `Hugging Face` `FastAPI` `Docker` `W&B`

<br>

**[Data_Battle-Dataverse](https://github.com/N-Mehdi/Data_Battle-Dataverse)** - predicting the end of thunderstorm alerts around French airports (Data Battle IA PAU 2026, ranked 4/80)  
Lightning alerts halt all outdoor airport activity, and operators lift them manually, often long after the storm has passed. We built a pipeline on 230K lightning strikes from the Météorage network that computes 74 spatio-temporal features at each silent instant (strike counts, distances, amplitudes, 5/10/20 min sliding windows, inter-arrival times) and compared logistic regression, random forest and XGBoost. The decision threshold (θ = 0.91) maximizes the time saved under a missed-lightning constraint: 216 hours of alerts lifted earlier than the standard rule (30 minutes after the last thunder strike), with 2% of strikes missed. Served through a FastAPI backend for batch predictions on CSV and Parquet files. `Python` `pandas` `scikit-learn` `XGBoost` `FastAPI`
<br>
### Software engineering

**[ENSAI-2A-S2-ConceptionLog](https://github.com/morgannder/ENSAI-2A-S2-ConceptionLog)** - Rocket League player statistics and match analysis platform (ENSAI team project)  
Our team of four collected about 70,000 matches through the Ballchasing API (rate-limited to 2 requests/s) into a SQLite database, and built a layered FastAPI backend (24 endpoints) with a React/Vite frontend. A GitHub Actions CI/CD pipeline builds the backend and frontend Docker images, pushes them to Docker Hub and deploys them on Kubernetes (SSPCloud), with a [live version online](http://rocketclstats.api.kub.sspcloud.fr/). Backed by 254 unit tests (pytest). `Python` `FastAPI` `SQLite` `React` `Docker` `Kubernetes` `GitHub Actions` `uv` `Ruff`

**[bar-management-API-REST](https://github.com/N-Mehdi/bar-management-API-REST)** - cocktail and bar inventory management REST API (academic project)  
Home bartenders need to know which cocktails they can make from what they actually have. Built a layered FastAPI + PostgreSQL backend (API, service and DAO layers) with JWT authentication, seeded from TheCocktailDB public API: 43 endpoints covering public and private recipes, ingredient stock, shopping lists, favorites, reviews and recommendations of cocktails makeable from the current stock, with automatic unit conversion. `Python` `FastAPI` `PostgreSQL` `pytest` `uv` `Ruff`

## Currently

Final year at ENSAI, looking for a 6-month internship.
