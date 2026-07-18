# 🎬 Movies React

Aplicación web para buscar y explorar películas, construida con React. Permite buscar títulos, ver un listado con scroll infinito y consultar el detalle de cada película.

🔗 **Demo:** [melisa8181.github.io/movies-react](https://melisa8181.github.io/movies-react)

## ✨ Funcionalidades

- 🔍 Búsqueda de películas con **debounce** (evita hacer una petición por cada tecla)
- 📃 Listado de resultados con **scroll infinito** (`react-infinite-scroll-component`)
- 🎞️ Vista de detalle por película (poster, información, etc.)
- ⏳ Estado de carga con spinner
- 🚫 Estado vacío cuando no hay resultados
- 🖼️ Imagen placeholder (`no-image.jpg`) cuando la película no tiene poster
- 🧭 Navegación entre páginas con React Router

## 🛠️ Tecnologías

- [React 17](https://reactjs.org/)
- [React Router DOM v5](https://v5.reactrouter.com/)
- [React Icons](https://react-icons.github.io/react-icons/)
- [React Infinite Scroll Component](https://www.npmjs.com/package/react-infinite-scroll-component)
- [The Movie Database (TMDB) API](https://www.themoviedb.org/documentation/api) — fuente de datos de películas
- Create React App (`react-scripts`)
- Hooks personalizados (`useDebounce`, `useQuery`)

## 📁 Estructura del proyecto

```
src/
├── components/
│   ├── Empty.jsx            # Estado vacío (sin resultados)
│   ├── MovieCard.jsx        # Tarjeta individual de película
│   ├── MoviesGrid.jsx       # Grilla de resultados
│   ├── Search.jsx           # Input de búsqueda
│   ├── Spinner.jsx          # Indicador de carga
│   └── movies.json          # Datos de ejemplo (mock de listado, formato TMDB)
├── hooks/
│   ├── useDebounce.jsx      # Debounce para el input de búsqueda
│   └── useQuery.jsx         # Hook para manejar query params / peticiones
├── pages/
│   ├── LandingPage.jsx      # Página principal (búsqueda + listado)
│   ├── MovieDetails.jsx     # Página de detalle de una película
│   └── movie.json           # Datos de ejemplo (mock de detalle, formato TMDB)
├── utils/
│   ├── getMovieImg.js       # Construye la URL de la imagen del poster
│   └── httpClient.js        # Cliente HTTP para consumir la API
├── App.jsx
├── index.js
└── no-image.jpg
```

## 🚀 Cómo correrlo localmente

1. Cloná el repositorio:
   ```bash
   git clone https://github.com/Melisa8181/movies-react.git
   cd movies-react
   ```

2. Instalá las dependencias:
   ```bash
   npm install
   ```

3. Configurá las variables de entorno. Copiá el archivo de ejemplo:
   ```bash
   cp .env.template .env
   ```
   Y completá tu `.env` con las credenciales de [TMDB](https://www.themoviedb.org/settings/api):
   ```
   REACT_APP_API=https://api.themoviedb.org/3
   REACT_APP_API_TOKEN=tu_read_access_token_de_tmdb
   ```
   > ⚠️ Usá el **Read Access Token** (API v4, formato JWT largo), no la API Key clásica — la app lo envía como `Authorization: Bearer ...`.

4. Iniciá el proyecto en modo desarrollo:
   ```bash
   npm start
   ```
   Se abrirá en [http://localhost:3000](http://localhost:3000).

## 📜 Scripts disponibles

| Comando         | Descripción                                      |
|-----------------|---------------------------------------------------|
| `npm start`     | Corre la app en modo desarrollo                    |
| `npm run build` | Genera la versión de producción en `/build`        |
| `npm test`      | Corre los tests                                    |
| `npm run eject` | Expone la configuración de Create React App        |

## 🌐 Deploy

El proyecto está desplegado con **GitHub Pages**, publicado desde:
```
https://melisa8181.github.io/movies-react
```
