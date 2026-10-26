- **Alumno:** Cristian Raul Horopan
- **Bloque:** B0.P01 Casa Prestamo de portatiles con Git y Github
- **Fase / ejercicio:** Fase 0.8
- **Fecha de inicio:** 26/09/2026
- **Fecha de entrega:** 26/09/2026
---
## Qué se pedía

Había que crear desde cero una página web para gestionar el préstamo de portátiles y guardar sus cambios utilizando Git y GitHub. 

## ⌨ Comandos y pasos importantes

- `git --version` — comprobar la versión de Git instalada.
    
- `git config --global user.name` — consultar el nombre del autor de los commits.
    
- `git config --global user.email` — consultar el correo configurado.
    
- `ssh -T git@github.com` — comprobar la conexión SSH con GitHub.
    
- `pwd` — comprobar en qué carpeta estoy.
    
- `git init` — crear un repositorio Git local.
    
- `git branch -M main` — establecer el nombre de la rama principal.
    
- `git status` — comprobar el estado de los archivos.
    
- `git remote add origin DIRECCION_SSH` — conectar el repositorio local con GitHub.
    
- `git remote -v` — comprobar las direcciones del repositorio remoto.
    
- `git add .` — preparar todos los archivos que no estén ignorados.
    
- `git add ruta_del_archivo` — preparar un archivo concreto.
    
- `git diff -- web/index.html` — ver los cambios realizados en la portada.
    
- `git diff --cached --stat` — ver un resumen de los cambios preparados.
    
- `git check-ignore -v` — comprobar qué regla de `.gitignore` excluye un archivo.
    
- `git commit -m "mensaje"` — guardar una versión en el historial local.
    
- `git push` — subir los commits al repositorio remoto.
    
- `git push -u origin main` — realizar la primera subida y configurar el seguimiento de la rama remota.
    
- `git log --oneline` — consultar el historial de versiones.
    
- `git switch --detach CODIGO_PRIMER_COMMIT` — visitar una versión anterior sin modificar el historial.
    
- `git switch main` — volver a la rama principal.
    
- `.gitignore` — indicar qué archivos, como los vídeos MP4, no deben incluirse en Git.
    

## Qué he hecho

Primero preparé el entorno y comprobé la configuración de Git y la conexión con GitHub. Después creé la bóveda `Boveda_HTML_Casa` en Obsidian y organicé las carpetas para separar el proyecto, la bitácora y las grabaciones.

A continuación, creé la página `index.html` con el estado inicial del portátil y abrí la web en el navegador. Inicialicé Git dentro de `01_Proyecto`, creé un repositorio vacío en GitHub y lo conecté mediante SSH.

Después guardé y subí las tres versiones de la web: la página inicial con el portátil disponible, la modificación que lo marca como reservado para mantenimiento y la ampliación con las páginas de normas y contacto y una imagen. También preparé los archivos individualmente y comprobé que los vídeos estuvieran excluidos mediante `.gitignore`.

Por último, consulté el historial, visité la primera versión y regresé a `main` para recuperar la web actual. Durante el proceso fui comprobando los cambios con `git status`, `git diff` y otros comandos de Git.

## Qué me ha fallado y cómo lo he resuelto

Al preparar los archivos para guardarlos en Git, ejecuté el comando `git add web/normas.html`, pero Git mostró el error `fatal: pathspec 'web/normas.html' did not match any files`. El problema estaba relacionado con la ruta o el nombre del archivo que intentaba añadir. Volví a ejecutar el comando y comprobé el estado del repositorio con `git status --short --untracked-files=all` para revisar los archivos preparados y pendientes.
## Respuestas a las preguntas

**1. ¿Por qué hice** `**git init**` **en** `**01_Proyecto**` **y no en la raíz de la bóveda?**

Porque la bóveda sirve para organizar el proyecto y la bitácora en Obsidian, mientras que `01_Proyecto` es la carpeta cuyo historial quiero controlar con Git. Así, las grabaciones quedan fuera del repositorio.

**2. ¿Qué mostró** `**git status**` **antes de** `**add**`**, después de** `**add**` **y después de** `**commit**`**?**

Antes de `add`, mostró los archivos nuevos o modificados sin preparar. Después de `add`, indicó cuáles estaban preparados para el siguiente commit. Después de `commit`, mostró que los cambios guardados ya estaban registrados y que no quedaban cambios pendientes.

**3. ¿Por qué creé un repositorio propio en GitHub y lo conecté con** `**git remote add origin**`**?**

Porque esta práctica de casa es independiente de la del centro. Creé un repositorio nuevo y utilicé `origin` para indicar a Git dónde tenía que subir los commits de este proyecto.

**4. ¿Por qué las páginas nuevas aparecen en** `**git status**` **pero no en** `**git diff -- web/index.html**`**?**

Porque `git status` muestra los archivos nuevos sin seguimiento, mientras que `git diff -- web/index.html` compara los cambios de ese archivo concreto. Las páginas nuevas todavía no están controladas por Git y no forman parte de esa comparación.

**5. ¿Cómo comprobé que los vídeos existen, pero no se van a subir?**

Comprobé que los vídeos estaban en la carpeta `web/videos/` y utilicé `git check-ignore -v` para verificar que la regla `*.mp4` de `.gitignore` los excluía. También comprobé que no aparecían entre los archivos preparados para el commit.

**6. ¿Qué muestra** `**git diff --cached --stat**` **después de preparar los cuatro archivos?**

Muestra un resumen de los cambios preparados. En esta práctica debían aparecer los cuatro archivos de la tercera versión: `index.html`, `normas.html`, `contacto.html` y `imagenes/portatil.png`. Los vídeos no debían aparecer.

**7. ¿Qué cambió al visitar el primer commit y qué recuperé al volver a** `**main**`**?**

Al visitar el primer commit, la web volvió a mostrar el portátil como disponible y desaparecieron la imagen y los enlaces añadidos posteriormente. Al volver a `main`, recuperé la versión actualizada, con el estado de mantenimiento, la imagen y los enlaces. El historial no se borró.

**8. ¿Por qué necesita historial esta web y qué aportaría GitHub si trabajase con otro técnico?**

Porque permite saber qué cambios se hicieron, guardar versiones y recuperar una anterior si algo falla. GitHub permite compartir el repositorio y facilitar la colaboración con otros técnicos.

**9. Si mañana corrigiese una errata en** `**normas.html**`**, ¿qué pasos repetiría y cuáles no?**

Modificaría y guardaría el archivo, comprobaría los cambios con `git status` y `git diff`, prepararía el archivo con `git add web/normas.html`, crearía un commit con `git commit` y subiría los cambios con `git push`. No repetiría `git init` ni `git remote add origin`, porque el repositorio y la conexión ya existen.

## Enlaces

- **Vídeo de esta fase:** https://youtu.be/aJscJNAGQ1I
    
- **Playlist:** https://youtube.com/playlist?list=PLbo_E1s7OQoE&si=NWoIoQaSAknQam7s

## Dudas / a repasar

Me vendría bien repasar la diferencia entre `git add`, `git commit` y `git push`, cómo interpretar las dos columnas de `git status --short` y cómo consultar una versión antigua con `git switch --detach` y regresar después a `main`.