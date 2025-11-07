# `btop`

## Descripción

`btop` es un monitor de recursos del sistema en la línea de comandos moderno, estéticamente agradable y rico en funciones. Escrito en C++, es una continuación de `bashtop` y `bpytop`, que ofrece visualización en tiempo real de las estadísticas de uso del procesador, memoria, discos, red y procesos de su máquina.

## Instalación

`btop` se puede instalar en varias distribuciones de Linux utilizando sus respectivos administradores de paquetes. Por ejemplo:

*   **Debian/Ubuntu:**
    ```bash
    sudo apt install btop
    ```
*   **Fedora:**
    ```bash
    sudo dnf install btop
    ```
*   **Arch Linux:**
    ```bash
    sudo pacman -S btop
    ```
*   **macOS (a través de Homebrew):**
    ```bash
    brew install btop
    ```

## Sintaxis de Uso

Una vez instalado, puede iniciar `btop` simplemente escribiendo `btop` en su terminal.

```bash
btop [opciones]
```

## Opciones Válidas

`btop` es altamente interactivo y la mayoría de las opciones se configuran dentro de la interfaz de usuario. Sin embargo, algunas opciones de línea de comandos están disponibles:

*   `-v, --version`: Muestra la versión del programa.
*   `-h, --help`: Muestra el mensaje de ayuda.
*   `--utf-force`: Fuerza el uso de caracteres UTF-8.
*   `--debug`: Inicia en modo de depuración.

Dentro de la interfaz, puede presionar `Esc` o `m` para acceder al menú principal, donde puede configurar opciones, temas de color y más.

## Ejemplos de Uso

*   **Ejemplo de uso básico:**
    Para iniciar el monitor de recursos, simplemente ejecute:
    ```bash
    btop
    ```
    Esto abrirá la interfaz interactiva que muestra una descripción general completa de los recursos de su sistema.

*   **Navegación y filtrado:**
    Una vez dentro de `btop`, puede usar las teclas de flecha y el mouse para navegar. Para filtrar procesos, simplemente comience a escribir el nombre del proceso que desea encontrar.

*   **Enviar una señal a un proceso:**
    1.  Seleccione un proceso de la lista.
    2.  Presione `Shift+t` (SIGTERM), `Shift+k` (SIGKILL) o `Shift+i` (SIGINT) para enviar la señal correspondiente.