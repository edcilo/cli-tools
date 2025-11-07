# `iftop`

## Descripción

`iftop` es una herramienta de línea de comandos que muestra el uso del ancho de banda en una interfaz de red en tiempo real. Muestra una lista actualizada de las conexiones de red, ordenadas por el uso actual del ancho de banda, lo que permite identificar rápidamente qué hosts están utilizando más ancho de banda.

## Instalación

```bash
sudo apt install iftop
```

## Sintaxis de Uso

```bash
iftop [opciones]
```

## Opciones Válidas

*   `-i <interfaz>`: Especifica la interfaz de red a monitorear (por ejemplo, eth0, wlan0).
*   `-n`: No resuelve nombres de host (muestra solo direcciones IP).
*   `-N`: No resuelve números de puerto (muestra solo números de puerto).
*   `-p`: Ejecuta en modo promiscuo (captura todo el tráfico).
*   `-P`: Muestra los puertos de origen y destino.
*   `-f <filtro>`: Utiliza un filtro de paquetes (formato pcap) para seleccionar el tráfico a mostrar.
*   `-B`: Muestra el ancho de banda en bytes en lugar de bits.
*   `-F <red/máscara>`: Muestra el tráfico que entra o sale de la red especificada.

## Ejemplos de Uso

*   **Monitorear la interfaz predeterminada:**
    ```bash
    sudo iftop
    ```
    Esto iniciará `iftop` monitoreando la interfaz de red predeterminada.

*   **Monitorear una interfaz específica (por ejemplo, eth0):**
    ```bash
    sudo iftop -i eth0
    ```

*   **Mostrar solo direcciones IP (sin resolución de nombres de host):**
    ```bash
    sudo iftop -n
    ```

*   **Mostrar puertos de origen y destino:**
    ```bash
    sudo iftop -P
    ```

*   **Monitorear el tráfico en bytes por segundo:**
    ```bash
    sudo iftop -B
    ```
