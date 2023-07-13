# Manual Básico de Git

Git es un sistema de control de versiones distribuido que permite a los equipos trabajar en el mismo proyecto sin pisarse entre ellos. Con Git, puedes rastrear los cambios en tu código, revertir a versiones anteriores y crear ramas separadas para trabajar en nuevas características o solucionar problemas.

Es importante seguir las mejores prácticas de Git:

- **Hacer commits pequeños y frecuentes**: Esto hace más fácil entender qué cambios se hicieron y por qué.
- **Escribir mensajes de commit claros y significativos**: Los mensajes de commit deben describir qué se cambió y por qué.
- **Usar ramas para trabajar en nuevas características o solucionar problemas**: Esto permite trabajar en cambios sin afectar el código de producción hasta que estés listo para fusionarlo.

**Nomenclatura de ramas**: Un buen sistema de nomenclatura para las ramas de Git puede hacer que sea mucho más fácil entender qué está sucediendo en un proyecto. Una convención común es usar categorías como `feature/`, `bugfix/`, o `hotfix/` seguido del nombre del feature o el issue. Por ejemplo, si estás trabajando en un feature para añadir autenticación, podrías llamar a tu rama `feature/authentication`.

**Mensajes de commit**: Los mensajes de commit deben ser claros y descriptivos. Una práctica común es escribir mensajes de commit en el tiempo presente. El mensaje debería empezar con una línea breve (menos de 50 caracteres) que resuma el cambio, seguido de una línea en blanco y luego una descripción más detallada del cambio si es necesario. Por ejemplo:

```
Añade funcionalidad de autenticación

Este commit añade una nueva funcionalidad que permite a los usuarios registrarse e iniciar sesión. Se ha añadido una nueva página de inicio de sesión y un formulario de registro.
```

**Pull Requests**: Los Pull Requests son una característica de muchas plataformas que alojan repositorios Git, como GitHub. Permiten a los desarrolladores solicitar que sus cambios sean incorporados en la rama principal. Los Pull Requests permiten la revisión de código, lo que significa que otros desarrolladores pueden revisar y comentar los cambios antes de que se integren.

Es importante proporcionar toda la información necesaria en la descripción del Pull Request para que los revisores puedan entender qué cambios se han hecho y por qué. Esto incluye cualquier contexto o justificación para los cambios, una descripción de cómo se han probado los cambios y cualquier otro detalle que creas que puede ser útil.

**Rebasing y Merging**: Git ofrece dos formas principales de incorporar cambios de una rama a otra: rebasing y merging. Merging crea un nuevo commit que incorpora los cambios de la otra rama. Rebasing, por otro lado, mueve los cambios de la rama actual para que se apliquen en la punta de la otra rama. Ambos tienen sus usos: merging es a menudo más simple y es una buena opción si quieres mantener un historial explícito de cuando los cambios fueron integrados, mientras que rebasing puede ser una buena opción si quieres mantener un historial de commits más limpio.

**Gitignore**: El archivo `.gitignore` te permite especificar archivos o directorios que Git debe ignorar. Esto es útil para archivos que no deben ser controlados por versiones, como los archivos generados por el sistema, los archivos de log, o los archivos locales de configuración. Un buen archivo `.gitignore` puede ayudar a mantener tu repositorio limpio y ordenado.


Git es una herramienta esencial para cualquier desarrollador. Es un sistema de control de versiones que permite realizar seguimiento de los cambios realizados en un proyecto a lo largo del tiempo. A continuación, te presento un breve manual sobre cómo comenzar a utilizar Git. 

## Instalación

