# Mega Cascade Adventure

¡Bienvenido a **Mega Cascade Adventure**!  
Este es un juego web desarrollado con [PixiJS](https://pixijs.com/) para el frontend y [FastAPI](https://fastapi.tiangolo.com/) para el backend. Los niveles del juego pueden gestionarse tanto desde un archivo YAML como desde un módulo TypeScript, facilitando el desarrollo y la edición.

---

## Estructura del Proyecto

```
mega_cascade_adventure/
├── client/                # TypeScript + PixiJS
│   ├── index.html
│   ├── engine.ts
│   └── resources/         # Texturas, audio, efectos
├── server/                # Python (FastAPI)
│   ├── main.py            # Lógica del juego y API REST
│   ├── stages.yaml        # Niveles en formato YAML
│   └── stages.ts          # Niveles en formato TypeScript
└── README.md              # Este archivo
```

---

## Instalación y Ejecución

### 1. Clona el Repositorio

```bash
git clone https://github.com/tu-usuario/mega_cascade_adventure.git
cd mega_cascade_adventure
```

### 2. Backend (FastAPI)

#### a. Instalación de dependencias

```bash
cd server
python -m venv venv
source venv/bin/activate  # En Windows usa: venv\Scripts\activate
pip install fastapi uvicorn
```

#### b. Ejecuta el servidor

```bash
uvicorn main:app --reload
```

El backend estará disponible en [http://localhost:8000](http://localhost:8000)

> **Nota:** Puedes elegir entre usar los niveles desde `stages.yaml` o `stages.ts` cambiando la variable `USE_YAML` en `main.py`.

### 3. Frontend (PixiJS)

Abre un servidor local en la carpeta `client` (recomendado para evitar problemas de CORS). Por ejemplo:

- Usando VS Code: haz clic derecho en `index.html` y elige "Open with Live Server".
- O usa Node simple HTTP server:

```bash
cd client
npx http-server -p 9000
```

Luego visita [http://localhost:9000](http://localhost:9000) en tu navegador.

---

## Uso de la API

- Obtener un nivel específico (por ID):
  ```
  GET /api/stage/<stage_id>
  ```
  Ejemplo: [http://localhost:8000/api/stage/1](http://localhost:8000/api/stage/1)

La respuesta será un JSON con los datos del nivel.

---

## Niveles

Puedes definir los niveles en dos archivos:

- **stages.yaml:** Ideal para edición rápida y externa.
- **stages.ts:** Útil si quieres lógica TypeScript o cargar los niveles desde código.

Cambia la variable `USE_YAML` en `server/main.py` según el método que prefieras.

---

## Personalización

- Agrega tus texturas, sprites y audio en `client/resources/`.
- Modifica la lógica del juego en `client/engine.ts`.
- Amplía la API o la lógica de niveles en `server/main.py`, `stages.yaml` o `stages.ts`.

---

## Créditos

- [PixiJS](https://pixijs.com/) para el motor de renderizado 2D.
- [FastAPI](https://fastapi.tiangolo.com/) para el backend en Python.

---

## Licencia

Este proyecto se distribuye bajo la licencia Apache-2.0.  
¡Siéntete libre de modificar, compartir y mejorar!

---

# PR Merge: 2025-12-03 11:10:41
