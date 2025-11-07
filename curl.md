# curl

`curl` es una potente herramienta de línea de comandos y una biblioteca (libcurl) para transferir datos desde o hacia un servidor utilizando una amplia gama de protocolos. Es ampliamente utilizada en scripts, aplicaciones y para depuración de red.

### ¿Qué es `curl`?

`curl` (Client URL) es una utilidad que permite realizar transferencias de datos con URLs. Soporta diversos protocolos como HTTP, HTTPS, FTP, FTPS, SCP, SFTP, SMB, SMBS, TELNET, DICT, FILE, GOPHER, IMAP, IMAPS, LDAP, LDAPS, MQTT, POP3, POP3S, RTMP, RTMPS, RTSP, SMTP, SMTPS, TFTP, WS y WSS. En esencia, `curl` permite interactuar con servidores y recuperar o enviar datos de manera eficiente.

### Características y Usos Principales

*   **Transferencia de datos**: Descarga y sube archivos desde y hacia servidores.
*   **Soporte de protocolos**: Maneja una gran variedad de protocolos de red.
*   **Interacción con APIs**: Permite realizar solicitudes HTTP (GET, POST, PUT, etc.) para interactuar con servicios web y APIs.
*   **Inspección de contenido**: Puede mostrar el contenido sin procesar de una página web o los encabezados de respuesta.
*   **Reanudación de transferencias**: Soporta la reanudación de descargas y subidas de archivos.
*   **Manejo de cookies**: Permite enviar y almacenar cookies.

### Sintaxis Básica

La sintaxis fundamental de `curl` es:
`curl [OPCIONES] [URL]`

Si no se especifica un protocolo en la URL, `curl` lo interpretará como HTTP por defecto.

### Ejemplos de Uso Comunes

Aquí tienes algunos ejemplos prácticos de cómo usar `curl`:

*   **Mostrar el contenido de una página web**:
    ```bash
    curl https://ejemplo.com
    ```
    Este comando envía una solicitud GET y muestra el código fuente HTML de la página en la terminal.

*   **Guardar la salida en un archivo**:
    ```bash
    curl -o salida.html https://ejemplo.com
    ```
    La opción `-o` permite especificar un nombre de archivo para guardar la salida.
    También puedes usar `-O` (mayúscula) para guardar el archivo con el mismo nombre que el remoto en el directorio actual.

*   **Seguir redirecciones**:
    ```bash
    curl -L http://ejemplo.com
    ```
    La opción `-L` hace que `curl` siga cualquier redirección HTTP que el servidor pueda enviar.

*   **Realizar una solicitud POST con datos**:
    ```bash
    curl -X POST -d "param1=valor1&param2=valor2" https://api.ejemplo.com/recurso
    ```
    La opción `-X POST` especifica el método POST, y `-d` se usa para enviar datos. `curl` añade automáticamente la cabecera `Content-Type: application/x-www-form-urlencoded`.

*   **Enviar datos JSON en una solicitud POST**:
    ```bash
    curl -X POST -H "Content-Type: application/json" -d '{"clave": "valor"}' https://api.ejemplo.com/recurso
    ```
    Aquí se usa `-H` para especificar la cabecera `Content-Type` como `application/json`.

*   **Mostrar solo los encabezados de respuesta**:
    ```bash
    curl -I https://ejemplo.com
    ```
    La opción `-I` (o `--head`) realiza una solicitud HEAD y muestra solo los encabezados HTTP.

*   **Verificar la versión de `curl`**:
    ```bash
    curl --version
    ```
    Este comando muestra la versión de `curl` instalada y los protocolos compatibles.

### Dónde Encontrar Más Documentación

Para una documentación más detallada y completa, se recomienda consultar:

*   **"The book: Everything curl"**: Un libro gratuito y exhaustivo que cubre todos los aspectos de `curl` y `libcurl`.
*   **Página `man` de `curl`**: En sistemas Linux/Unix, puedes acceder al manual completo ejecutando `man curl` en la terminal.
*   **Documentación oficial de `curl`**: El sitio web oficial de `curl` (curl.se) ofrece una sección de documentación con tutoriales y referencias.