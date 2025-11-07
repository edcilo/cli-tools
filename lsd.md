# `lsd`

## Descripción

`lsd` es un reemplazo para el comando `ls` con muchos colores bonitos y otras características como iconos, vista de árbol y más.

## Instalación

```bash
sudo apt install lsd
```
Si no está disponible en los repositorios de tu versión de Debian, puedes descargarlo desde la página de [releases de GitHub](https://github.com/lsd-rs/lsd/releases).

## Sintaxis de Uso

```bash
lsd [opciones] [ruta]
```

## Opciones Válidas

*   `-l, --long`: Muestra metadatos extendidos.
*   `-a, --all`: No ignora las entradas que comienzan con `.`.
*   `-i, --inode`: Muestra el número de inodo de cada archivo.
*   `-d, --directory-only`: Muestra los directorios en lugar de su contenido.
*   `-h, --human-readable`: Muestra los tamaños de archivo en un formato legible por humanos.
*   `--tree`: Muestra los archivos en una estructura de árbol.
*   `--depth <N>`: Limita la profundidad del árbol.
*   `--color <when>`: Cuándo usar colores (`always`, `auto`, `never`).
*   `--icon <when>`: Cuándo mostrar iconos (`always`, `auto`, `never`).

## Ejemplos de Uso

*   **Listar archivos en el directorio actual con detalles y de forma legible:**
    ```bash
    lsd -lh
    ```

*   **Listar todos los archivos, incluidos los ocultos:**
    ```bash
    lsd -a
    ```

*   **Mostrar el contenido del directorio como un árbol:**
    ```bash
    lsd --tree
    ```

*   **Mostrar el árbol con una profundidad máxima de 2:**
    ```bash
    lsd --tree --depth 2
    ```

*   **Listar archivos con iconos:**
    ```bash
    lsd --icon always
    ```
    *Nota: Para que los iconos se muestren correctamente, es posible que necesites instalar una "Nerd Font".*
