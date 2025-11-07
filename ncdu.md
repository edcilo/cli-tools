# `ncdu`

## Descripción

`ncdu` (NCurses Disk Usage) es una herramienta de análisis de uso de disco con una interfaz de ncurses. Proporciona una forma rápida de ver qué directorios están consumiendo más espacio en disco.

## Instalación

```bash
sudo apt install ncdu
```

## Sintaxis de Uso

```bash
ncdu [opciones] [directorio]
```

## Opciones Válidas

*   `-h, --help`: Muestra un mensaje de ayuda.
*   `-v, -V, --version`: Muestra la versión de ncdu.
*   `-x, --one-file-system`: No cruza los límites del sistema de archivos.
*   `--exclude PATTERN`: Excluye archivos que coincidan con el patrón.
*   `-o FILE`: Exporta los datos a un archivo en lugar de mostrar la interfaz.
*   `-f FILE`: Importa los datos desde un archivo previamente exportado.
*   `-q`: Modo silencioso, útil para conexiones lentas.
*   `-r`: Modo de solo lectura.

## Ejemplos de Uso

*   **Analizar el directorio actual:**
    ```bash
    ncdu
    ```
    Esto escaneará el directorio actual y mostrará los resultados en la interfaz de ncdu.

*   **Analizar un directorio específico:**
    ```bash
    ncdu /home/usuario
    ```
    Esto escaneará el directorio `/home/usuario`.

*   **Analizar el directorio raíz sin cruzar sistemas de archivos:**
    ```bash
    ncdu -x /
    ```
    Esto es útil para ver el uso del disco del sistema de archivos principal sin incluir puntos de montaje.

*   **Exportar los resultados a un archivo:**
    ```bash
    ncdu -o /tmp/disk-usage.gz /
    ```
    Esto escaneará el directorio raíz y guardará los resultados en un archivo comprimido.

*   **Leer los resultados desde un archivo:**
    ```bash
    ncdu -f /tmp/disk-usage.gz
    ```
    Esto cargará los datos del archivo especificado, lo cual es mucho más rápido que volver a escanear.
