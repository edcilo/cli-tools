# `nload`

## Descripción

`nload` es una utilidad de línea de comandos que monitorea el tráfico de red y el uso del ancho de banda en tiempo real. Proporciona una visualización clara y concisa del tráfico entrante y saliente para cada interfaz de red.

## Instalación

```bash
sudo apt install nload
```

## Sintaxis de Uso

```bash
nload [opciones] [dispositivo]
```

## Opciones Válidas

*   `-t <intervalo>`: Establece el intervalo de actualización en milisegundos (por defecto: 500).
*   `-i <unidad>`: Establece la unidad de visualización para el tráfico entrante (por defecto: M).
*   `-o <unidad>`: Establece la unidad de visualización para el tráfico saliente (por defecto: M).
*   `-U <unidad>`: Establece la unidad de visualización para el tráfico total (por defecto: M).
*   `-m`: Muestra múltiples interfaces en una sola pantalla.
*   `-a <segundos>`: Muestra el promedio de tráfico durante los últimos <segundos> (por defecto: 300).
*   `-s <segundos>`: Establece el tamaño del historial de tráfico en segundos (por defecto: 300).

## Ejemplos de Uso

*   **Monitorear todas las interfaces de red:**
    ```bash
    nload
    ```
    Esto mostrará el tráfico en tiempo real para todas las interfaces de red activas.

*   **Monitorear una interfaz específica (por ejemplo, eth0):**
    ```bash
    nload eth0
    ```

*   **Establecer el intervalo de actualización a 1 segundo (1000 ms):**
    ```bash
    nload -t 1000
    ```

*   **Mostrar el tráfico en kilobytes por segundo:**
    ```bash
    nload -i K -o K
    ```

*   **Mostrar múltiples interfaces en una sola pantalla:**
    ```bash
    nload -m
    ```
