# Étape de build avec Node.js
FROM node:18.18 as build

# Définir le répertoire de travail
WORKDIR /app


ARG VITE_API_URL=http://localhost:3000

ENV VITE_API_URL=${VITE_API_URL}


COPY package*.json ./
RUN npm install


COPY . .


RUN npm run build


FROM nginx:stable
COPY --from=build /app/dist /usr/share/nginx/html


EXPOSE 80

