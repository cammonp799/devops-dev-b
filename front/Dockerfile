#  image Node.js officielle
FROM node:18.18 as build

# Création et définition du répertoire de travail
WORKDIR /app

# Copie du package.json et installation des dépendances
COPY package*.json ./
RUN npm install

# Copier le reste du code
COPY . .

RUN npm run build

FROM nginx:stable
COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80