FROM python:3.12-slim
WORKDIR /repo

RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/*
RUN git clone https://github.com/mmenapace/SomeBankingApp.git .

WORKDIR /repo/backend
RUN pip install --no-cache-dir -r requirements.txt fastapi

ENTRYPOINT ["python", "-m", "uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]