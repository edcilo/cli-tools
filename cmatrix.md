# `cmatrix`

## Descripción

`cmatrix` es una utilidad de línea de comandos ligera que recrea el icónico efecto visual de "lluvia digital" visto en la serie de películas The Matrix. Muestra un flujo continuo de caracteres que caen, principalmente números y caracteres Katakana, a través de la pantalla de su terminal, imitando el código verde sobre negro de la película. A menudo se utiliza con fines estéticos, como salvapantallas o para añadir un elemento visualmente impactante a una interfaz de línea de comandos.

## Instalación

El proceso de instalación de `cmatrix` varía según su distribución de Linux:

*   **Sistemas basados en Debian/Ubuntu (por ejemplo, Ubuntu, Linux Mint, Pop!_OS):**
    ```bash
    sudo apt update && sudo apt install cmatrix
    ```
*   **Arch Linux/Manjaro:**
    ```bash
    sudo pacman -S cmatrix
    ```
*   **Fedora:**
    ```bash
    sudo dnf install cmatrix
    ```
*   **macOS (usando Homebrew):**
    ```bash
    brew install cmatrix
    ```

## Sintaxis de Uso

Para ejecutar `cmatrix` después de la instalación, simplemente escriba `cmatrix` en su terminal y presione Enter.

```bash
cmatrix [opciones]
```

Para salir de una instancia de `cmatrix` en ejecución, presione `Ctrl+C`. Si `cmatrix` se está ejecutando en modo salvapantallas (`-s`), saldrá automáticamente al presionar cualquier tecla.

## Opciones Válidas

`cmatrix` ofrece varias opciones de línea de comandos para personalizar el efecto de lluvia digital:

*   `-a`: Desplazamiento asíncrono. Hace que cada línea caiga a una velocidad aleatoria, proporcionando una animación más suave.
*   `-b`: Habilita caracteres en negrita para algunas de las gotas que caen.
*   `-B`: Fuerza que todos los caracteres sean en negrita.
*   `-C <color>`: Cambia el color de la matriz. Los colores disponibles incluyen `green` (predeterminado), `red`, `blue`, `white`, `yellow`, `cyan`, `magenta` y `black`.
*   `-l`: Muestra solo letras minúsculas.
*   `-s`: Modo salvapantallas. Sale automáticamente al presionar cualquier tecla.
*   `-u <velocidad>`: Ajusta la velocidad de desplazamiento (0-10, predeterminado 4). Números más bajos resultan en un desplazamiento más rápido.
*   `-r`: Habilita un efecto de color arcoíris.
*   `-U`: Habilita el soporte UTF-8, permitiendo una gama más amplia de caracteres.
*   `-c`: Utiliza caracteres japoneses como se ve en la Matrix original (requiere fuentes apropiadas).
*   `-h`: Muestra un breve mensaje de ayuda con las opciones de línea de comandos.

## Ejemplos de Uso

*   **Ejemplo de uso básico:**
    ```bash
    cmatrix
    ```
    Esto iniciará la lluvia digital con la configuración predeterminada (caracteres verdes, velocidad normal).

*   **Cambiar el color a azul:**
    ```bash
    cmatrix -C blue
    ```
    Esto mostrará la lluvia digital en color azul.

*   **Modo salvapantallas con desplazamiento asíncrono y negrita:**
    ```bash
    cmatrix -s -a -b
    ```
    Esto ejecutará `cmatrix` como salvapantallas con líneas de caída aleatorias y algunos caracteres en negrita.

*   **Lluvia digital arcoíris:**
    ```bash
    cmatrix -r
    ```
    Esto mostrará la lluvia digital con un efecto de color arcoíris.