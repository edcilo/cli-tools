# `navi`

## Descripción

`navi` es una herramienta de cheatsheet interactiva para la línea de comandos. Te permite navegar a través de cheatsheets (chuletas) y ejecutar comandos sin necesidad de recordar la sintaxis exacta. Puedes buscar comandos de forma interactiva y ver los argumentos que puedes usar.

## Instalación

La forma más común de instalar `navi` es a través de `brew`:
```bash
brew install navi
```
También puedes instalarlo clonando el repositorio y compilando desde la fuente.

## Sintaxis de Uso

Para iniciar la herramienta interactiva:
```bash
navi
```

Para buscar un comando específico:
```bash
navi query <texto_a_buscar>
```

Para ejecutar el comando seleccionado:
```bash
navi <subcomando> [opciones]
```

## Opciones Válidas

*   `query <texto>`: Busca un comando en las cheatsheets.
*   `repo add <repositorio>`: Añade una nueva cheatsheet desde un repositorio git.
*   `repo browse`: Muestra los repositorios de cheatsheets disponibles.
*   `--help`: Muestra el mensaje de ayuda.
*   `--version`: Muestra la versión de navi.

## Ejemplos de Uso

*   **Iniciar la búsqueda interactiva:**
    ```bash
    navi
    ```
    Esto abrirá una interfaz interactiva para buscar y seleccionar comandos.

*   **Buscar un comando específico:**
    ```bash
    navi query "git commit"
    ```
    Esto mostrará todos los comandos relacionados con "git commit" en las cheatsheets disponibles.

*   **Añadir un nuevo repositorio de cheatsheets:**
    ```bash
    navi repo add denisidoro/cheats
    ```
    Esto descargará las cheatsheets del repositorio especificado.