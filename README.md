# PharmaVida - Base de Datos Multi-Motor

Este proyecto configura un entorno de desarrollo con múltiples bases de datos usando Docker y Docker Compose.

## Arquitectura

- **MongoDB**: Base de datos NoSQL orientada a documentos
- **MySQL**: Base de datos relacional tradicional
- **PostgreSQL**: Base de datos relacional avanzada
- **Adminer**: Interfaz web para administrar todas las bases de datos

## Instrucciones de Uso

### 1. Prerequisitos
- Docker instalado
- Docker Compose instalado

### 2. Levantar los servicios
```bash
docker-compose up -d
```

### 3. Verificar que los contenedores estén corriendo
```bash
docker-compose ps
```

### 4. Acceder a Adminer
Abrir navegador en: `http://localhost:8080`

## Credenciales para Adminer

### MongoDB
- **Sistema**: MongoDB
- **Servidor**: `mongodb` (nombre del contenedor)
- **Usuario**: `admin`
- **Contraseña**: `pharmavida123`
- **Base de datos**: `pharmavida_db`
- **Puerto**: 27018

*Nota: Para MongoDB en Adminer, es posible que necesites usar una herramienta específica como MongoDB Compass*

### MySQL
- **Sistema**: MySQL
- **Servidor**: `mysql`
- **Usuario**: `pharmavida_user`
- **Contraseña**: `pharmavida123`
- **Base de datos**: `pharmavida_db`
- **Puerto**: 3307

**Credenciales alternativas de root:**
- **Usuario**: `root`
- **Contraseña**: `pharmavida123`

### PostgreSQL
- **Sistema**: PostgreSQL
- **Servidor**: `postgresql`
- **Usuario**: `pharmavida_user`
- **Contraseña**: `pharmavida123`
- **Base de datos**: `pharmavida_db`
- **Puerto**: 5433

## Conexiones Directas (desde host)

Si quieres conectarte directamente desde tu máquina local:

- **MongoDB**: `mongodb://admin:pharmavida123@localhost:27018/pharmavida_db`
- **MySQL**: `mysql://pharmavida_user:pharmavida123@localhost:3307/pharmavida_db`
- **PostgreSQL**: `postgresql://pharmavida_user:pharmavida123@localhost:5433/pharmavida_db`

## Comandos Útiles

### Detener todos los servicios
```bash
docker-compose down
```

### Detener y eliminar volúmenes (¡CUIDADO! Se perderán los datos)
```bash
docker-compose down -v
```

### Ver logs de un servicio específico
```bash
docker-compose logs [servicio]
# Ejemplo: docker-compose logs mysql
```

### Reiniciar un servicio específico
```bash
docker-compose restart [servicio]
```

## Estructura de Volúmenes

Los datos se persisten en volúmenes Docker:
- `mongodb_data`: Datos de MongoDB
- `mysql_data`: Datos de MySQL
- `postgresql_data`: Datos de PostgreSQL

## Red

Todos los servicios están en la red `PharmaVida` y pueden comunicarse entre sí usando sus nombres de contenedor como hostnames.