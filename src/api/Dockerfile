FROM ghcr.io/astral-sh/uv:python3.12-bookworm-slim

WORKDIR /app

COPY src/api/requirements.txt .
RUN uv pip install --system --no-cache -r requirements.txt

COPY models/model.joblib .
COPY src/api/main.py .

EXPOSE 8000
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
