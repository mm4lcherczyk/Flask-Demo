FROM python:3.12-slim
WORKDIR /app
COPY . /app
RUN apt-get update && apt-get install -y default-libmysqlclient-dev build-essential && pip install --no-cache-dir -r requirements.txt
EXPOSE 5000
CMD ["python", "app.py"]
