FROM node:20 AS builder
WORKDIR /app
COPY . .
RUN npm install && npm run build
FROM nginx:alpine
COPY --from=builder /app/dist/classrooms/browser /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf
