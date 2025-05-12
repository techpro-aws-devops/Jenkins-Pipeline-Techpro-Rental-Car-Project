FROM python:3.9-slim
WORKDIR /app
RUN pip install --upgrade pip
COPY ./App/requirements.txt .  # /app/requirements.txt
RUN pip install -r requirements.txt
COPY ./App/ .                  # Tüm dosyaları /app'e kopyala (App klasörünü değil)
CMD ["gunicorn", "-w", "2", "-b", "0.0.0.0:8000", "--timeout", "30", "wsgi:app"]