# Usa un'immagine di Python come base
FROM python:3.12.0-slim

# Imposta il work directory nell'applicazione
WORKDIR /app

# Copia il file dei requisiti e installa le dipendenze
COPY requirements.txt /app
COPY Spotify.py /app
COPY templates /app/templates
COPY static /app/static
COPY .env /app

RUN pip install --no-cache-dir -r requirements.txt
RUN python3 -m textblob.download_corpora

# Esponi la porta su cui il server Flask ascolterà le richieste
EXPOSE 8000

# Comando per avviare il server Flask
CMD ["python", "Spotify.py"]
