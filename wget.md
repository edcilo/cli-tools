# `wget`

## Descripción

`wget` es una utilidad de línea de comandos no interactiva para descargar archivos de Internet. Soporta los protocolos HTTP, HTTPS y FTP, y puede reanudar descargas interrumpidas.

## Instalación

`wget` suele venir preinstalado en la mayoría de las distribuciones de Linux. Si no lo tienes, puedes instalarlo con tu gestor de paquetes:

```bash
# En sistemas basados en Debian/Ubuntu
sudo apt install wget

# En sistemas basados en Fedora
sudo dnf install wget

# En macOS con Homebrew
brew install wget
```

## Sintaxis de Uso

```bash
wget [opciones] [URL]
```

## Opciones Válidas

*   `-O <archivo>`: Guarda el archivo descargado con un nombre diferente.
*   `-P <directorio>`: Especifica el directorio donde se guardarán los archivos.
*   `-c, --continue`: Reanuda una descarga interrumpida.
*   `-b, --background`: Inicia la descarga en segundo plano.
*   `-i <archivo>`: Lee las URLs de un archivo de texto para descargar múltiples archivos.
*   `--limit-rate=<velocidad>`: Limita la velocidad de descarga (ej. `--limit-rate=200k`).
*   `-r, --recursive`: Descarga de forma recursiva (útil para directorios).
*   `--mirror`: Crea una copia local de un sitio web.
*   `--convert-links`: Convierte los enlaces para la visualización local.
*   `--page-requisites`: Descarga todos los archivos necesarios para mostrar una página HTML (imágenes, CSS, etc.).
*   `--no-parent`: No asciende al directorio padre al descargar recursivamente.
*   `-q, --quiet`: Suprime la mayoría de la salida de `wget`.
*   `--no-check-certificate`: Ignora la verificación del certificado SSL (usar con precaución).

## Ejemplos de Uso

*   **Descargar un solo archivo:**
    ```bash
    wget https://example.com/file.zip
    ```

*   **Descargar un archivo con un nombre diferente:**
    ```bash
    wget -O newname.zip https://example.com/file.zip
    ```

*   **Reanudar una descarga interrumpida:**
    ```bash
    wget -c https://example.com/largefile.iso
    ```

*   **Limitar la velocidad de descarga a 200 KB/s:**
    ```bash
    wget --limit-rate=200k https://example.com/file.zip
    ```

*   **Descargar en segundo plano:**
    ```bash
    wget -b https://example.com/verylargefile.tar.gz
    ```
    La salida se guardará en `wget-log`.

*   **Descargar múltiples archivos desde un archivo de texto:**
    Crea un archivo `downloads.txt` con una URL por línea y luego ejecuta:
    ```bash
    wget -i downloads.txt
    ```

*   **Crear un espejo de un sitio web para verlo sin conexión:**
    ```bash
    wget --mirror --convert-links --page-requisites --no-parent https://example.com
    ```
