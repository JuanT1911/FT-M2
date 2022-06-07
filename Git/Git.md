<img src="gitcommands.jpg">

# **Git:**
 ## ***git reset vs git rm***

  Tenemos aquí un par de opciones para "volver en el tiempo" pero debemos tener cuidado, primero veremos el caso del git rm.
 ### ***git rm:***
  Aquí debemos tener en cuenta que podemos usar:
  ### **git rm --cached:**
   Aquí una vez que usamos este comando, los archivos serán eliminados de git y del staging, pero los mantiene en el disco duro, es como si le dijeramos que queremos reversar el git add, sencillamente los archivos pasan de tracked a untracked.

    git rm -cached
  ### **git rm --force:**
   En este nuevo caso, los archivos serán eliminados de git y del disco duro, pero como git siempre guarda como una "copia de seguridad" de todo, podemos igualmente regresar en el tiempo y recuperar los archivos, pero se necesitaran comandos un poco más avanzados.

    git rm --force
 ### ***git reset:***
  Para este comando tenemos tres posibilidades:
  ### **git reset --soft:**
   Es la manera más segura de volver en el tiempo, aquí sencillamente volveremos a una versión anterior pero guardando los cambios que tenemos en el staging, pudiendo acceder a estos por medio de un commit anterior.

    git reset --soft
  ### **git reset --hard:**
   Aquí tenemos que tener más cuidado, es la opción más usada pero la más peligrosa también, aquí literal si la usamos, nos va a devolver a una versión anterior, pero se van a borrar todos los cambios que pudiesemos haber hecho antes.

    git reset --hard
  ### **git reset HEAD:**
   Con este comando podemos hacer una reversión de los cambios que tenemos en el staging, así, no eliminamos ningún documento ni nada por el estilo, lo único que hacemos es devolver los archivos del staging a nuestra área de trabajo y así podemos actualizar los documentos para volverlos a commitear.

    git reset HEAD
 ## ***git log:***
  Este comando lo usamos para ver todos los cambios y su respectivo número de referencia a esos cambios:
  ### **git log --stat:**
   Por medio de este comando podemos ver no sólo los distintos commits que se hicieron al repositorio sino también en que han cambiado en sentido de bits el uno del otro. Es como un detallado.

    git log --stat
 ## ***git show:***
  En este caso podremos encontrar todos los cambios que se hicieron dentro de los archivos de texto plano, lo que se eliminó y lo que se colocó.
   
    git show
# **GitHub:**

 Aquí tenemos el repositorio remoto donde van a estar almacenados todos los archivos que queremos usar y compartir con otras personas, principalmente usado cuando trabajamos con más personas en un mismo proyecto. A continuación veremos algunos comandos para trabajar con git y github.
 ## **Comandos:**
### **git add:**
  Este comando es bien conocido porque por medio de este vamos a subir los archivos que queremos al staging, podemos usar el . para subir todos los archivos o el nombre de archivo para sólo subir ese archivo. 

    git add .
    git add <file>
 ### **git commit:**
  Por medio de este comando vamos a commitear los archivos que ya tenemos en el área de staging, aquí ya pasan a estar en el repositorio local, o sea que ya podemos tener el versionado de nuestro proyecto y ver las distintas versiones con los cambios y todo lo que se hizo. No debemos olvidar usar el -m y añadir el comentario de lo que se hizo ya que es una buena práctica.

    git commit -m "Comentario"
 ### **git push:**
  Aquí se viene la unión entre git y github, una vez que ya tenemos comiteados neustros cambios, vamos a subir nuestros cambios a github, esto lo hacemos por medio del comando git push, esto nos va a pushear o empujar los documentos a github y todas las personas en nuestro proyecto van a poder ver los cambios que hemos realizado.

    git push
    git push <url>
 ### **git fetch:**
  Cuando alguna persona hace una actualización al proyecto y nosotros queremos traer esa actualización al repositorio local (PILAS, al repositorio LOCAL, no al directorio de trabajo) usar git fetch para esa actualización.

    git fetch
 ### **git merge:**
  Con este comando haremos que las actualizaciones que están en el repositorio local pasen al directorio de trabajo, es copiar los archivos o borrar los que el otro colaborador borró.

    git merge
 ### **git pull:**
  Así como con push mandabamos los cambios al repositorio remoto, aquí lo que estamos haciendo es trayendo los cambios del repositorio remoto al directorio de trabajo y al repositorio local, es como si estuvieran combinados git fetch y git merge en un sólo comando.

    git pull  
 ### **git commit -am:**
  Con este comando vamos a hacer el git add y el git commit en una misma líne de código, esto lo hacemos con archivos a los que se les hizo un git add previamente, o sea que con archivos nuevos no va a funcionar, en esos casos debemos hacer primero el git add y luego si git commit:

    git commit -am "Comentario"
 ## **Ramas:**
  ### **Creación de ramas:**
   Para crear ramas vamos a usar el comando 

    git branch <branch name>
   De esta manera tendremos una nueva rama llamada "branch name", pero igualmente en principio estaremos trabajando en la rama master. Para cambiar esto vamos a usar el comando

    git checkout <branch name>
   Aquí podremos encontrar que estamos trabajando en la rama "branch name".Si hacemos git log en este punto, vamos a ver que el HEAD igualmente va a estar apuntando a cabecera y a master, pero si hacemos un cambio, luego commiteamos el cambio y hacemos git log de nuevo, veremos que ahora si el HEAD va a estar apuntando a la nueva.
   