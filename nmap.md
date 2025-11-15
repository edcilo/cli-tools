# `nmap`

## Descripción

`nmap` (Network Mapper) es una potente utilidad de línea de comandos de código abierto para la exploración de redes y la auditoría de seguridad. Permite a los administradores de red descubrir dispositivos en su red, identificar puertos y servicios abiertos, y detectar vulnerabilidades. Es ampliamente utilizado por profesionales de la ciberseguridad, administradores de red y hackers para diversos propósitos, incluyendo la creación de mapas de red, la búsqueda de direcciones IP remotas, la obtención de detalles del sistema operativo y software, y la auditoría de estándares de seguridad de servidores.

## Instalación

Nmap está disponible para varios sistemas operativos, incluyendo Linux, Windows y macOS.

**Linux (Debian/Ubuntu):**
```bash
sudo apt update
sudo apt install nmap
```

**Linux (CentOS/Fedora):**
```bash
sudo dnf install nmap
# o
sudo yum install nmap
```

**macOS (Homebrew):**
```bash
brew install nmap
```

**Windows:**
Descarga el instalador (`nmap-<version>-setup.exe`) desde la página oficial de Nmap (nmap.org). El instalador suele incluir la GUI Zenmap y otras herramientas. Nmap para Windows también requiere la biblioteca de captura de paquetes Npcap, que a menudo se incluye en el instalador.

## Sintaxis de Uso

La sintaxis básica para Nmap es:
```bash
nmap [Tipo(s) de Escaneo] [Opciones] {especificación_de_objetivo}
```

**Especificación de Objetivo:**
Puedes especificar objetivos usando nombres de host, direcciones IP o rangos de red.
*   **IP única:** `nmap 192.168.1.1`
*   **Nombre de host:** `nmap example.com`
*   **Múltiples IPs:** `nmap 192.168.1.1,192.168.1.5`
*   **Rango de IP:** `nmap 192.168.1.1-20`
*   **Subred:** `nmap 192.168.1.0/24`
*   **Desde un archivo:** `nmap -iL <nombre_de_archivo_de_entrada>`

## Opciones Válidas

Nmap ofrece una amplia gama de opciones para personalizar los escaneos. Aquí están algunas de las más comunes e importantes:

**Descubrimiento de Hosts:**
*   `-sn` (Ping Scan): Deshabilita el escaneo de puertos, solo realiza el descubrimiento de hosts.
*   `-Pn`: Trata a todos los hosts como online, omitiendo el descubrimiento de hosts. Útil si los hosts bloquean las solicitudes de ping.
*   `-n`: Nunca realiza resolución DNS.
*   `-R`: Siempre resuelve DNS.
*   `--traceroute`: Traza la ruta de salto a cada host.

**Técnicas de Escaneo:**
*   `-sS`: Escaneo TCP SYN (escaneo sigiloso). Este es el tipo de escaneo predeterminado y más popular.
*   `-sT`: Escaneo TCP Connect.
*   `-sU`: Escaneo UDP.
*   `-sV`: Detección de servicio y versión.
*   `-O`: Detección de sistema operativo.
*   `-A`: Escaneo agresivo (habilita la detección de SO, detección de versión, escaneo de scripts y traceroute).

**Especificación de Puertos y Orden de Escaneo:**
*   `-p <rangos de puertos>`: Solo escanea los puertos especificados.
    *   `nmap -p 22 <objetivo>`: Escanea el puerto 22.
    *   `nmap -p 1-100 <objetivo>`: Escanea los puertos del 1 al 100.
    *   `nmap -p 22,80,443 <objetivo>`: Escanea puertos específicos.
    *   `nmap -p U:53,T:21-25,80 <objetivo>`: Escanea el puerto UDP 53 y los puertos TCP 21-25, 80.
*   `-F`: Modo rápido. Escanea menos puertos que el escaneo predeterminado.
*   `-r`: Escanea puertos secuencialmente en lugar de aleatoriamente.

**Salida:**
*   `-oN <archivo>`: Guarda la salida en formato normal en un archivo.
*   `-oG <archivo>`: Guarda la salida en formato "grepable" en un archivo.
*   `-oX <archivo>`: Guarda la salida en formato XML en un archivo.
*   `-v` / `-vv`: Aumenta el nivel de verbosidad.
## Ejemplos de Uso

Aquí hay algunos ejemplos prácticos de comandos `nmap`:

*   **Escaneo básico de un solo host:**
    ```bash
    nmap 192.168.1.1
    ```
    Este comando escaneará la dirección IP especificada en busca de puertos y servicios abiertos.

*   **Escaneo de ping para descubrir hosts activos en una subred:**
    ```bash
    nmap -sn 192.168.1.0/24
    ```
    Esto listará todas las direcciones IP activas en la red 192.168.1.0/24 sin realizar un escaneo de puertos.

*   **Escanear puertos específicos en un objetivo:**
    ```bash
    nmap -p 80,443,22 example.com
    ```
    Esto escanea los puertos 80 (HTTP), 443 (HTTPS) y 22 (SSH) en `example.com`.

*   **Detectar SO y versiones de servicio:**
    ```bash
    nmap -O -sV 192.168.1.100
    ```
    Este comando intenta determinar el sistema operativo (`-O`) y las versiones de los servicios (`-sV`) que se ejecutan en el host objetivo.

*   **Escaneo agresivo:**
    ```bash
    nmap -A 192.168.1.1
    ```
    Esto habilita la detección de SO, la detección de versiones, el escaneo de scripts y el traceroute para un escaneo completo.

*   **Escanear un rango de direcciones IP y guardar la salida en un archivo:**
    ```bash
    nmap -p 1-100 -oN scan_results.txt 192.168.1.1-20
    ```
    Esto escanea los puertos del 1 al 100 en las IPs de 192.168.1.1 a 192.168.1.20 y guarda la salida normal en `scan_results.txt`.

*   **Deshabilitar la resolución DNS para escaneos más rápidos:**
    ```bash
    nmap -n 192.168.1.1
    ```
    Esto evita que Nmap realice búsquedas DNS inversas, lo que puede acelerar el escaneo.

*   **Escaneo UDP:**
    ```bash
    nmap -sU -p 161 192.168.1.50
    ```
    Esto realiza un escaneo UDP en el puerto 161 (SNMP) del objetivo.
