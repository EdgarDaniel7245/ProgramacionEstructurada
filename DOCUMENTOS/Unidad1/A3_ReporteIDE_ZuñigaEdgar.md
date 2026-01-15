# Actividad 3 — Configuración de un Entorno de Desarrollo Integrado (IDE)

**Alumno:** Zuñiga Lugo Edgar Daniel
**Grupo:** 2IRD-G1
**Fecha:** 14 de Enero de 2026
**Unidad:** 1

## 1. IDE seleccionado
- **IDE:** Visual Studio Code (VS Code)
- **Versión:** 1.85 (Estable)
- **Sistema operativo:** Windows 11 (64-bits)

## 2. Justificación
- **Criterio 1: Ligereza y Rendimiento.** A diferencia de entornos pesados como Visual Studio Community o IntelliJ IDEA, VS Code es un editor de código optimizado que consume pocos recursos de RAM, permitiendo un flujo de trabajo fluido en equipos portátiles.
- **Criterio 2: Integración Nativa con Git.** Cuenta con una interfaz gráfica para el control de versiones (Source Control) y una terminal integrada potente, lo que facilita realizar `commits` y gestionar ramas sin salir del editor.
- **Criterio 3: Ecosistema de Extensiones.** Su arquitectura modular permite transformar el editor en un IDE completo para Java y Python simultáneamente mediante plugins oficiales, evitando la necesidad de instalar múltiples programas.

## 3. Requisitos previos
- **Sistema Operativo:** Windows 10 u 11, macOS o Linux (arquitectura x64).
- **Hardware:** Procesador de 1.6 GHz o superior y mínimo 4 GB de RAM (8 GB recomendados).
- **Permisos:** Acceso de administrador para realizar la instalación y modificar las variables de entorno (PATH) del sistema.

## 4. Instalación (paso a paso)
1. **Descarga:** Se accedió al sitio oficial [code.visualstudio.com](https://code.visualstudio.com/) y se descargó el instalador "System Installer" para Windows x64.
2. **Ejecución:** Se ejecutó el archivo `.exe`, aceptando los términos de licencia y seleccionando la ruta de instalación predeterminada.
3. **Configuración del PATH:** Durante el asistente de instalación, se marcaron las casillas críticas:
   - "Agregar 'Abrir con Code' al menú contextual de archivo".
   - **"Agregar a PATH (disponible después de reiniciar)".** Esto es vital para invocar el editor desde la consola.

### 4.1 Verificación
- **¿Cómo comprobé que funciona?** Abrí una terminal de PowerShell y ejecuté el comando `code .`.
- **Evidencia:** El editor se abrió correctamente mostrando la carpeta actual y la pantalla de bienvenida "Get Started", confirmando que las variables de entorno quedaron bien configuradas.

## 5. Configuración inicial
### 5.1 Ajustes básicos
- **Auto Save:** Se activó la opción en `File > Auto Save` para guardar cambios automáticamente tras la edición.
- **Terminal Predeterminada:** Se configuró **Git Bash** como el perfil de terminal por defecto para tener compatibilidad con comandos Unix/Linux dentro de Windows.

### 5.2 Extensiones / plugins

| Extensión/Plugin | Función | Por qué se instaló |
|---|---|---|
| **Extension Pack for Java** | Incluye soporte para lenguaje (Red Hat), depurador y Maven/Gradle. | Esencial para compilar, depurar y ejecutar proyectos de la materia de Programación Orientada a Objetos. |
| **Python** (Microsoft) | Provee IntelliSense (autocompletado), linting y depuración. | Requerido para interpretar scripts `.py` y cuadernos Jupyter. |
| **Spanish Language Pack** | Traduce la interfaz de usuario al español. | Facilita la navegación rápida por los menús de configuración. |
| **GitLens** | Mejora las funciones nativas de Git. | Permite visualizar el historial de cambios línea por línea y autoría del código ("blame"). |

### 5.3 Herramientas adicionales
- **Compilador/Intérprete:** Se verificó la instalación del **JDK 17** (Java Development Kit) y de **Python 3.12** mediante los comandos `java -version` y `python --version` en la terminal integrada.

## 6. Documentación de Git y GitHub
Siguiendo los requisitos de la actividad, se configuró el control de versiones desde cero para gestionar las evidencias de la asignatura. A continuación, se detalla el procedimiento técnico realizado:

### 6.1 Configuración de Identidad y SSH
1.  **Instalación:** Se instaló "Git for Windows" integrando Git Bash.
2.  **Identidad del Usuario:** Se configuraron las credenciales globales para firmar los cambios:
    ```bash
    git config --global user.name "Lola"
    git config --global user.email "lolita18@hotmail.com"
    ```
3.  **Seguridad (SSH):** Para evitar el uso de contraseñas en cada interacción, se generó un par de llaves criptográficas:
    * *Comando:* `ssh-keygen -t ed25519`
    * *Vinculación:* Se copió la llave pública (`id_ed25519.pub`) y se registró en la configuración de GitHub (*Settings > SSH and GPG keys*).

### 6.2 Creación del Repositorio
1.  **Inicialización Local:** Se navegó a la carpeta del proyecto (`ProgramacionEstructurada`) en la terminal integrada de VS Code y se ejecutó:
    ```bash
    git init
    ```
    *Esto creó la carpeta oculta `.git`, inicializando el repositorio local.*

2.  **Conexión Remota:** Se creó un repositorio vacío en GitHub y se vinculó al local mediante el protocolo SSH:
    ```bash
    git remote add origin git@github.com:EdgarDaniel7245/ProgramacionEstructurada.git
    ```

### 6.3 Flujo de Trabajo (Stage, Commit, Push)
Para subir las actividades y documentación, se sigue el ciclo estándar de Git:

1.  **Stage (Preparación):** Se agregan los archivos nuevos o modificados al área de espera.
    ```bash
    git add .
    ```
    *(El punto `.` indica que se agreguen todos los archivos de la carpeta actual).*

2.  **Commit (Confirmación):** Se guarda una "versión" del estado actual con un mensaje descriptivo.
    ```bash
    git commit -m "Descripción de los cambios realizados"
    ```

3.  **Push (Publicación):** Se envían los cambios confirmados a la nube (GitHub).
    ```bash
    git push -u origin main
    ```

## 7. Prueba final (mini-ejercicio)
Se creó un archivo de prueba `HolaMundo.java` para validar el compilador y la ejecución:

```java
public class HolaMundo {
    public static void main(String[] args) {
        System.out.println("Entorno configurado y listo para programar.");
    }
}