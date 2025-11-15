# `yt-dlp`

## Descripción

`yt-dlp` es una herramienta de línea de comandos para descargar videos y audio de YouTube y cientos de otros sitios web. Es un fork de `youtube-dl` con características adicionales y correcciones.

## Instalación

Se recomienda instalar `yt-dlp` usando `pip` para obtener siempre la última versión.

```bash
# Usando pip (recomendado)
python3 -m pip install -U yt-dlp

# En macOS con Homebrew
brew install yt-dlp

# Para actualizar yt-dlp a la última versión
yt-dlp -U
```
Para funcionalidades completas como la conversión de formatos, también necesitarás `ffmpeg`.
```bash
# Instalar ffmpeg en Debian/Ubuntu
sudo apt install ffmpeg

# Instalar ffmpeg en macOS con Homebrew
brew install ffmpeg
```

## Sintaxis de Uso

```bash
yt-dlp [opciones] "URL"
```

## Opciones Válidas

*   `-F, --list-formats`: Lista todos los formatos de video y audio disponibles.
*   `-f <id>, --format <id>`: Descarga un formato específico por su ID.
*   `-x, --extract-audio`: Extrae solo el audio del video.
*   `--audio-format <formato>`: Especifica el formato de audio (ej. `mp3`, `m4a`, `wav`).
*   `-o <plantilla>, --output <plantilla>`: Especifica la plantilla para el nombre del archivo de salida (ej. `%(title)s.%(ext)s`).
*   `--write-subs`: Descarga los subtítulos del video.
*   `--sub-langs <idiomas>`: Especifica los idiomas de los subtítulos a descargar (ej. `en`, `es`).
*   `--write-thumbnail`: Descarga la miniatura del video.
*   `--skip-download`: No descarga el video (útil con `--write-thumbnail` o `--write-subs`).
*   `-U, --update`: Actualiza `yt-dlp` a la última versión.
*   `-h, --help`: Muestra el mensaje de ayuda.

## Ejemplos de Uso

*   **Descargar un video en la mejor calidad disponible:**
    ```bash
    yt-dlp "URL_DEL_VIDEO"
    ```

*   **Listar todos los formatos disponibles para un video:**
    ```bash
    yt-dlp -F "URL_DEL_VIDEO"
    ```

*   **Descargar un formato de video y audio específico y fusionarlos:**
    ```bash
    yt-dlp -f "bestvideo+bestaudio" --merge-output-format mp4 "URL_DEL_VIDEO"
    ```

*   **Extraer solo el audio y guardarlo como MP3:**
    ```bash
    yt-dlp -x --audio-format mp3 "URL_DEL_VIDEO"
    ```

*   **Descargar un video con un nombre de archivo personalizado:**
    ```bash
    yt-dlp -o "%(title)s - [%(id)s].%(ext)s" "URL_DEL_VIDEO"
    ```

*   **Descargar una lista de reproducción completa:**
    ```bash
    yt-dlp "URL_DE_LA_LISTA_DE_REPRODUCCION"
    ```

*   **Descargar un video y sus subtítulos en español:**
    ```bash
    yt-dlp --write-subs --sub-langs es "URL_DEL_VIDEO"
    ```

*   **Descargar solo la miniatura del video:**
    ```bash
    yt-dlp --write-thumbnail --skip-download "URL_DEL_VIDEO"
    ```
