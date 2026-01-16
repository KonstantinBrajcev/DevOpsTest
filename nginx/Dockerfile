FROM nginx:1.25-alpine

# Копируем конфигурацию
COPY nginx.conf /etc/nginx/nginx.conf

# Удаляем дефолтную конфигурацию
RUN rm /etc/nginx/conf.d/default.conf

EXPOSE 80