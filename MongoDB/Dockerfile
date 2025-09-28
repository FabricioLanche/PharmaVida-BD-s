# MongoDB Dockerfile
FROM mongo:7.0

# Establecer el directorio de trabajo
WORKDIR /data/db

# Exponer el puerto por defecto de MongoDB
EXPOSE 27017

# Comando por defecto para ejecutar MongoDB
CMD ["mongod", "--bind_ip_all"]