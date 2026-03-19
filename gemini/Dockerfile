FROM python:3.10-slim

WORKDIR /app

RUN apt-get update && apt-get install -y \
    build-essential \
    curl \
    git \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

EXPOSE 8889

CMD ["jupyter", "lab", "--ip='0.0.0.0'", "--port=8889", "--no-browser", "--allow-root", "--NotebookApp.token=''", "--NotebookApp.password=''"]
