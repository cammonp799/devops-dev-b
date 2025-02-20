# Image Node.js officielle basée sur Alpine
FROM node:18.18-alpine

# Installer les outils de compilation
RUN apk add --no-cache make gcc g++ python3

# Définir le répertoire de travail
WORKDIR /app

# Copier uniquement les fichiers de configuration des dépendances
COPY package*.json ./

# Installer les dépendances (cela compile bcrypt pour Linux)
RUN npm install

# Forcer la recompilation de bcrypt (au cas où)
RUN npm rebuild bcrypt --update-binary

# Copier le reste du code
COPY . .

# Exposer le port
EXPOSE 3000

# Démarrer l'application
CMD [ "npm", "run", "start" ]
