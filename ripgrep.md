# `ripgrep`

## Descripción

`ripgrep` (rg) es una utilidad de búsqueda de línea de comandos que busca recursivamente directorios para patrones de expresiones regulares. Es extremadamente rápido y eficiente, ideal para desarrolladores y administradores de sistemas.

## Instalación

```bash
# En sistemas basados en Debian/Ubuntu
sudo apt install ripgrep

# En sistemas basados en Fedora
sudo dnf install ripgrep

# En macOS con Homebrew
brew install ripgrep

# En Windows con Scoop
scoop install ripgrep
```

## Sintaxis de Uso

```bash
rg [opciones] <patrón> [ruta...]
```

## Opciones Válidas

*   `-i, --ignore-case`: Realiza una búsqueda insensible a mayúsculas y minúsculas.
*   `-F, --fixed-strings`: Trata el patrón como una cadena literal, no como una expresión regular.
*   `-w, --word-regexp`: Busca el patrón como una palabra completa.
*   `-l, --files-with-matches`: Imprime solo los nombres de los archivos que contienen coincidencias.
*   `-n, --line-number`: Muestra el número de línea para cada coincidencia.
*   `-C <num>, --context <num>`: Muestra `num` líneas de contexto alrededor de cada coincidencia.
*   `-B <num>, --before-context <num>`: Muestra `num` líneas de contexto antes de cada coincidencia.
*   `-A <num>, --after-context <num>`: Muestra `num` líneas de contexto después de cada coincidencia.
*   `--type <tipo>`: Busca solo en archivos de un tipo específico (ej. `--type=py` para Python).
*   `--exclude-type <tipo>`: Excluye archivos de un tipo específico.
*   `-g <globo>, --glob <globo>`: Incluye o excluye archivos que coinciden con un patrón glob.
*   `-U, --multiline`: Habilita la búsqueda de patrones que abarcan varias líneas.
*   `-z, --search-zip`: Busca dentro de archivos comprimidos (gzip, xz, lzma, bzip2, brotli, zstd).
*   `--json`: Imprime los resultados en formato JSON.
*   `-h, --help`: Muestra el mensaje de ayuda.

## Ejemplos de Uso

*   **Búsqueda básica de un patrón:**
    ```bash
    rg "mi_patron"
    ```
    Busca "mi_patron" en el directorio actual y sus subdirectorios.

*   **Búsqueda insensible a mayúsculas y minúsculas:**
    ```bash
    rg -i "error" logs/
    ```
    Busca "error" (ignorando mayúsculas/minúsculas) en el directorio `logs/`.

*   **Buscar una frase literal (no regex):**
    ```bash
    rg -F "User Name" ./src
    ```
    Busca la frase literal "User Name" en el directorio `src/`.

*   **Mostrar 3 líneas de contexto alrededor de cada coincidencia:**
    ```bash
    rg -C 3 "mi_funcion"
    ```
    Busca "mi_funcion" y muestra 3 líneas antes y después de cada coincidencia.

*   **Buscar solo en archivos Python:**
    ```bash
    rg --type py "import os"
    ```
    Busca "import os" solo en archivos Python.

*   **Excluir el directorio `node_modules`:**
    ```bash
    rg "TODO" --glob '!node_modules/**'
    ```
    Busca "TODO" excluyendo el directorio `node_modules`.

*   **Listar solo los nombres de los archivos que contienen una coincidencia:**
    ```bash
    rg -l "FIXME"
    ```
    Muestra los nombres de los archivos que contienen la palabra "FIXME".

*   **Búsqueda multilínea para un bloque de código:**
    ```bash
    rg -U 'function\\s+myFunction\\s*\\([^)]*\\)\\s*\\{[^}]*\\}'
    ```
    Busca una definición de función JavaScript/TypeScript que abarque varias líneas.
