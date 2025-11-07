# `ipcalc`

## Descripción

`ipcalc` es una calculadora de direcciones IP para la línea de comandos. Toma una dirección IP y una máscara de red y calcula la dirección de broadcast, la red, la máscara wildcard de Cisco y el rango de hosts.

## Instalación

```bash
sudo apt install ipcalc
```

## Sintaxis de Uso

```bash
ipcalc [opciones] [DIRECCIÓN]/[MÁSCARA]
```

## Opciones Válidas

*   `-n, --nocolor`: No muestra códigos de color ANSI.
*   `-b, --nobinary`: Suprime la salida en formato binario.
*   `-c, --class`: Solo imprime la máscara de conteo de bits de la dirección dada.
*   `-h, --html`: Muestra los resultados como HTML.
*   `-s, --split n1 n2 n3`: Divide en redes de tamaño n1, n2, n3.
*   `-r, --range`: Desagrega el rango de direcciones.

## Ejemplos de Uso

*   **Calcular la información de una red:**
    ```bash
    ipcalc 192.168.1.15/24
    ```
    Esto mostrará la dirección de red, la máscara de red, el rango de hosts y la dirección de broadcast para la red dada.

*   **Usando una máscara de red en formato decimal:**
    ```bash
    ipcalc 192.168.1.15 255.255.255.0
    ```

*   **Mostrar la salida sin los valores binarios:**
    ```bash
    ipcalc -b 192.168.1.15/24
    ```

*   **Dividir una red en subredes:**
    ```bash
    ipcalc 192.168.0.0/24 -s 60 60 120
    ```
    Esto dividirá la red /24 en tres subredes que pueden alojar 60, 60 y 120 hosts respectivamente.
