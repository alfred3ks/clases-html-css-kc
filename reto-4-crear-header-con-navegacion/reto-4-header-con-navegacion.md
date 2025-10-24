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

Hasta aqui términa el video 2. Seguimos...
