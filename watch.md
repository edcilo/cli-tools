# `watch`

## Descripción

`watch` es una utilidad de Linux que ejecuta repetidamente un comando y muestra su salida en pantalla completa, permitiéndote monitorear cambios a lo largo del tiempo. Por defecto, se actualiza cada 2 segundos.

## Instalación

`watch` suele venir preinstalado en la mayoría de las distribuciones de Linux. Si no lo tienes, puedes instalarlo con tu gestor de paquetes:

```bash
# En sistemas basados en Debian/Ubuntu
sudo apt install procps

# En sistemas basados en Fedora
sudo dnf install procps-ng
```

## Sintaxis de Uso

```bash
watch [opciones] <comando>
```

## Opciones Válidas

*   `-n <segundos>, --interval <segundos>`: Especifica el intervalo de actualización en segundos (por defecto es 2).
*   `-d, --differences`: Resalta las diferencias entre actualizaciones sucesivas.
*   `-g, --chgexit`: Sale de `watch` tan pronto como la salida del comando cambia.
*   `-t, --no-title`: Oculta el encabezado que muestra el intervalo, el comando y la hora actual.
*   `-h, --help`: Muestra el mensaje de ayuda.

## Ejemplos de Uso

*   **Monitorear la fecha y hora actuales:**
    ```bash
    watch date
    ```
    Muestra la fecha y hora actuales, actualizándose cada 2 segundos.

*   **Monitorear `ls -l` cada 5 segundos:**
    ```bash
    watch -n 5 "ls -l"
    ```
    Lista el contenido del directorio actual en formato largo cada 5 segundos.

*   **Resaltar diferencias en el uso de memoria:**
    ```bash
    watch -d free -m
    ```
    Muestra el uso de memoria en megabytes y resalta los cambios entre actualizaciones.

*   **Salir cuando la salida cambia:**
    ```bash
    watch -g "ls -l my_file.txt"
    ```
    `watch` se cerrará tan pronto como la información de `my_file.txt` cambie.

*   **Monitorear procesos de Apache sin encabezado:**
    ```bash
    watch -t "ps aux | grep apache2"
    ```
    Muestra los procesos relacionados con `apache2` sin el encabezado de `watch`.
