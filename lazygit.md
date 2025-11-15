# `lazygit`

## Descripción

`lazygit` es una interfaz de usuario de terminal (TUI) para Git que simplifica la ejecución de comandos de Git. Permite gestionar repositorios de Git de forma visual e interactiva desde la consola, agilizando tareas como el staging de archivos, la creación de commits, la gestión de ramas y la visualización del historial. Es ideal tanto para principiantes que aprenden Git como para usuarios experimentados que buscan mayor productividad.

## Instalación

La instalación de `lazygit` puede variar según el sistema operativo. A continuación se muestran algunos métodos comunes:

**Ubuntu/Debian:**
```bash
sudo add-apt-repository ppa:lazygit-team/release
sudo apt-get update
sudo apt-get install lazygit
```

**Fedora:**
```bash
sudo dnf copr enable atim/lazygit -y
sudo dnf install lazygit
```

**Arch Linux:**
```bash
sudo pacman -S lazygit
```

**macOS (Homebrew):**
```bash
brew install lazygit
```

**Go:**
```bash
go install github.com/jesseduffield/lazygit@latest
```

## Sintaxis de Uso

Para iniciar `lazygit`, simplemente navega hasta un repositorio de Git en tu terminal y ejecuta el comando sin argumentos:

```bash
lazygit
```

Esto abrirá la interfaz interactiva de `lazygit`, que ocupa toda la ventana de la terminal.

## Opciones Válidas

`lazygit` se utiliza principalmente de forma interactiva, por lo que las opciones de línea de comandos son limitadas. Las más importantes son:

*   `-v`, `--version`: Muestra la versión de `lazygit`.
*   `-h`, `--help`: Muestra el mensaje de ayuda con las opciones disponibles.
*   `-p`, `--path <ruta>`: Abre `lazygit` en un repositorio específico ubicado en la ruta indicada.

Dentro de la interfaz, las operaciones se realizan mediante atajos de teclado. Algunos de los más comunes son:
*   **`flechas`**: Navegar entre paneles y elementos.
*   **`espacio`**: Añadir/quitar un archivo del "staging area".
*   **`a`**: Añadir/quitar todos los archivos del "staging area".
*   **`c`**: Crear un commit.
*   **`p`**: Hacer "pull" de los cambios desde el repositorio remoto.
*   **`P`**: Hacer "push" de los cambios al repositorio remoto.
*   **`q`**: Salir de la aplicación.
*   **`x`**: Abrir el menú de opciones para el panel seleccionado.

## Ejemplos de Uso

*   **Iniciar `lazygit` en el repositorio actual:**
    Navega a la carpeta de tu proyecto que es un repositorio de Git y ejecuta:
    ```bash
    lazygit
    ```

*   **Abrir `lazygit` en un repositorio específico:**
    Si quieres abrir `lazygit` para un proyecto ubicado en `/home/usuario/proyectos/mi-proyecto` sin navegar primero a esa carpeta, puedes usar:
    ```bash
    lazygit -p /home/usuario/proyectos/mi-proyecto
    ```