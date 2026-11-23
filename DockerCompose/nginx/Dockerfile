FROM nginx:alpine

# Rimuove la configurazione di default e copia la tua
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 8080