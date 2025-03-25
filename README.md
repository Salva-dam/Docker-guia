# 🚀 Guía rápida de Docker y Docker Compose

Este repositorio proporciona una guía básica para usar Docker y Docker Compose, con los comandos más comunes y sus explicaciones.

---

## 📌 Instalación de Docker y Docker Compose

### 🔹 **Instalar Docker en Ubuntu**
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y ca-certificates curl gnupg

# Agregar clave GPG y repositorio oficial
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo tee /etc/apt/keyrings/docker.asc > /dev/null
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Instalar Docker
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### 🔹 **Instalar Docker Compose manualmente**
```bash
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

Verificar la instalación:
```bash
docker --version
docker-compose --version
```

---

## 🔥 **Comandos esenciales de Docker**

### 🛠️ **Gestionar contenedores**

| Comando | Descripción |
|---------|-------------|
| `docker run -d -p 80:80 nginx` | Ejecuta un contenedor en segundo plano con Nginx en el puerto 80 |
| `docker ps` | Lista los contenedores en ejecución |
| `docker ps -a` | Lista todos los contenedores (activos e inactivos) |
| `docker stop <ID>` | Detiene un contenedor |
| `docker rm <ID>` | Elimina un contenedor |
| `docker logs <ID>` | Muestra los logs de un contenedor |

### 🏗️ **Imágenes y volúmenes**
| Comando | Descripción |
|---------|-------------|
| `docker images` | Lista las imágenes locales |
| `docker rmi <IMAGEN>` | Elimina una imagen |
| `docker volume ls` | Lista los volúmenes disponibles |
| `docker volume rm <VOLUMEN>` | Elimina un volumen |

---

## ⚡ **Comandos esenciales de Docker Compose**

### 📄 **Ejemplo de `docker-compose.yml`**
```yaml
version: '3.8'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
    volumes:
      - ./html:/usr/share/nginx/html
```

### 🛠️ **Administrar servicios con Docker Compose**

| Comando | Descripción |
|---------|-------------|
| `docker-compose up -d` | Inicia los contenedores en segundo plano |
| `docker-compose down` | Detiene y elimina los contenedores |
| `docker-compose ps` | Lista los servicios en ejecución |
| `docker-compose logs` | Muestra los logs de los servicios |

---

## 🚀 **Clonar este repositorio y probarlo**
```bash
git clone https://github.com/tu_usuario/docker-guide.git
cd docker-guide
docker-compose up -d
```

Visita `http://localhost:8080` para ver el contenedor en acción.

---

### 🛠️ **Siguientes pasos**
- Experimenta con Docker creando tu propia aplicación.
- Aprende sobre Docker Hub y cómo subir imágenes personalizadas.
- Investiga más opciones de `docker-compose.yml` para configuraciones avanzadas.

📌 **Este repositorio es ideal para principiantes y puede ampliarse con nuevos ejemplos.** ¡Contribuye y mejora la guía! 🚀