Para instalar Git, puedes seguir las instrucciones en el [sitio web oficial de Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

## Configuración inicial

Una vez que hayas instalado Git, debes configurar tu nombre de usuario y correo electrónico ya que Git agrega esta información a cada commit que realizas.

```
git config --global user.name "Tu Nombre"
git config --global user.email "tunombre@ejemplo.com"
```

## Crear un nuevo repositorio

Para iniciar un nuevo repositorio Git, navega al directorio del proyecto en tu terminal y ejecuta:

```
git init
```

## Realizar un commit

Un commit es un punto en el tiempo que puedes utilizar para volver a un estado anterior de tu código. Para realizar un commit, primero debes agregar los archivos que deseas incluir en el commit con `git add`:

```
git add .
```

Esto agrega todos los archivos en el directorio actual. Si solo deseas agregar un archivo específico, puedes hacerlo así:

```
git add nombreArchivo
```

Luego, puedes realizar un commit de estos archivos con `git commit`:

```
git commit -m "Mensaje del commit"
```

## Clonar un repositorio

Para trabajar en un proyecto existente, puedes clonar su repositorio. Esto crea una copia local del repositorio en tu máquina.

```
git clone https://github.com/usuario/nombre-del-repositorio.git
```

## Git pull

`git pull` se usa para actualizar tu repositorio local con los cambios más recientes del repositorio remoto.

```
git pull origin nombre-de-la-rama
```

Esta es una combinación de dos comandos, `git fetch` y `git merge`. Primero, `git fetch` se conecta al repositorio remoto y descarga cualquier cambio. Luego, `git merge` combina estos cambios con tu repositorio local.

## Git fetch

Si solo quieres ver los cambios del repositorio remoto sin combinarlos con tu repositorio local, puedes usar `git fetch`:

```
git fetch origin
```

## Ver el historial de commits

Para ver el historial de commits, puedes usar `git log`:

```
git log
```

## Ramas

Las ramas te permiten desarrollar funcionalidades aisladas sin afectar a otras ramas. Para crear una nueva rama, puedes utilizar `git branch`:

```
git branch nombreRama
```

Para cambiarte a esa rama, utiliza `git checkout`:

```
git checkout nombreRama
```

## Merging

Una vez que hayas finalizado el desarrollo en una rama, puedes combinarla con tu rama principal (por lo general, la rama `master` o `main`). Para hacer esto, primero debes cambiarte a la rama principal:

```
git checkout master
```

Luego, puedes combinar tu rama de desarrollo:

```
git merge nombreRama
```

## Subir tu código a GitHub

Para subir tu código a GitHub, primero debes crear un nuevo repositorio en GitHub. Luego, puedes conectar tu repositorio local a GitHub con `git remote`:

```
git remote add origin https://github.com/tunombredeusuario/nombreRepositorio.git
```

Luego, puedes subir (push) tus commits a GitHub con `git push`:

```
git push -u origin master
```

## Git diff

`git diff` es una gran herramienta para ver qué ha cambiado en tu código. Esto muestra las diferencias entre tu último commit y los cambios actuales.

```
git diff
```

## Git stash

Si tienes cambios en tu repositorio que no quieres commit, pero necesitas cambiar a una rama diferente, puedes usar `git stash` para guardar tus cambios y aplicarlos más tarde.

```
git stash
```

Cuando quieras volver a aplicar tus cambios, puedes usar `git stash pop`.

## Git reset

Si has realizado un commit y te das cuenta de que has cometido un error, puedes usar `git reset` para deshacer el commit.

```
git reset HEAD~1
```

Ten cuidado con este comando, ya que eliminará permanentemente tu último commit.

Estos son solo algunos de los comandos y operaciones más avanzados que puedes realizar con Git. Como siempre, puedes usar `git help <comando>` para obtener más información sobre un comando específico.


# Flujo Basico

### 1. Clonar un repositorio

Supongamos que existe un repositorio en GitHub que quieres trabajar. Lo primero que debes hacer es clonarlo en tu máquina local:

```bash
git clone https://github.com/usuario/proyecto.git
```

Esto creará un nuevo directorio llamado "proyecto" que contiene todos los archivos del repositorio.

### 2. Actualizar el repositorio (Pull/Fetch)

Antes de empezar a trabajar, debes asegurarte de que tienes la última versión del repositorio. Si otras personas también están trabajando en este proyecto, pueden haber hecho cambios desde la última vez que clonaste el repositorio.

```bash
cd proyecto
git pull origin main
```

Esto actualiza tu repositorio local con los cambios más recientes del repositorio remoto. Si prefieres solo descargar los cambios sin aplicarlos automáticamente, puedes usar `git fetch` en su lugar.

### 3. Modificar un archivo

Ahora puedes empezar a hacer cambios en el repositorio. Por ejemplo, podrías abrir el archivo `readme.md` y agregar algo de texto.

```bash
echo "Esto es una prueba" >> readme.md
```

### 4. Realizar un commit

Después de hacer tus cambios, necesitas realizar un commit para guardar tu progreso.

Primero, debes agregar los archivos que has modificado al área de preparación:

```bash
git add readme.md
```

Luego, puedes hacer el commit de tus cambios:

```bash
git commit -m "Agregué una línea al README"
```

El mensaje que proporcionas con el comando `-m` debe ser una breve descripción de los cambios que has realizado.

### 5. Push a GitHub

Finalmente, puedes subir tus cambios al repositorio remoto en GitHub:

```bash
git push origin main
```

Esto enviará tus cambios al repositorio remoto. Si otras personas han realizado cambios desde tu último `pull`, es posible que debas hacer otro `pull` y resolver cualquier conflicto antes de poder hacer `push`.

Y eso es todo. Has clonado un repositorio, actualizado tu copia local, realizado cambios, y luego subido esos cambios al repositorio remoto. Este es un flujo de trabajo muy común para los desarrolladores que utilizan Git.
