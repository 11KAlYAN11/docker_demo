# Stage 1 Build
FROM nginx:alpine AS builder
WORKDIR /usr/share/nginx/html
COPY . .

# Stage 2 Minimal Serving
FROM nginx:alpine
COPY --from=builder /usr/share/nginx/html /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"] 