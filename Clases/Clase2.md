# ***Bootstrap***:

Para hablar de bootstrap debemos iniciar hablando de los frameworks, estos son entornos que facilitan el trabajo cuando vamos a haceer la interfaz del usuario, entonces no tenemos que ponernos a definir propiedades CSS porque sencillamente bootstrap nos hace todo el trabajo, nada más es copiar y pegar código. Para poder hacer esto necesitamos primero exportar la libreria de bootstrap y esto lo hacemos con:

```HTML
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-0evHe/X+R7YkIZDRvuzKMRqM+OrBnVFBL6DOitfPri4tjfHxaWutUpFmBp4vmVor" crossorigin="anonymous">
```
Una vez que pegamos este link en nuestro documento HTML, podemos comenzar a trabajar con Bootstrap en nuestro proyecto.

### **Preprocessors:**
 Son como su nomrbe lo indica, preprocesadores, sencillamente vamos a ver que tenemos una forma de hacer código en JS, HTML y CSS, aquí podemos fácilmente ver cómo quedaría nuestro código en los distintos lenguajes, uno muy usado es el [Codepen](https://codepen.io/pen/).

### **LESS:**
Nos encontraremos con archivos .less, en estos archivos podemos encontrar que tienen una sintaxis muy similar a CSS, pero en este caso vamos a tener algunos agregados que nos van a ayudar, cómo por ejemplo es el caso de las variables en nuestro archivo de estilos, así si queremos usar un mismo color que nos gustó, es muy complicado recordar esa misma referencia de color siempre que la queramos usar, entonces es más fácil definir una variable, a esta referenciarle el color que queremos usar y usarla luego siempre que la necesitemos. Uno de esos preprocesadores es [lesscss](lesscss.org)

## **Nota:**
Podemos encontrar mucha información en la página de [w3school](https://www.w3schools.com/).

### **CSS media queries:**
Cuando queremos hacer responsive design, queremos que todo se acomode dependiendo del tamaño de la pantalla

```css
body {
  background-color: red;
}

/* Pantallas de menos de 992px de ancho */
@media screen and (max-width: 992px) {
  body {
    background-color: blue;
  }
}

/* Pantallas de menos de 600px de ancho */
@media screen and (max-width: 600px) {
  body {
    background-color: black;
  }
}
```

con el 

```css
@media screen and(max-width: 992px){
    body{
        background-color: blue;
    }
}
```
Lo que estamos haciendo es que en el momento en que la pantalla sea de un tamaño mayor a 992 píxeles, queremos que el fondo de nuestra aplicación o página web sea de color azul, ya con el segundo hacemos que cuando lleguemos a 600 píxeles, nuestro fondo sea de color negro.
### **Bootstrap grid system:**
Aquí tenemos el caso en el cuál bootstrap nos va a acomodar toda nuestra información en una grilla de 12 columnas, podemos hacer algunas más grandes, otras más pequeñas, pero siempre van a ser 12. Esto lo hacemos por medio de:
```html
<div class='row'>
    <div class='column-sm-3 sq'>col 1<div>
    <div class='column-sm-3 sq'>col 2<div>
    <div class='column-sm-3 sq'>col 3<div>
    <div class='column-sm-3 sq'>col 4<div>
</div>
```
Como vemos en el anterior trozo de código, vamos a tener 4 columnas y cada una va a ocupar un espacio de 3 columnas, esto lo vemos por el 3 después del sm.
### **Selectores:**
Primero debemos saber que existen distintos tipos de selectores, los de tipo, de clase y de ID, como vimos antes, estos también podemos hacerlo por medio del . para las clases, el # para los ID y sin nada para los tipos. Así tenemos:

```css
h1{} //Selector de tipo
.button{} //Selector de clase
#primero{} //Selector de ID
```
Así podemos agrupar las propiedades de cada uno en un selector diferente, podemos agrupar también selectores en uno mismo cuando queremos darle las mismas propiedades a dos cosas así:
```css
//Tenemos un par de elementos, y queremos que los dos tengan 
//el mismo color

<span id='span1'> Hola mundo </span>
<h1> Título de nuestra página </h1>

h1, #span1{
    color: black
}
```
Así, agrupamos nuestros selectores y les damos a ambos la misma propiedad sin tener que repetir propiedades ni nada por el estilo.

Con los selectores no sólo podemos seleccionar algo que queremos, podemos también dar el nombre a una clase y luego seleccionarla; definir una propiedad y luego poder llamarla en algún lugar específico para hacerle un cambio a esa propiedad. O incluso podría definirla como una url y luego usarla en cualquier momento.

Podemos incluso aplicar funciones y condiciones a nuestro código, en estos casos la condición if quedaría como 
```less
if((2 > 1), 0px, 10px)
```
Así si 2 es mayor que 1, va a tomar 0px que es el valor en true, sino pues tomará 10px que es el valor en false.

## **Nota:**
Cualquier cosa no olvidar ir a la documentación, ahí está todo.