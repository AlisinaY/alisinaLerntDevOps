# Build-Phase
FROM node:18 AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Serve-Phase (NGINX)
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html

# Optional: NGINX config anpassen (damit /api weitergeleitet wird, falls nötig)
EXPOSE 80
