### Reto 9: Crear animaciones y transiciones.

Video 6.

Aquí veremos:

- Open graph,
- Hover selector,
- Transition,
- Animations,
- Gradient.

#### Open graph tags:

Las **Open Graph tags** son etiquetas HTML que se colocan en el `<head>` de una página web y sirven para controlar cómo se muestra el contenido cuando lo compartes en redes sociales (como Facebook, Twitter, WhatsApp, LinkedIn).

En pocas palabras, le dicen a las plataformas qué título, descripción, imagen y otros datos deben mostrar al compartir el enlace, mejorando la vista previa y haciendo el enlace más atractivo.

Aquí tenemos un enlace donde podemos profundizar:

https://ogp.me/

#### index.html:

```html
<!-- Open graph -->
<meta property="og:title" content="Codeflix" />
<meta property="og:description" content="Codeflix website description." />
<meta
  property="og:image"
  content="https://github.com/alfred3ks/clases-html-css-kc/blob/main/codeflix/assets/app/open-graph-codeflix.jpg?raw=true"
/>
<!-- Open graph de twitter -->
<meta property="twitter:card" content="summary" />
```

Para el tema de la imagen, sacar la url de la imagen esta debe ser una ruta absoluta, osea un enlace, un dominio completo, desde el repo podemos buscar la imagen, sobre ella hacer click a copiar la url y lo tendriamos.

En twitter tiene su propia forma de mostrarlo como vemos. Para ver como seria se investiga en la web de X. Tiene varias formas de mostrarlo, este que usamos aquí es el básico.

#### Transitions: Video 6 min 0:44:48.

Las transiciones en CSS son efectos que permiten cambiar de un estilo a otro de manera gradual en lugar de hacerlo de golpe. Se activan cuando ocurre un evento, como pasar el mouse sobre un elemento o cambiar una clase.

En resumen, hacen que las modificaciones visuales (color, tamaño, posición, opacidad, etc.) sean más suaves y animadas.

Vamos a realizar con un hover en los botones de la web de codeflix como implementar transiciones. El css de los botones lo tenemos en components.css.

#### components.css:

```css
/* Estilos de botones */
.btn {
  color: var(--main-text-color);
  background-color: var(--main-brand-color);
  padding: 10px;
  border-radius: 5px;
  border: 1px solid var(--main-brand-color);
  /* transition */
  transition: background-color ease 2s;
}

/* Transiciones: Hover a los botones */
.btn:hover {
  background-color: cadetblue;
}
```

Para este caso de los botones, vamos a hacer que al pasar el raton por encima este haga un hover a otro color, y vemos como al poner las transiciones estas se puden hacer de manera mas suave. La propiedad que tiene un estado inicial y final es el background-color, le ponemos un tiempo que va a durar la transicion y una forma de hacerlo. Existen otras formas de hacer la transicion ease-in, ease-in-out, linear, etc.

Paro video 6 min 1:06:33

NOTA: Si queremos que el hover se aplique solo en dispositivos con raton podemos usar la media queries:

```css
@media (hover: hover) {
  /* Transiciones: Hover a los botones */
  .btn:hover {
    background-color: cadetblue;
  }
}
```

Ya si queremos rizar el rizo lo hacemos todo en la media querie:

```css
/* transition del hover */
@media (hover: hover) {
  .btn {
    transition: background-color easy 0.3s;
  }

  .btn:hover {
    background-color: var(--main-brand-color-light);
  }
}
```

#### Animaciones: Video 6 min 1:15:03

Las animaciones en CSS son efectos que permiten cambiar propiedades de un elemento de forma gradual en el tiempo, sin usar JavaScript. Sirven para crear movimiento o transiciones visuales, como mover un elemento, cambiar colores, tamaños, opacidades o rotaciones. Se definen con `@keyframes` y se aplican con propiedades como `animation-duration`, `animation-name` y `animation-iteration-count`.

Una animación permite que un elemento cambie gradualmete de un estilo a otro.

puedes cambiar tantas propiedades CSS como desees, tantas veces como desees.

NOTA: No todas las propiedades de CSS se pueden hacer transiciones o animaciones. Son propiedades que no tiene estados intermedios Por ejemplo el display, podemos pasar de block a none pero no hay estados interemdios, esta propiedad no se puede hacer transiciones ni animaciones.

Vamos a crear un spinner en la web de codeflix y animares el texto tambien al cargar el banner.

#### banner:

index.html:

```html
<!-- Banner -->
<section class="banner">
  <div class="banner__image"></div>
  <div class="banner__content">
    <h1>Unlimited movies, TV shows, and more</h1>
    <h2>Watch anywhere. Cancel anytime</h2>
    <p>Ready to watch?</p>
  </div>
</section>
```

banner.css:

