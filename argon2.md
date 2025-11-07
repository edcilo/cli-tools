# `argon2`

## Descripción

`argon2` es una herramienta de línea de comandos que implementa la función de derivación de claves Argon2, ganadora de la "Password Hashing Competition" (PHC). Está diseñada para ofrecer una seguridad robusta, con una fuerte resistencia contra ataques de fuerza bruta basados en GPU y ataques de canal lateral, lo que la hace ideal para el almacenamiento seguro de contraseñas y la derivación de claves criptográficas.

## Instalación

```bash
sudo apt install argon2
```

## Sintaxis de Uso

```bash
echo -n "contraseña" | argon2 <salt> [opciones]
```

## Opciones Válidas

*   `-i`: Utiliza la variante Argon2i (optimizado contra ataques de canal lateral).
*   `-d`: Utiliza la variante Argon2d (optimizado contra ataques de GPU).
*   `-id`: Utiliza la variante Argon2id (híbrido, recomendado para hashing de contraseñas).
*   `-t <iteraciones>`: Define el coste de tiempo (número de iteraciones).
*   `-m <coste>`: Define el coste de memoria en KiB (kilobytes).
*   `-p <paralelismo>`: Define el número de hilos o lanes a utilizar.
*   `-l <longitud>`: Define la longitud del hash en bytes.
*   `-e`: Muestra el hash en formato codificado estándar (comportamiento por defecto).
*   `-r`: Muestra el hash en formato raw (bytes crudos).
*   `-v`: Muestra la versión de la herramienta.

## Ejemplos de Uso

*   **Crear un hash con una salt específica:**
    ```bash
    echo -n "miContraseñaSecreta" | argon2 "miSaltUnica"
    ```

*   **Usar la variante Argon2id y especificar los costes:**
    ```bash
    echo -n "miContraseñaSecreta" | argon2 "miSaltUnica" -id -t 2 -m 16 -p 1
    ```
    *   `-t 2`: 2 iteraciones.
    *   `-m 16`: 65536 KiB (64 MiB) de memoria.
    *   `-p 1`: 1 hilo de paralelismo.

*   **Generar una salt aleatoria con OpenSSL:**
    ```bash
    echo -n "miContraseñaSecreta" | argon2 $(openssl rand -base64 12) -id
    ```

*   **Generar un hash con una longitud de 64 bytes:**
    ```bash
    echo -n "miContraseñaSecreta" | argon2 "miSaltUnica" -l 64
    ```

*   **Mostrar el hash en formato raw:**
    ```bash
    echo -n "miContraseñaSecreta" | argon2 "miSaltUnica" -r
    ```
