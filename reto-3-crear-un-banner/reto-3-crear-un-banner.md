### Reto 3: Crear un banner:

#### index.html:

```html
<!-- Banner -->
<div class="banner">
  <!-- Aqui metemos la imagen de fondo -->
  <div class="banner__image"></div>
  <div class="banner__content">
    <h1>Unlimited movies, TV shows; and more</h1>
    <h2>Watch anywhere. Cancel anytime.</h2>
    <p>Ready to watch?</p>
  </div>
</div>
```

Recordar relacionar el html con el css en el head.

```html
<head>
  <link rel="stylesheet" href="styles/banner.css" />
</head>
```

Ahora pasamos a añadir los estilos:

Para el caso de la imagen del fondo del banner agregamos una carpeta assets/app dentro de la raiz del proyecto y ahi meteremos las imagenes que nos hacen falta.

Para centrar el texto con flex se hace en tres lineas de código pero tenemos que ver el concepto de position.

Aquí hemos visto el concepto de position, esta propiedad tiene varios valores que podemos usar:

- absolute,
- fixed,
- static,
- relative
- sticky.

En CSS, la propiedad position define cómo se coloca un elemento dentro del flujo del documento.
Estos son sus principales valores y qué hace cada uno:

- static (por defecto):
  El elemento se coloca siguiendo el flujo normal de la página. No se pueden usar top, left, right o bottom.

- relative:
  El elemento mantiene su lugar en el flujo, pero puede moverse ligeramente respecto a su posición original usando top, left, right, bottom.

- absolute:
  El elemento se saca del flujo normal y se posiciona respecto al elemento contenedor con posición distinta de static.
  Si no hay ninguno, se posiciona respecto al html o la ventana.

- fixed:
  El elemento se fija en la pantalla, sin moverse al hacer scroll.
  Su referencia es la ventana del navegador.

  - sticky:
    Es una mezcla entre relative y fixed.
    El elemento se comporta como relative hasta que se alcanza una posición específica al hacer scroll, y entonces queda fijo.

En resumen:
static: posición normal.
relative: desplazamiento leve desde su lugar original. mantiene su espacio.
absolute: posición exacta dentro de un contenedor posicionado. Pierde su posicion en el flujo.
fixed: posición fija en pantalla.
sticky: se “pega” al hacer scroll.

NOTA:

- Siempre que usemos un position absolute este se va a posicionar a su contenedor padre mas cercano que tenga position relative, sino lo hay se posiciona sobre el html. Recordar que para dar tamaño a ese contenedor le damos las unidades de top:0, left:0, right:0 y botton:0.

- Para usar z-index necesitamos un position diferente al default de static puede ser un position relative.

#### styles/banner.css:

```css
/* Contenedor padre */
.banner {
  /* Unidad relativa al alto del la pantalla */
  height: 75vh;
  text-align: center;
  /* este es necesario para poder dar position absolute a la imagen */
  position: relative;
}

/* Contenedor hijo 1 */
.banner .banner__content {
  /* Para poder usar usar el z-index debemos dar un position diferente al static*/
  position: relative;
  /* Levantamos el texto */
  z-index: 2;
}

/* Contenedor hijo 2 */
.banner .banner__image {
  /* Insertamos la imagen del banner */
  background-image: url(../assets/app/catalog.jpg);
  /* Propiedades a las imagenes en background */
  /* background-repeat: no-repeat; */
  /* background-size: 100%; */
  /* background-size: cover; */
  /* background-size: contain; */
  z-index: 0;
  /* Damos opacidad a la imagen */
  opacity: 0.3;
  /* Se posiciona con su padre que tiene relative mas cercano, sino lo encuentra va al html */
  position: absolute;
  /* Centramos la imagen al contenedor div del .banner */
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}
```

Hasta aqui el reto 2 min 3:08:54 del segundo video.

Seguimos....
