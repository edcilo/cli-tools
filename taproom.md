# `taproom`

## Descripción

`taproom` es una Interfaz de Usuario de Terminal (TUI) interactiva para Homebrew. Está diseñada para proporcionar una forma más rápida y fluida de explorar, gestionar e interactuar con las fórmulas y casks de Homebrew directamente desde la terminal.

## Instalación

Puedes instalar `taproom` usando Homebrew:

```bash
brew install gromgit/brewtils/taproom
```

## Sintaxis de Uso

Para iniciar la interfaz interactiva, simplemente ejecuta:

```bash
taproom [opciones]
```

## Opciones Válidas

`taproom` acepta varios flags para personalizar su comportamiento inicial:

*   `-i, --invalidate-cache`: Invalida la caché y vuelve a descargar los datos de brew.sh.
*   `--fetch-release`: Obtiene información de lanzamiento para los paquetes instalados (requiere `gh` CLI).
*   `--hide-columns <columnas>`: Oculta y omite la carga de datos para las columnas especificadas (ej. "size,popularity").
*   `-t, --load-timer`: Muestra un temporizador en la pantalla de carga.
*   `--hide-help`: Oculta el texto de ayuda en la parte inferior de la aplicación.
*   `-s, --sort-column <nombre_columna>`: Especifica la columna inicial por la que ordenar.
*   `-f, --filters <filtros>`: Especifica filtros iniciales (ej. "installed").

## Ejemplos de Uso

*   **Iniciar `taproom`:**
    ```bash
    taproom
    ```
    Esto abrirá la TUI interactiva.

*   **Iniciar con la caché invalidada:**
    ```bash
    taproom --invalidate-cache
    ```
    Esto fuerza una recarga de todos los datos de Homebrew.

*   **Iniciar con un filtro predefinido:**
    ```bash
    taproom --filters "installed"
    ```
    Esto mostrará inicialmente solo los paquetes que ya están instalados.

*   **Iniciar y ordenar por popularidad:**
    ```bash
    taproom --sort-column "90d"
    ```
    Esto ordenará los paquetes por el recuento de instalaciones de los últimos 90 días.