```css
/* Contenedor hijo 1 */
.banner .banner__content {
  /* Para poder usar usar el z-index debemos dar un position diferente al static*/
  position: relative;
  /* Levantamos el texto */
  z-index: 2;

  /* Animación */
  /* Nombre de la animación */
  /* animation-name: fade-in; */
  /* Duración */
  /* animation-duration: 2s; */
  /* Forma del movimiento (suavizado) */
  /* animation-timing-function: ease; */
  /* Tiempo antes de empezar */
  /* animation-delay: 0s; */
  /* Repeticiones (1 vez) */
  /* animation-iteration-count: 1; */
  /* Dirección: normal, reverse, alternate... */
  /* animation-direction: normal; */
  /* Mantiene el estado final */
  /* animation-fill-mode: forwards; */
  /* Estado de la animación */
  /* animation-play-state: running; */
  /* Version en una sola linea */
  animation: fade-in 5s ease;
}

/* Animaciones del texto de banner */
@keyframes fade-in {
  /* inicio */
  0% {
    opacity: 0;
  }

  /* Final */
  100% {
    opacity: 1;
  }
}
```

Paro video 6 min 1:40:39

#### Spinner:

index.html:

```html
<!-- Creamos el spinner para animaciones -->
<div class="spinner"></div>
```

spinner.css:

```css
.spinner {
  width: 50px;
  height: 50px;
  border: 5px solid crimson;
  border-left-color: blue;
  border-radius: 50%;
  position: absolute;
  top: 25%;
  /* left: 50%; */
  left: calc(50% - 25px);
  z-index: 3;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}
```

Aquí como nuevo vemos la propiedad `transform` la cual nos permite mover cajas dentro del html. Muy interesante.

Descanso. 2:00:00.

#### Gradientes:

Los gradientes en CSS son transiciones suaves entre dos o más colores. En lugar de usar un color sólido, un gradiente mezcla los colores progresivamente, creando efectos como degradados lineales (de arriba a abajo, izquierda a derecha, etc.) o radiales (desde el centro hacia afuera).

Se usan para fondos, botones, textos y elementos decorativos, dando más profundidad y estilo visual a la interfaz.

Vamos a realizar los gradientes en el footer de codeflix.

index.html:

```html
<!-- footer -->
<footer class="footer">
  <p>@2025 <em>Codeflix</em> Website</p>
  <!-- Convencion de BEM para las clases del css -->
  <p class="footer__company">Powered by keepcoding</p>
</footer>
```

Este gradiente lo obtuvimos de la web https://cssgradient.io/

footer.css:

```css
.footer {
  background: radial-gradient(
    circle,
    rgba(255, 0, 0, 1) 0%,
    rgba(20, 14, 14, 1) 100%
  );
}
```

NOTA: Cuando queramos saber si algo que estamos implementando en el proyecto se puede usar en navegadores ir a la web de can i use y comprobarlo.

https://caniuse.com/

#### Imágenes Responsive:

Tenemos la carpeta images-responsive donde pondremos los ejemplos.

Hasta ahora hemos visto crear images con la etiqueta `<img/>`. Ahora veremos como podemos tener las control de las imagenes usando `<pictures></pictures>` y `srcset`.

#### Etiqueta img:

Este seria el caso si tenemos una imagen por medio de la etiqueta `<img/>`:

images-responsive/index.html:

```html
<!-- En esta imagen solo hemos usado la etiqueta img. -->
<!-- img -->
<img
  src="img/docus/docu_1.webp"
  class="docu"
  alt="imagen serpiente documentales"
/>
```

images-responsive/style.css:

```css
/* Estilos a una imagen con etiqueta img */
img.docu {
  /* Propiedad clave para que se adapte la imagen*/
  width: 100%;
  background-color: aqua;
  aspect-ratio: 16/9;
  object-fit: cover;
  object-position: center center;
}
```

Aquí vemos que la propiedad clave para hacer responsive la imagen es el width:100%.

aspect-ratio:
La propiedad aspect-ratio en CSS define la relación de proporción entre el ancho y la altura de un elemento.

object-fit:
Controla cómo se ajusta la imagen dentro de su contenedor, cuando no tiene la misma proporción.
cover → La imagen llena el espacio, puede recortarse.
contain → La imagen se ve completa, pero pueden quedar bordes/vacíos.
fill → Deforma la imagen para rellenar todo.
none → Mantiene tamaño original, puede sobresalir.
scale-down → Usa none o contain, lo que quede más pequeño.

object-position:
Define qué parte de la imagen se alinea o centra dentro del contenedor.
left top: Muestra parte superior izquierda
right bottom: Muestra parte inferior derecha
center center: Centra la imagen (por defecto)
50% 30%: Posición personalizada.

#### Etiqueta picture/source:

Para este caso tenemos las etiquetas `<pictures></pictures>` y `<sourse></sourse>`:

