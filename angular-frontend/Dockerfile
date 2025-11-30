FROM node:20-alpine As Build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx:alpine
WORKDIR /usr/share/nginx/html
COPY --from=Build /app/dist/ .
EXPOSE 80

