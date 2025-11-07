# `tmux`

## Descripción

`tmux` es un multiplexor de terminal. Te permite crear y gestionar múltiples terminales (o "ventanas") dentro de una única ventana de terminal. Puedes desvincularte de una sesión y volver a vincularte más tarde, manteniendo los procesos en ejecución en segundo plano.

## Instalación

```bash
sudo apt install tmux
```

## Sintaxis de Uso

```bash
tmux [comando] [argumentos]
```

Si se ejecuta sin comandos, `tmux` inicia una nueva sesión.

## Comandos y Opciones Válidas

`tmux` se controla principalmente a través de comandos y atajos de teclado dentro de una sesión.

### Comandos de Línea de Comandos

*   `tmux new -s <nombre-sesion>`: Inicia una nueva sesión con un nombre específico.
*   `tmux attach -t <nombre-sesion>`: Se vincula a una sesión existente.
*   `tmux ls`: Lista las sesiones de `tmux` en ejecución.
*   `tmux kill-session -t <nombre-sesion>`: Termina una sesión específica.
*   `tmux kill-server`: Termina todas las sesiones y el servidor de `tmux`.

### Atajos de Teclado (dentro de una sesión)

El prefijo por defecto es `Ctrl-b`. Después de presionar el prefijo, se presiona la siguiente tecla.

*   `c`: Crea una nueva ventana.
*   `w`: Lista las ventanas.
*   `n`: Se mueve a la siguiente ventana.
*   `p`: Se mueve a la ventana anterior.
*   `&`: Cierra la ventana actual.
*   `%`: Divide el panel actual verticalmente.
*   `"`: Divide el panel actual horizontalmente.
*   `flechas`: Se mueve entre paneles.
*   `d`: Se desvincula de la sesión actual.
*   `[`: Entra en el modo de copia para desplazarse hacia arriba.

## Ejemplos de Uso

*   **Iniciar una nueva sesión llamada "mi-sesion":**
    ```bash
    tmux new -s mi-sesion
    ```

*   **Desvincularse de la sesión:**
    Presiona `Ctrl-b` y luego `d`. El terminal volverá a tu shell normal, pero la sesión de `tmux` seguirá ejecutándose en segundo plano.

*   **Listar las sesiones activas:**
    ```bash
    tmux ls
    ```

*   **Volver a vincularse a la sesión "mi-sesion":**
    ```bash
    tmux attach -t mi-sesion
    ```

*   **Trabajar con paneles:**
    1.  Dentro de `tmux`, presiona `Ctrl-b` y luego `%` para dividir la pantalla verticalmente.
    2.  Presiona `Ctrl-b` y luego `"` para dividir el nuevo panel horizontalmente.
    3.  Presiona `Ctrl-b` y luego las teclas de flecha para moverte entre los paneles.
