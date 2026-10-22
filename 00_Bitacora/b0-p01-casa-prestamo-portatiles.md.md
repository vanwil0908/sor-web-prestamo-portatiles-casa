
- **Alumno:** Vanessa Wilczek
- **Bloque:** B0 — Prerrequisitos
- **Fase / ejercicio:** Fase 0.8
- **Fecha de inicio:** 22/10/2026
- **Fecha de entrega:** 23/10/2026

---

## 🎯 Qué se pedía

(Dos o tres líneas con tus palabras: qué había que conseguir.)

Debíamos de empezar una bóveda de 0 y crear sus carpetas respectivas, luego teníamos que hacer unas páginas web y 3 commits, y finalmente cambiar de main a nuestro primer commit.
## ⌨️ Comandos y pasos importantes

git --version = Muestra la versión de Git instalada; no instala ni actualiza nada.
git config --global user.name = Muestra el nombre global que Git usará como autor; debe ser el tuyo.
git config --global user.email = Muestra el correo global del autor de los commits; debe ser el tuyo.
ls -l ~/.ssh/id_ed25519 ~/.ssh/id_ed25519.pub = Comprueba que existen los archivos de clave privada y pública; no muestra su contenido.
ssh -T git@github.com = Prueba la autenticación con GitHub. El saludo debe identificar tu usuario; no abre una shell ni sube archivos.
pwd = Muestra la carpeta actual. Contrasta su ruta con la indicada en este paso antes de seguir.
git init = Crea el repositorio local en la carpeta que acabas de comprobar.
git branch -M main = Establece main como nombre de la rama actual.
git status = Muestra la rama main, sin commits todavía, y los archivos iniciales sin seguimiento.
git remote add origin git@github.com:TU-USUARIO/sor-web-prestamo-portatiles-casa.git = Registra origin con la dirección SSH de tu repositorio vacío; todavía no envía archivos.
git remote -v = Muestra las direcciones de lectura y envío de los remotos; origin debe ser el de este proyecto.
git add . = Prepara todos los archivos no ignorados que hay bajo esta carpeta: en esta primera entrega, gitignore, bitácora y portada.
git commit -m = Guarda localmente una versión con los cambios preparados y el mensaje indicado.
git push -u origin main =  Sube main por primera vez a origin y configura su seguimiento para las siguientes subidas.
git diff -- = Compara la portada del disco con el índice: antes de prepararla verás la frase anterior con - y la nueva con +. No compara dos archivos diferentes.
git add web/index.html = Prepara únicamente el contenido actual del archivo indicado para el próximo commit; no sube nada.
git push = Envía los commits pendientes al remoto ya configurado. Comprueba que termina sin errores.
git status --short --untracked-files=all = Muestra el estado abreviado y enumera cada archivo sin seguimiento por su ruta completa, en lugar de agruparlos por carpetas. --short abrevia la salida; --untracked-files=all despliega los nuevos.
git check-ignore -v web/videos/revision-01.mp4 web/videos/revision-02.mp4 = Indica, para cada ruta, el archivo de reglas, su número de línea y el patrón que la ignora. `-v` pide esos detalles.
git status --short --untracked-files=all = Muestra de nuevo qué está preparado y qué sigue sin preparar. Observa el archivo recién seleccionado.
git diff --cached --stat = Resume los cambios preparados en el índice: nombres y estadísticas. --cached selecciona lo preparado; --stat pide un resumen, no todas las líneas.
git log --oneline = Enumera los commits con código abreviado y mensaje, del más reciente al más antiguo. 
git switch --detach CODIGO_PRIMER_COMMIT = Cambia los archivos seguidos a la versión del commit indicado. --detach permite consultar ese commit sin situarte en una rama.
git switch main = Vuelve a la rama main, recuperando sus archivos seguidos.
## 🛠️ Qué he hecho

