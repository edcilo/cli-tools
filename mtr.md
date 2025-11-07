# `mtr`

## Descripción

`mtr` combina la funcionalidad de las herramientas `traceroute` y `ping` en una sola herramienta de diagnóstico de red. Envía paquetes con TTLs bajos para investigar la conexión de red entre el host y un host de destino.

## Instalación

```bash
sudo apt install mtr
```

## Sintaxis de Uso

```bash
mtr [opciones] [hostname]
```

## Opciones Válidas

*   `-r, --report`: Pone a mtr en modo de informe, donde se ejecuta por un número de ciclos y luego imprime estadísticas y sale.
*   `-c COUNT`: Establece el número de pings a enviar.
*   `-s PACKETSIZE`: Establece el tamaño del paquete utilizado para el sondeo.
*   `-n, --no-dns`: No resuelve los nombres de host.
*   `-b, --show-ips`: Muestra tanto los nombres de host como las direcciones IP numéricas.
*   `-i SECONDS, --interval SECONDS`: Especifica el número de segundos entre las solicitudes de eco ICMP.
*   `-4`: Usa solo IPv4.
*   `-6`: Usa solo IPv6.

## Ejemplos de Uso

*   **Iniciar un trazado a un host:**
    ```bash
    mtr google.com
    ```
    Esto iniciará una sesión interactiva de mtr que muestra la ruta y las estadísticas en tiempo real.

*   **Generar un informe de 10 ciclos:**
    ```bash
    mtr -r -c 10 google.com
    ```
    Esto enviará 10 paquetes a cada salto en la ruta y luego imprimirá un resumen.

*   **Usar solo IPv4 y no resolver DNS:**
    ```bash
    mtr -4n google.com
    ```

*   **Establecer el intervalo de ping en 2 segundos:**
    ```bash
    mtr -i 2 google.com
    ```
