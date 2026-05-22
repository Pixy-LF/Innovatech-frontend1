# 💻 Innovatech - Plataforma de Despachos (Frontend)

Este repositorio contiene la interfaz gráfica de usuario para el sistema de despachos de **Innovatech**, optimizada para producción y desplegada de forma automatizada en la nube.

## 🛠️ Tecnologías Utilizadas
* **Frontend:** JavaScript / Node.js
* **Servidor Web de Producción:** Nginx (Alpine)
* **Contenedorización:** Docker & Docker Compose
* **CI/CD:** GitHub Actions
* **Cloud Infrastructure:** AWS EC2

## ⚡ Optimización y Despliegue (Rúbrica)
* **Estrategia Multi-stage:** Se utiliza Node.js exclusivamente para compilar los recursos estáticos del sitio y luego se transfieren a una imagen limpia de **Nginx**, logrando un contenedor ultra ligero y veloz.
* **Orquestación Local:** Configurado con `docker-compose.yml` para levantar el servidor web en el puerto `80`.

## 🚀 Pipeline de Automatización
Al realizar un `push` a la rama `deploy`:
1. GitHub Actions construye la imagen con la última versión del código.
2. Sube la imagen a **Docker Hub**.
3. Ejecuta un script remoto vía **SSH** en **AWS EC2** para actualizar el contenedor de cara al cliente final.