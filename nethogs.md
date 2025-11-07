# `nethogs`

## Descripción

`nethogs` es una utilidad de línea de comandos de código abierto que proporciona monitoreo de ancho de banda de red en tiempo real, agrupado por procesos o aplicaciones individuales. A diferencia de la mayoría de las herramientas de monitoreo de red que desglosan el tráfico por protocolo o subred, `nethogs` muestra qué ID de proceso (PID) y programa específico están consumiendo ancho de banda. Esto lo convierte en una herramienta invaluable para identificar aplicaciones que consumen mucho ancho de banda, diagnosticar actividad de red inesperada o simplemente comprender cómo se utilizan los recursos de la red.

`nethogs` funciona rastreando el tráfico de red en interfaces especificadas y correlacionándolo con los ID de proceso examinando el sistema de archivos `/proc`. No depende de un módulo de kernel especial. La interfaz interactiva basada en curses permite a los usuarios ordenar datos, alternar modos de visualización y actualizar estadísticas dinámicamente.

## Instalación

`nethogs` requiere privilegios de root para operar. Antes de instalar, es posible que necesites instalar bibliotecas de desarrollo como `ncurses` para la interfaz basada en texto y `libpcap` para la captura de paquetes a nivel de usuario.

Aquí están los comandos de instalación comunes para varias distribuciones de Linux:

*   **Debian/Ubuntu/Linux Mint:**
    ```bash
    sudo apt install nethogs
    ```
    También es posible que necesites instalar las dependencias primero:
    ```bash
    sudo apt-get install libncurses5-dev libpcap0.8-dev
    sudo apt-get install nethogs
    ```

*   **RHEL/CentOS/Rocky Linux/AlmaLinux:**
    Normalmente, primero debes habilitar el repositorio EPEL y luego instalar `nethogs`.
    ```bash
    sudo yum install epel-release
    sudo yum install nethogs
    ```

*   **Fedora:**
    ```bash
    sudo dnf install nethogs
    ```

*   **Arch Linux:**
    ```bash
    sudo pacman -S nethogs
    ```

## Sintaxis de Uso

```bash
sudo nethogs [opciones] [interfaz]
```

## Opciones Válidas

*   `-d <segundos>`: Establece la tasa de actualización (por ejemplo, cada 3 segundos). La tasa de actualización predeterminada es 1 segundo.
*   `-t`: Modo de rastreo (vuelca la salida a la salida estándar en lugar de la interfaz interactiva). Útil para scripting o registro.
*   `-V`: Muestra la información de la versión.
*   `-h`: Muestra el mensaje de ayuda.

## Ejemplos de Uso

*   **Uso básico (monitorear todas las interfaces activas):**
    ```bash
    sudo nethogs
    ```
    Este comando iniciará `nethogs` y comenzará automáticamente a monitorear el uso del ancho de banda en las interfaces de red predeterminadas.

*   **Monitorear una interfaz de red específica:**
    ```bash
    sudo nethogs eth0
    ```
    Reemplaza `eth0` con la interfaz de red deseada (por ejemplo, `wlan0`, `enp0s3`).

*   **Monitorear múltiples interfaces de red:**
    ```bash
    sudo nethogs eth0 wlan0
    ```

*   **Establecer la tasa de actualización en 5 segundos:**
    ```bash
    sudo nethogs -d 5
    ```

*   **Modo de rastreo para scripting:**
    ```bash
    sudo nethogs -t
    ```

## Controles Interactivos (mientras `nethogs` está en ejecución)

Cuando `nethogs` se está ejecutando en su modo interactivo, puedes usar los siguientes atajos de teclado:

*   `m`: Cambia entre los modos de visualización para las unidades de ancho de banda (KB/s, KB, B, MB, MB/s, GB/s).
*   `r`: Ordena los procesos por ancho de banda recibido (descarga).
*   `s`: Ordena los procesos por ancho de banda enviado (subida).
*   `q`: Sale de la aplicación.
*   `K`: Intenta terminar el proceso seleccionado (usar con extrema precaución).
*   `d`: Alterna la visualización de las columnas de ancho de banda recibido, enviado y total.
*   `l`: Alterna la visualización de las direcciones IP locales/remotas y los puertos para las conexiones.
*   `b`: Muestra el nombre base del programa.