Yo empecé primero leyendo el PDF, seguí todos los pasos 1 por 1, primero comprobé que tenía Git disponible, que fuera mi identidad y que mi SSH funcionara. A continuación empecé con la bóveda, cree sus carpetas correspondidas y las notas que se necesitabas dentro de las carpetas, en una de ellas hice un .gitignore en git bash, para que no me aparezcan archivos con ciertas extensiones. Luego, hice la primera página web que se pide y luego me asegure de hacer la ruta y el primer git init. Proseguí con hacer el repositorio en Github, asegurándome de que copie el SSH público. A continuación hice el primer commit y push de esa página, y luego en el siguiente apartado me pidieron cambiarla y tuve que volver a hacer un commit y push, luego tuve que crear 2 páginas nuevas y cambiar una cosa en la primera página, y comprobar que con un git status cambie algo. Después tuve que comprobar porque los videos quedaban fuera, una vez hice eso prepare las páginas que cambie, revisando la selección completa, lo guarde y lo subí, me asegure de que la entrega fue terminada. Finalmente se me pidió que localizase la primera entrega y entrara en ella para comprobar que los archivos desaparecían y luego de volver al main, los archivos volvían.

## 🚩 Qué me ha fallado y cómo lo he resuelto

No me salió como tal un error, pero tuve que revisar que escribía bien los comandos, eso fue mi único error.

## 🤔 Respuestas a las preguntas

1. ¿Por qué `git init` se hizo en `01_Proyecto` y no en la raíz de la bóveda?
i haces git init en la raíz de la bóveda, estarías mezclando absolutamente todo en un único repositorio. Al hacerlo dentro de 01_Proyecto, limitas el control de versiones exclusivamente a esa carpeta.

2. ¿Qué mostró `git status` antes de `add`, después de `add` y después de `commit`?
Antes de add: Aparecieron los archivos en rojo bajo la sección "Untracked files"
Después de add: Los archivos pasaron a color verde bajo "Changes to be committed".
Después de commit: El mensaje indicó "nothing to commit, working tree clean".

3. ¿Por qué creaste un repositorio de GitHub propio y lo conectaste con `git remote add origin`?
Se creó para tener una copia de seguridad en la nube que proteja el código ante fallos locales, poder acceder al proyecto desde cualquier dispositivo y establecer la dirección oficial donde se sincronizan los cambios del repositorio.

4. ¿Por qué las páginas nuevas aparecen en `git status` pero no en `git diff -- web/index.html`?
Porque git diff compara los cambios realizados en archivos que **ya están siendo rastreados** por Git con respecto al último commit y si una página es completamente nueva y nunca ha sido añadida con Git add, Git no tiene una versión anterior con la cual compararla, por lo que git diff no mostrará diferencias para ese archivo nuevo.

5. ¿Cómo has comprobado que los vídeos existen pero no se van a subir?
Ejecutando git status, después de realizar el .gitignore.

6. ¿Qué muestra `git diff --cached --stat` después de preparar los cuatro archivos?
El modificador --cached  le pide a Git que muestre los cambios que ya están preparados y  --stat genera un en resumen estadístico, mostrando cuántos archivos se han modificado/añadido.

7. ¿Qué cambia al visitar el primer commit y qué recuperas al volver a `main`?
Pierdes el progreso que hiciste después del primer commit, y cuando vuelvo al main recupero todos esos archivos que no tenia en el primer commit. 

8. ¿Por qué esta web necesita historial? ¿Qué aportaría GitHub si otro técnico trabajase contigo?
El historial te permite saber qué cambió, cuándo y revertir errores al instante. Con otro técnico, GitHub aporta un código centralizado en la nube para trabajar a la vez sin sobrescribirse, usando ramas y revisiones antes de publicar los cambios.

9. Si mañana corriges una errata en `normas.html`, ¿qué pasos repites y cuáles no?
Haría un git add . luego un commit -m con un nombre como "Corección en normas" y luego un push. 
Los pasos que no haría serían un git init, y un git remote add origin.

## 🔗 Enlaces

- **Vídeo de esta fase:** https://youtu.be/sxy1P2vrAvI
- **Playlist:** https://www.youtube.com/playlist?list=PLNpEnGyUHbMs

## 💭 Dudas / a repasar

- (lo que no te ha quedado claro)
Quizás algún comando, que me confunda, o que no sepa del todo bien que hacen.