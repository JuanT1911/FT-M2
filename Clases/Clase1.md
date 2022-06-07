# ***DOM***

 Lo que representa en si el DOM es un árbol con rama principal el HTML, sus dos ramas hijas son el head y el body, ya luego se pueden crear más ramas hijas como los divs, meta y todas las demás etiquetas que necesitemos.

# ***CSSOM***

 Es un objeto que representa los estilos asociados al DOM.

# ***Render Tree***

 Es como el resumen de lo anterior, aquí se va a renderizar todo lo que queremos que se vea en pantalla.

# ***Ejecutando JS***

 Pilas con los scripts, porque aquí se va a frenar la ejecución de nuestra página y va a ejecutar el script, si lo hacemos mal pues F, va a parecer que nuestra página se rompió y va a quedar una mala experiencia para el usuario.

### Nota: hay que tener cuidado con el responsive development, esto porque si no tenemos en cuenta esto, una vez que abramos nuestra página en un dispositivo diferente a un computador (Celular o tablet), es posible que nuestra página se vea terriblemente mal y genere una peor experiencia para el usuario

Para poder adaptar el tamaño de nuestra pantalla a otras pantallas más pequeñas podemos usar la etiqueta:

```HTML
   <meta name="viewport" content="width=device-width,initial-scale=1">
```
# ***Selectores***

- **document.getElementsByClassName('nombreDeLaClase'):**

   Va a traer todos los elemento que tengas la clase pasada por argumento.

-  **document.getElementById('nombreDelId'):**

   Va a traer el elemento que tenga ese ID, pero recordemos que sólo va a traer un elemento ya que con ID sólo se puede nombrar a un elemento.

-  **querySelector():**

   Aquí tenemos el caso de un selector que va a servir para ambos casos, para buscar un objeto por ID como por su clase, tenemos que hacer es la separación de ambos casos, esta la hacemos llamando con un punto (**.**) a las cosas que sean clases, y con un númeral (**#**) a las que sean un ID:

   ```HTML
   <div class='PrimeraClase'> <div>
   <meta class='PrimeraClase'> <meta>
   <meta id='PrimerId'> <meta>
   ```

   ```Javascript
   document.querySelector('.PrimeraClase'); //<div class='PrimeraClase'> <div>

   document.querySelector('#PrimerId'); //<meta id='PrimerId'> <meta>
   ```
   Cómo podemos observar, usamos querySelector para llamar a los objetos que tengan la clase 'PrimeraClase', pero tenemos dos objetos y sólo llegó uno, para ser más específicos sólo llamo al primer objeto con esa clase, eso es lo que hace querySelector con las clases, llama al primer objeto con esa clase, sólo al primero.

- **querySelectorAll():**
   
   Aquí tenemos un querySelector() que va a llamar a todos los objetos que tengan una determinada clase, así, entonces:

   ```Javascript
   document.querySelectorAll('.PrimeraClase');

   //NodeList(2)[
   //<div class='PrimeraClase'> <div>
   //<meta class='PrimeraClase'> <div>]
   ```

   Como vemos, aquí nos llamó a los dos objetos que tenían esa misma clase.
   Podemos también usarlo para los ID's pero en este caso nos va a devolver el objeto con su respectivo ID como si fuera una lista, por aquello de los hijos etc, etc, etc.

   Pilas porque también podría llamar a un objeto de la siguiente manera:

   ```Javascript
   document.querySelectorAll('meta');
   
   //NodeList(2)
   //<meta class='PrimeraClase'> <meta>
   //<meta id='PrimerId'> <meta>
   ```

   Como podemos ver, aquí no pusimos ni . ni #, e igualmente nos llamó dos objetos, esto es porque al no poner ni . ni # lo que va a hacer es llamar a todos los **Tags**, en este caso quisimos llamar a los tags meta.

# ***Creación de elementos***

- **document.createElement('elemento'):**
 
   Aquí tenemos la forma de crear un nuevo elemento, un nuevo tag para ser más precisos, aquí haremos un ejemplo de un HTML ya iniciado al que queremos agregarle algo:

   ```HTML
   <html>
      <head>
         <script>
            alert('Inyectando código Javascript');
         </script>
      </head>
      <body>
         <div>
            <p>Holaaa</p>
            <p>Hola</p>
            <p>Chau</p>
         </div>
         <script type="text/javascript">alert('chau');</script>
      </body>
   </html>
   ```

   Resulta que aqui queremos crear un nuevo elemento de tag p, que diga holiii en su texto interior y que esté dentro del div, así que haremos:

   ```Javascript   
   const newDiv = document.createElement('p'); //Creamos el tag p
   
   let div = document.querySelector('div'); //Seleccionamos el div

   newDiv.innerText='Holiii'; // Colocamos el texto al interior del p

   newDiv //<p>Holii</p>

   div.append(newDiv);
   ```

- **objeto.innerText='texto':**

   Aquí tenemos el caso en que una vez que creamos un objeto, queremos darle texto interior, por eso se llama innerText, únicamente es el texto, ya que podríamos también añadirle alguna característica del tipo HTML, pero eso lo veremos más adelante.

-  