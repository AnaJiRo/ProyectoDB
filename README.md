# 📘 Proyecto de Base de Datos con GitHub, Docker y PostgreSQL

## 🎯 Objetivo del Ejercicio

El objetivo principal de este proyecto es reforzar habilidades esenciales para el desarrollo y gestión de bases de datos, integrando herramientas modernas como GitHub, Docker y PostgreSQL. Aprenderás a:

- Crear y gestionar un repositorio en GitHub.
- Trabajar con ramas, commits y hacer rollback de cambios en Git.
- Configurar y levantar un contenedor PostgreSQL usando Docker.
- Conectarte a la base de datos desde un gestor como DBeaver.
- Diseñar un Diagrama Entidad-Relación (ERD) para un proyecto propio.

---

## 📝 Instrucciones

### 1. Crear un nuevo repositorio en GitHub

- Ve a tu cuenta de GitHub y crea un nuevo repositorio, por ejemplo: `ProyectoDB`.
- Añade un `README.md` inicial describiendo el propósito del proyecto (e.g., tienda de ropa, autoescuela, etc.).

### 2. Clonar el repositorio en tu máquina local

```bash
git clone <URL-del-repositorio>
cd ProyectoDB
```

### 3. Crear un proyecto sencillo de base de datos

Crea un archivo `docker-compose.yml` con el siguiente contenido:

```yaml
version: '3.8'

services:
  db:
    image: postgres:latest
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
      POSTGRES_DB: proyectodb
    ports:
      - "5432:5432"
    volumes:
      - postgres-data:/var/lib/postgresql/data

volumes:
  postgres-data:
```

### 4. Levantar el contenedor PostgreSQL con Docker

Ejecuta el siguiente comando en la terminal:

```bash
docker-compose up -d
```

Esto descargará la imagen de PostgreSQL (si aún no la tienes) y levantará el contenedor en segundo plano.

### 5. Crear ramas y hacer commits

Una buena práctica en Git es trabajar con ramas para desarrollar nuevas funcionalidades. Aquí te mostramos cómo hacerlo:

1. Crea una nueva rama:
```bash
git checkout -b feature/database-setup
```
2. Realiza los cambios que necesites (por ejemplo, agregar el archivo docker-compose.yml).

3. Añade los archivos al área de staging:

```bash
git add .
```

4. Haz un commit con un mensaje claro:

```bash
git commit -m "feat(database): add PostgreSQL setup with Docker Compose"
```

5. Sube tu rama a GitHub:

```bash
git push -u origin feature/database-setup
```
Usar mensajes de commit descriptivos y consistentes ayuda a mantener un historial claro y entendible.

### 6. Cometer errores a propósito y practicar rollback

Para mejorar tu dominio de Git, es útil practicar cómo revertir errores y deshacer cambios.

#### 🔁 Deshacer el último commit (pero conservar los cambios):

```bash
git reset --soft HEAD~1
```
- Esto elimina el commit más reciente pero mantiene los archivos modificados en tu área de trabajo.

🔙 Volver al estado de un commit anterior:
```bash
git checkout <ID-del-commit>
```
- Puedes encontrar el ID del commit ejecutando `git log`.

↩️ Revertir un commit (sin eliminar historial):
```bash
git revert <ID-del-commit>
```
- Esto crea un nuevo commit que deshace los cambios del commit indicado.

  🗑️ Borrar una rama en remoto:
```bash
git push origin --delete nombre-rama
```
- Útil para limpiar ramas que ya no necesitas en el repositorio remoto.

### 7. Conectar a PostgreSQL con DBeaver (o cualquier otro gestor de bases de datos)

Sigue estos pasos para conectar tu base de datos PostgreSQL al gestor de bases de datos DBeaver:

1. Abre **DBeaver** e inicia una nueva conexión.
2. Selecciona **PostgreSQL** como tipo de base de datos.
3. Introduce los siguientes datos de conexión:

```bash
Host: localhost
Port: 5432
Database: proyectodb
User: user
Password: password
```

4. Haz clic en **Test Connection** para comprobar que todo funciona correctamente.
5. Si la conexión es exitosa, guarda y comienza a explorar tu base de datos desde el gestor.

> Asegúrate de que el contenedor esté corriendo (`docker ps`) antes de intentar conectarte.

### 8. Diseñar un Diagrama Entidad-Relación (ERD)

Utiliza DBeaver para diseñar visualmente el modelo relacional de tu base de datos. Sigue estos pasos:

1. Abre **DBeaver** y selecciona tu conexión a PostgreSQL.
2. Crea un nuevo esquema o usa uno existente.
3. Abre el **Diagrama ERD** desde el esquema y empieza a agregar tablas y relaciones.
4. Diseña el modelo de acuerdo a tu proyecto.

#### 💡 Ideas de proyectos:

- 🛒 **Tienda de Ropa**: Productos, Categorías, Clientes, Pedidos, Facturas.
- 🚗 **Autoescuela**: Alumnos, Clases, Instructores, Pagos, Exámenes.
- 🎓 **Plataforma de Cursos Online**: Usuarios, Cursos, Lecciones, Evaluaciones, Certificados.

> Usa las herramientas de DBeaver para diseñar tu modelo relacional y documenta cómo piensas implementarlo en tu proyecto.

### 9. Subir cambios a GitHub

Cuando consideres que tu rama está lista, fusiónala con main:

```bash
git checkout main
git merge feature/database-setup
git push

```
### 10. Documentación

- Documenta todos los pasos en tu repositorio como parte del proyecto.
- Incluye capturas de pantalla y explicaciones claras en formato Markdown o PDFs en carpetas organizadas.
- Asegúrate de tener tu repositorio público y bien estructurado.
---

## 🚀 Entrega
- Asegúrate de que tu repositorio está público, con todos los cambios subidos y bien documentado.
- Añade el enlace de tu repositorio a un draft dentro del proyecto de tu equipo animal.
- Informa a tu tutor de CodeArts cuando hayas completado el ejercicio o si necesitas ayuda en algún paso.
