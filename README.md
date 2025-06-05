# 🎬📚 Mis recursos app

Una aplicación web que permite a los usuarios llevar un registro de su progreso al ver **series, películas** y **leer libros**. Los usuarios pueden agregar, editar, eliminar y visualizar sus recursos favoritos, así como filtrarlos y buscarlos de forma sencilla.

---

## 🛠️ Tecnologías Recomendadas

- Backend: Node.js / Express / Python Flask
- Base de datos: MongoDB (Se uso en este caso)
- Frontend: React / Vue / HTML-CSS-JS
- Otros: Mongoose (ODM para MongoDB), MongoDB Compass (interfaz visual)

---

## 📦 Estructura del Proyecto

- [usuarios.json](usuarios.json) : contiene 50 usuarios registrados.
- [plataformas.json](plataformas.json) : contiene 39 plataformas diferentes (Netflix, Amazon, Kindle, etc.).
- [generos.json](generos.json) : contiene 36 géneros distintos (Drama, Ciencia Ficción, Terror, etc.).
- [recursos.json](recursos.json) : contiene 50 registros con datos variados de recursos agregados por los usuarios.

---

## 📚 Colecciones en MongoDB

### 1. `usuarios`

Contiene información básica del usuario:

```json

{
  "id": 1,
  "nombre": "Carlos Martínez",
  "correo": "carlos.martinez@example.com",
  "contrasena": "clave123",
  "fecha_creacion": "2023-04-12"
}

```

### 2. `plataformas`

Lista de plataformas donde se consumen los recursos:

```json

{
  "id": 1,
  "nombre": "Netflix"
}

```

### 3. `generos`

Tipos de géneros clasificados:

```json

{
  "id": 1,
  "nombre": "Acción"
}

```

### 4. `recursos`

Registro de los recursos que los usuarios están viendo o han terminado:

```json

{
  "usuario_id": 22,
  "nombre": "La Casa de Papel",
  "genero_id": 29,
  "plataforma_id": 20,
  "estado": "Pendiente",
  "formato": "Serie",
  "fecha_terminacion": "2025-04-07",
  "valoracion": 4,
  "resena": "El final me dejó sin palabras."
}

```

---

## ✅ Funcionalidades

### CRUD (Crear, Leer, Actualizar, Eliminar)

- **Crear**: añadir un recurso con campos como nombre, género, plataforma, estado, formato, fecha de terminación, valoración y reseña.
- **Leer**: visualizar todos los recursos del usuario.
- **Actualizar**: modificar la información de cualquier recurso existente.
- **Eliminar**: eliminar un recurso de la base de datos.

### Filtros y Búsqueda

- Filtrar por estado (Pendiente, En progreso, Terminado).
    ```js
    db.recursos.find({ "estado": "Pendiente" })
    db.recursos.find({ "estado": "En progreso" })
    db.recursos.find({ "estado": "Terminado" })
    ```
- Filtrar por formato (Serie, Película, Libro).
    ```js
    db.recursos.find({ "formato": "Serie" })
    db.recursos.find({ "formato": "Película" })
    db.recursos.find({ "formato": "Libro" })
    ```

- Filtrar por plataforma (Netflix, HBO, Kindle, etc.).
    ```js
    db.recursos.find({ "plataforma_id": 6 })  // Apple TV+
    db.recursos.find({ "plataforma_id": 9 })  // YouTube
    db.recursos.find({ "plataforma_id": 33 })  // Wattpad
    ```
- Buscar recursos por nombre.
    ```js
    db.recursos.find({ "nombre": "Big Little Lies" }) 
    db.recursos.find({ "nombre": "The Crown" })
    db.recursos.find({ "nombre": "Sapiens: De animales a dioses" })
    ```

### Validación de Datos

- Validar que la fecha de terminación sea válida.
- Asegurar que la valoración esté entre 1 y 5 estrellas.
- Verificar que los campos obligatorios estén presentes.

---

## ⚙️ Comandos para crear las colecciones

Asumiendo que estás usando MongoDB con la herramienta de línea de comandos `mongodb`:

```js
use entretenimiento

db.usuarios.insertMany(<contenido de usuarios.json>)  
db.plataformas.insertMany(<contenido de plataformas.json>)
db.generos.insertMany(<contenido de generos.json>)
db.recursos.insertMany(<contenido de recursos.json>)
    
```

Asegúrate de tener los archivos `.json` bien formateados antes de importar.

---

## 📅 Fecha de entrega

🕒 **5 de junio de 2025 – 11:59 p.m.**

---

## 📁 Archivos incluidos para entrega

- `usuarios.json` → colección `usuarios`
- `plataformas.json` → colección `plataformas`
- `generos.json` → colección `generos`
- `recursos.json` → colección `recursos`