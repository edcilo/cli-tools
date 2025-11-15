# `tldr`

## Descripción

`tldr` es un cliente para el proyecto `tldr-pages`, que proporciona ejemplos simplificados y prácticos para herramientas de línea de comandos comunes. Ofrece resúmenes concisos, más fáciles de digerir que las páginas `man` tradicionales.

## Instalación

La instalación de `tldr` varía según el sistema operativo y el gestor de paquetes. Aquí algunos ejemplos:

### Node.js (multiplataforma)
```bash
npm install -g tldr
```

### Python (multiplataforma)
```bash
pip install tldr
```

### Homebrew (macOS y Linux)
```bash
brew install tldr
```

### Apt (Debian/Ubuntu)
```bash
sudo apt install tldr
```

## Sintaxis de Uso

```bash
tldr [opciones] <comando>
```

## Opciones Válidas

*   `-u, --update`: Actualiza la caché local de las páginas tldr.
*   `-p <plataforma>, --platform <plataforma>`: Especifica la plataforma (ej. `linux`, `osx`, `windows`, `android`, `sunos`).
*   `-s <palabra_clave>, --search <palabra_clave>`: Busca comandos relacionados con una palabra clave.
*   `-L, --list`: Lista todas las páginas disponibles en la caché local.
*   `-v, --version`: Muestra la versión del cliente tldr.
*   `-h, --help`: Muestra el mensaje de ayuda.

## Ejemplos de Uso

*   **Obtener ayuda para un comando básico:**
    ```bash
    tldr ls
    ```
    Muestra ejemplos de uso común para el comando `ls`.

*   **Obtener ayuda para un subcomando (ej. git clone):**
    ```bash
    tldr git-clone
    ```
    Muestra ejemplos para el subcomando `git clone`.

*   **Actualizar la caché local de páginas:**
    ```bash
    tldr --update
    ```
    Descarga las últimas páginas tldr al caché local.

*   **Buscar un comando en una plataforma específica (ej. tar en Linux):**
    ```bash
    tldr -p linux tar
    ```
    Muestra ejemplos de `tar` específicos para Linux.

*   **Buscar comandos relacionados con una palabra clave:**
    ```bash
    tldr -s "network"
    ```
    Busca y lista comandos relacionados con "network".
