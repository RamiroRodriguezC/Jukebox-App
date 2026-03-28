# Jukebox

Aplicación web para gestión y descubrimiento musical. Permite explorar álbumes, artistas y canciones, escribir reseñas y gestionar tus favoritas.

## Tech Stack

**Backend:**
- Node.js + Express
- MongoDB + Mongoose
- JWT Authentication
- bcrypt

**Frontend:**
- React + Vite
- Ant Design
- React Router
- Axios

## Estructura del Proyecto

```
Jukebox/
├── backend/           # Servidor API
│   ├── src/
│   │   ├── config/    # Configuración de BD
│   │   ├── controllers/
│   │   ├── models/    # Modelos Mongoose
│   │   ├── routes/   # Rutas API
│   │   ├── services/  # Lógica de negocio
│   │   └── app.js    # Entry point
│   └── package.json
│
├── frontend/         # Aplicación React
│   ├── src/
│   └── package.json
│
└── README.md
```

## Modelos de Datos

- **Usuario**: mail, username, rol (admin/user), foto de perfil, canciones favoritas (máx 4)
- **Artista**: nombre, país, descripción, foto
- **Álbum**: título, año, portada, artistas, canciones
- **Canción**: título, duración, género, fecha de salida, álbum, autores
- **Review**: rating (0-5), like, comentario, autor, entidad (álbum o canción)

## API Endpoints

| Recurso   | Endpoints                                      |
|-----------|-----------------------------------------------|
| `/usuarios` | GET, POST, PUT, DELETE                        |
| `/artistas` | GET, POST, PUT, DELETE                        |
| `/albums`   | GET, POST, PUT, DELETE                        |
| `/canciones`| GET, POST, PUT, DELETE, búsqueda texto        |
| `/reviews`  | GET, POST, PUT, DELETE                        |

## Instalación

```bash
# Instalar dependencias del backend
cd backend
npm install

# Instalar dependencias del frontend
cd ../frontend
npm install
```

## Configuración

Crear archivo `.env` en `/backend`:

```env
PORT=3000
MONGO_URI=mongodb://localhost:27017/jukebox
JWT_SECRET=tu_secreto_aqui
```

## Ejecutar

```bash
# Backend (desde /backend)
npm run devstart

# Frontend (desde /frontend)
npm run dev
```

El frontend corre en `http://localhost:5173` y el backend en `http://localhost:3000`.

## Características

- **Autenticación**: Registro/login con JWT
- **Roles**: Admin (gestión completa) / User (limitado)
- **Reviews**: Reseñas con rating y likes en álbumes y canciones
- **Favoritos**: Hasta 4 canciones favoritas por usuario
- **Búsqueda**: Búsqueda de texto completo en canciones
- **Borrado lógico**: Eliminación en cascada de entidades relacionadas
