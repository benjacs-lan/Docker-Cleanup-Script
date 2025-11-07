🧹 Docker Cleanup Script
Descripción

Este script en Bash realiza una limpieza completa de Docker, eliminando recursos no utilizados como imágenes, contenedores, volúmenes y cachés de compilación.
Es una herramienta sencilla pero potente para liberar espacio en disco y mantener un entorno Docker limpio y eficiente.

⚙️ ¿Qué hace?

El script ejecuta una serie de comandos Docker en orden lógico:

🖼️ Elimina imágenes no etiquetadas

docker image prune -a


🧩 Elimina contenedores detenidos

docker container prune


💾 Elimina volúmenes sin uso

docker volume prune


⚙️ Limpia sistemas no utilizados (redes, cachés, etc.)

docker system prune


🧱 Limpia la caché de compilación de imágenes

docker builder prune


Cada comando solicitará confirmación antes de eliminar los recursos, a menos que se ejecute con la opción -f para forzar la eliminación.

🧰 Requisitos

Sistema operativo: Linux o macOS

Docker instalado y corriendo

Permisos suficientes para ejecutar comandos Docker (puede requerir sudo)

Bash 4.0 o superior

🚀 Uso

1️⃣ Otorgar permisos de ejecución al script:

chmod +x docker_cleanup.sh


2️⃣ Ejecutar el script:

./docker_cleanup.sh


💡 Si deseas omitir las confirmaciones, puedes agregar la opción -f directamente en cada comando dentro del script.

🧩 Ejemplo de salida
WARNING! This will remove:
  - all stopped containers
  - all networks not used by at least one container
  - all dangling images
  - all dangling build cache
Are you sure you want to continue? [y/N] y
Deleted Images:
  untagged: <none>
  deleted: sha256:abc123...
Total reclaimed space: 2.1GB
✅ Limpieza completada exitosamente.

⚠️ Advertencia

Este script elimina recursos de Docker de forma permanente.
Antes de ejecutarlo, asegúrate de que no necesites los contenedores, imágenes o volúmenes en uso.

🧑‍💻 Autor

Benjamin Felipe Castillo
DevOps & Ciberseguridad

📄 Licencia
Este script se distribuye bajo la licencia MIT.
