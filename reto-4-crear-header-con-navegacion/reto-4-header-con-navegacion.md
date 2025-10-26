### Reto 4: Header con navegación:

Este reto comienza en el minuto 3:08:57 del video 2.

Creamos en el index.html nuestro header:

#### index.html:

```html
<!-- Header -->
<header class="header">
  <!-- Logo de la web -->
  <div class="header__image">
    <!-- OJO añadir atributo title -->
    <img
      src="./assets/app/codeflix.png"
      alt="logo de codeflix"
      title="logo de codeflix"
    />
  </div>
  <!-- Barra de navegación -->
  <nav class="header__nav">
    <ul class="header__nav__list">
      <li class="header__nav__list__item">
        <a class="btn hidden" href="#shows">All shows</a>
      </li>
      <li class="header__nav__list__item">
        <a class="btn " href="sign-in.html">Sign in</a>
      </li>
    </ul>
  </nav>
</header>
```

NOTA:
Para el tema de listas de tipo (ol) le podemos agregar el atributo type="" y personalizar el tipo de lista que queremos, que sean letras, numeros romanos etc. La lista (ul) no acepta ese atributo.

Para el tema de la etiqueta img, recordar usar los atributos alt="" y title="".

```html
<ol type="I">
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ol>
```

Tambien debemos saber que un enlace, la etiqueta (a) anchor tags su comportamiento es inline-block, ojo con eso:

```html
<a class="btn" href="sign-in.html">Sign in</a>
```

#### Semantic HTML:

Semantic HTML significa usar etiquetas de HTML que describen claramente el significado y la función del contenido, en lugar de solo su apariencia.

Los motores de búsqueda considerán su contenido como palabras clave importantes para influir en el ranking de la búsqueda de la página (SEO).

Ayuda a los lectores de pantalla a tener más claro la estructura.

Es más sencillo de navegar por el código.

Por ejemplo:
header: indica la cabecera de una página o sección.
nav: define la navegación principal.
main: contiene el contenido principal.
article, section, footer, etc., ayudan a estructurar mejor la información.

Esto mejora la accesibilidad, el SEO y la legibilidad del código.

Como vamos a usar semantic HTMl nuestro banner lo metemos dentro de una etiqueta main.

```html
<!-- Contenido -->
<main>
  <!-- Banner -->
  <section class="banner">
    <!-- Aqui metemos la imagen de fondo -->
    <div class="banner__image"></div>
    <div class="banner__content">
      <h1>Unlimited movies, TV shows; and more</h1>
      <h2>Watch anywhere. Cancel anytime.</h2>
      <p>Ready to watch?</p>
    </div>
  </section>
</main>
```

Hasta aquí términa el video 2. Seguimos...

El reto 4 continua en el video 3.

NOTA:
Cuando queramos fijar un header podemos usar la propiedad position fixed junto con el z-index con unvalor alto, muchas webs vemos valores altos, por ejemplo 9999. Tambien debemos usar la propiedad top: 0 para fijar ese header arriba completamente.

```css
/* Fijamos el header arriba */
position: fixed;
/* Usamos un valor asi nos aseguramos que siempre este arriba */
z-index: 999;
/* Lo fijamos arriba */
top: 0;
```

Tambien cuando usamos este tipo de posicionamiento el contenido siguiente sube y ocupa el espacio liberado por que tiene position fixed, para hacer que baje bastara con darle un margin-top del alto del header.

Tambien tenemos position:stycky. Este es un nuevo posicionamiento que tenemos, es muy parecido al anterior solo que el header no pieder su posicion, tambien necesitamos darle un z-index y top.

Tema imagenes:

Cuando estemos trabajando con imagenes, lo mas comun es asignarle a la etiqueta imagen un width del 100% y al contener padre asiganer el valor en pixel que queramos. Lo vemos en la imagen del header.

Para el tema de botones, como es un elemento que se puede usar en diferentes partes de la web, haremos los estilos en un archivo independiente, alla donde nos haga falta llamaremos esa hoja de estilos. Eso suele hacerse para css reusable. Asi no repetimos estilos.

Diferencias entre display:none | visibility:hidden:

display: none → El elemento no se muestra ni ocupa espacio en la página. Es como si no existiera en el layout.
visibility: hidden → El elemento no se ve, pero sigue ocupando su espacio en el layout (como si fuera invisible).

#### Flexbox:

Flexbox (Flexible Box Layout) es un modelo de diseño en CSS que facilita crear estructuras responsivas y alineaciones precisas sin usar floats ni posicionamientos complicados. Permite controlar fácilmente la dirección, el tamaño, la alineación y la distribución del espacio entre los elementos de un contenedor, ajustándose automáticamente al tamaño del contenedor o pantalla.

Vamos a poner las clases para el header y components:

#### header.css:

```css
.header {
  background-color: var(--main-bg-color);
  /* Fijamos el header arriba */
  /* position: fixed; */
  position: sticky;
  /* Usamos un valor asi nos aseguramos que siempre este arriba */
  z-index: 999;
  /* Lo fijamos arriba */
  top: 0;
  /* Aplicamos flex-box */
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  padding: 20px 15px;
}

/* Estilos al contenedor de la imagen */
.header__image {
  width: 120px;
}

/* Estilos de la imagen */
.header__image img {
  width: 100%;
}

/* Estilos de los enlaces de nav */
.header .header__nav .header__nav__list {
  list-style: none;
}

.header__nav__list .header__nav__list__item a {
  text-decoration: none;
}
```

#### components.css:

```css
/* Estilos de botones */
.btn {
  color: var(--main-text-color);
  background-color: var(--main-brand-color);
  padding: 10px;
  border-radius: 5px;
  border: 1px solid var(--main-brand-color);
}

/* Ocultar elementos */
.hidden {
  display: none;
  /* visibility: hidden; */
}
```

Como ya sabemos como usar flexbox aprovechamos y se lo aplicacmos al banner:

#### banner.css:

```css
/* Contenedor padre */
.banner {
  /* Unidad relativa al alto del la pantalla */
  height: 75vh;
  text-align: center;
  /* este es necesario para poder dar position absolute a la imagen */
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}
```

Hasta aquí el reto 4, video 3 minuto: 2:37:43 Seguimos...
