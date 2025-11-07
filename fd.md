# `fd`

## Descripción

fd es una alternativa más rápida y fácil de usar al comando `find` de Unix. Proporciona una sintaxis más intuitiva, resultados coloreados y algunas características adicionales como la búsqueda de expresiones regulares por defecto y el respeto automático de los archivos `.gitignore`.

## Instalación

<!--
  Muestra el comando o los comandos necesarios para instalar la herramienta.
  Utiliza un bloque de código para que sea fácil de copiar y pegar.
  Ejemplo:
-->
```bash
sudo apt install fd-find
```

## Sintaxis de Uso

```bash
fd [opciones] [patrón] [ruta...]
```

## Opciones Válidas

*   `-H`, `--hidden`: Incluye archivos y directorios ocultos en la búsqueda.
*   `-I`, `--no-ignore`: No respeta los archivos `.gitignore`, `.ignore` o `.fdignore`.
*   `-L`, `--follow`: Sigue enlaces simbólicos.
*   `-t <tipo>`, `--type <tipo>`: Filtra por tipo de archivo (f: archivo, d: directorio, l: enlace simbólico, e: ejecutable).
*   `-e <extensión>`, `--extension <extensión>`: Filtra por extensión de archivo.
*   `-s <tamaño>`, `--size <tamaño>`: Filtra por tamaño de archivo (ej. `+1M`, `-500K`).
*   `-x <comando>`, `--exec <comando>`: Ejecuta un comando para cada resultado encontrado.
*   `-h`, `--help`: Muestra el mensaje de ayuda.

## Ejemplos de Uso

*   **Buscar archivos por nombre en el directorio actual:**
    ```bash
    fd mi_archivo
    ```
    Esto buscará archivos que contengan "mi_archivo" en su nombre en el directorio actual y subdirectorios.

*   **Buscar archivos `.js`:**
    ```bash
    fd -e js
    ```
    Encuentra todos los archivos con la extensión `.js`.

*   **Buscar directorios con un nombre específico:**
    ```bash
    fd -t d mis_docs
    ```
    Busca directorios llamados "mis_docs".

*   **Buscar y ejecutar un comando en los resultados:**
    ```bash
    fd ".log" -x rm
    ```
    Encuentra todos los archivos `.log` y los elimina.

*   **Buscar archivos ignorando `.gitignore`:**
    ```bash
    fd -I "temp"
    ```
    Busca archivos o directorios que contengan "temp", incluso si están en `.gitignore`.
