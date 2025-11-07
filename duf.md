# `duf`

## Descripción

`duf` es una utilidad de línea de comandos para visualizar el uso y el espacio libre en disco de una manera más organizada y visualmente atractiva que los comandos tradicionales `df` y `du`.

## Instalación

```bash
sudo apt install duf
```

## Sintaxis de Uso

```bash
duf [opciones] [ruta]
```

## Opciones Válidas

*   `--all`: Muestra todos los sistemas de archivos, incluyendo los duplicados y los inaccesibles.
*   `--hide-fs <filesystem>`: Oculta sistemas de archivos específicos.
*   `--json`: Muestra la salida en formato JSON.
*   `--only-fs <filesystem>`: Muestra solo los sistemas de archivos especificados.
*   `--output <archivo>`: Escribe la salida en un archivo.
*   `--sort <criterio>`: Ordena la salida por tamaño, uso, etc.
*   `--width <numero>`: Establece el ancho de la salida.

## Ejemplos de Uso

*   **Mostrar el uso del disco para todos los puntos de montaje:**
    ```bash
    duf
    ```

*   **Mostrar el uso del disco para directorios específicos:**
    ```bash
    duf /home /var
    ```

*   **Mostrar también los inodos:**
    ```bash
    duf --inodes
    ```

*   **Ordenar la salida por tamaño:**
    ```bash
    duf --sort size
    ```

*   **Generar un informe en formato JSON:**
    ```bash
    duf --json
    ```
