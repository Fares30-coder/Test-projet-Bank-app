# Utiliser une image Python officielle
FROM python:3.12

# Définir le répertoire de travail
WORKDIR /app

# Copier les fichiers nécessaires
COPY server.py .
COPY html/ html/
COPY db.sqlite db.sqlite
COPY requirements.txt requirements.txt

# Installer les dépendances + Gunicorn
RUN pip install --no-cache-dir -r requirements.txt
RUN pip install gunicorn

# Exposer le port 80
EXPOSE 80

# Lancer Flask avec Gunicorn sur le bon port
CMD ["gunicorn", "-b", "0.0.0.0:80", "server:app"]
