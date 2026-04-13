FROM python:3.10-slim AS builder

WORKDIR /app

COPY app/requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY app .

FROM python:3.10-slim

WORKDIR /app

COPY --from=builder /app /app

EXPOSE 5000

CMD ["python", "app.py"]