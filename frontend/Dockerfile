FROM nginx:alpine AS builder

WORKDIR /usr/share/nginx/html

COPY . .

COPY nginx.conf /etc/nginx/conf.d/default.conf

FROM nginx:alpine

WORKDIR /usr/share/nginx/html

COPY --from=builder /usr/share/nginx/html ./

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