La etiqueta `<picture>` se usa para mostrar diferentes versiones de una imagen según el dispositivo, tamaño de pantalla o tipo de formato, y dentro de ella se usan `<source>` y un `<img>` de respaldo.

- picture: Es un contenedor que permite colocar varias fuentes de imagen.

- source:

Define imágenes alternativas con condiciones, por ejemplo:
Usar WebP si el navegador lo soporta
Usar una imagen grande en pantallas grandes
Usar versión pequeña en móviles

Tiene atributos como:
srcset → archivo de imagen
media → condición (como media query)
type → tipo de formato (ej: WebP, PNG, JPEG)

- img:

La imagen por defecto (fallback).
Se usa si ninguna condición del source aplica.

images-responsive/index.html:

```html
<!-- pictures/source -->
<!-- Recurso externo desde pexels -->
<!-- NOTA: el orden es importante porque actua como una media queries en funcion del tamaña mostrara una u otra imagen -->
<picture>
  <!-- Desktop -->
  <source
    srcset="
      https://images.pexels.com/photos/34375368/pexels-photo-34375368.jpeg?w=1200
    "
    media="(min-width:1200px)"
  />
  <!-- Tablet -->
  <source
    srcset="
      https://images.pexels.com/photos/34375368/pexels-photo-34375368.jpeg?w=768
    "
    media="(min-width: 768px)"
  />
  <!-- Imagen por defecto, mobile si no ponemos las otras esta se muestra siempre -->
  <img
    src="https://images.pexels.com/photos/34375368/pexels-photo-34375368.jpeg?w=300"
    class="docu"
    alt="horizonte"
  />
</picture>
```

#### Imágenes con diferentes densidad de pixeles:

Tambien se puede usar `<img/>` con el atributo `srcset=""`. Esto es bastante interesante cuando queremos mostrar las imágenes en función de la densidad de pixeles del usuario. Lo que se llama pantalas retinas.

En el navegador en la ventana del inspector podemos habilitar para mostrar los tres niveles de pantallas. Va desde 1 al 3. 1 para pantallas normales, 2 para pantallas buenas y 3 para pantallas muy buenas.

images-responsive/index.html:

```html
<!-- srcset para densidad de pixeles del usuario, retina, cargara solo la imagen para la densidad de pixel -->
<img
  src="./img/paisaje800_1x.jpg"
  class="docu"
  alt="paisaje"
  srcset="
    ./img/paisaje800_1x.jpg  1x,
    ./img/paisaje1200_2x.jpg 2x,
    ./img/paisaje2400_3x.jpg 3x
  "
/>
```

Tamaños recomendados de imágenes:
La regla es multiplicar el tamaño base.
Ejemplo: si tu imagen se mostrará a 800px de ancho visiblemente:
Escala:
Normal 1X: 800px
Retina 2x: 1600px
SuperRetina 3x: 2400px

Tenemos una web donde podemos tratar las imagenes:

https://responsivebreakpoints.com

#### Añadir fuentes al proyecto:

Para codeflix vamos a añadir la fuente roboto.

https://fonts.google.com/
https://fonts.google.com/?query=roboto

Copiamos el codigo embebido que nos dan y lo usamos en el head del index.html.

index.html:

```html
<head>
  <!-- Google font -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap"
    rel="stylesheet"
  />
</head>
```

Luego en common.css aplicamos la fuente:

common.css:

```css
/* Variables  colores se pueden usar en todos los archivos*/
:root {
  font-family: 'Roboto', sans-serif;
}
```

Si no podemos o no nos dejan usar fuente de google font, podemos bajarlas a nuestro proyecto, existe una web donde podemos bajar las fuentes:

https://gwfh.mranftl.com/fonts

Escogemos la fuente que deseamos y bajamos los archivos, en una carpeta llamada font la ponemos en la raiz del proyecto. lo recomendado es descargar .woff2 y .woff asi tendremos mas soporte.

En nuestro archivo common.css la usariamos asi: OJO ponerlo antes del root:

common.css:

```css
/* ====== Fuentes ====== */
/* Roboto Thin 100 */
@font-face {
  font-family: 'Roboto';
  src: url('../fonts/roboto/roboto-v30-latin-100.woff2') format('woff2');
  font-weight: 100;
  font-style: normal;
}

/* Roboto Light 300 */
@font-face {
  font-family: 'Roboto';
  src: url('../fonts/roboto/roboto-v30-latin-300.woff2') format('woff2');
  font-weight: 300;
  font-style: normal;
}

/* Roboto Bold 700 */
@font-face {
  font-family: 'Roboto';
  src: url('../fonts/roboto/roboto-v30-latin-700.woff2') format('woff2');
  font-weight: 700;
  font-style: normal;
}
```
