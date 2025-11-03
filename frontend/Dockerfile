# Build
FROM node:20 As build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

#nginx 
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
