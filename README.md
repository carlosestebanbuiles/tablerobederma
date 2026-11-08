# Tablero privado

Sitio estático con dos páginas protegidas con contraseña. El contenido de cada página está cifrado (AES-256, clave derivada con PBKDF2); sin la contraseña solo se ve el formulario de acceso.

| Página | Ruta | Para quién |
|---|---|---|
| Tablero completo | `/` (`index.html`) | Socias de BeDerma |
| Tablero Resurface | `/resurface/` (`resurface/index.html`) | Socias de Resurface |

Las cifras son fijas a la fecha que muestra cada página. No hay servidor, base de datos ni conexión a otros servicios: todo funciona dentro del navegador.

## Publicar en GitHub Pages

1. Crear un repositorio nuevo (por ejemplo `tablero`). Puede ser público: el contenido va cifrado.
2. Subir a la raíz del repositorio, sin cambiarles el nombre ni la ubicación:
   - `index.html`
   - `resurface/index.html`
   - `robots.txt`
   - `.nojekyll`
   - `README.md`
3. En el repositorio: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
4. En uno o dos minutos queda en línea:
   - `https://<usuario>.github.io/<repositorio>/`
   - `https://<usuario>.github.io/<repositorio>/resurface/`

## Reglas

- No subir nunca las contraseñas, ni los archivos de la carpeta `fuente` (contienen los datos sin cifrar).
- No editar los `index.html` a mano: se regeneran completos en cada actualización.
- Para actualizar, reemplazar los dos `index.html` por los nuevos y hacer commit. El enlace no cambia.
