### Reto 6: Mobile First:

Aquí continuamos en el video 3 min: 3:54:20.

#### Resposive Design:

Diseño responsive es la adaptación de un sitio web, aplicación o presentación a diferentes dispositivos y tamaños de pantalla para garantizar una visualización optima en todos ellos.

Aquí es importante para empezar en nuestro .html que tengamos en el head la siguiente etiqueta:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

Si no usamos esta etiqueta veremos como nuestra web dentro de un movil se ve toda como si fuera un pc pero en el movil. No adapta nada muestra la web de pc.

Aquí tenemos documentación para profundizar sobre diferentes patrones que podemos usar para pasar de movile a desktop:

https://web.dev/learn/design/macro-layouts?continue=https%3A%2F%2Fweb.dev%2Flearn%2Fdesign&hl=es-419#article-https://web.dev/learn/design/macro-layouts&hl=es-419

https://web.dev/learn/design/micro-layouts?continue=https%3A%2F%2Fweb.dev%2Flearn%2Fdesign&hl=es-419#article-https://web.dev/learn/design/micro-layouts&hl=es-419

#### Media queries:

Las Media Queries son un módulo de CSS3 que permite aplicar estilos específicos a un sitio web en función de las características del dispositivo o del entorno donde se está visualizando.

¿Para qué sirven?

Su principal función es permitir el diseño web responsivo (responsive web design), asegurando que el contenido se adapte y se vea correctamente en una amplia gama de dispositivos, como:

- Diferentes tamaños de pantalla: smartphones, tablets y ordenadores de escritorio.
- Orientación: horizontal (landscape) o vertical (portrait).
- Características del dispositivo: como la resolución, la relación de aspecto, o si el dispositivo soporta desplazamiento (hover) o esquemas de color preferidos (modo oscuro/claro).

Estructura y Funcionamiento:

Una media query se compone generalmente de:

1 - Regla @media: El punto de partida que indica que se aplicarán estilos condicionalmente.

2 - Tipo de medio (Media Type) (opcional): Define la categoría general del dispositivo (ej. screen para pantallas, print para impresión, all para todos).

4 - Expresión de característica de medio (Media Feature): Define la condición específica a evaluar. Esto a menudo es el ancho (width o min-width/max-width), que establece los puntos de quiebra (breakpoints) donde el diseño cambia.

5 - Bloque de estilos CSS: Los estilos que se aplicarán solo si la condición es verdadera.

Ejemplo Básico de Sintaxis:

```css
@media screen and (width: 600px) {
  /* Estilos que se aplicarán si la pantalla es de 600px o menos de ancho */
  body {
    background-color: lightblue;
  }
}
```

El conocimiento y uso de las media queries es fundamental en el desarrollo web moderno, en particular bajo el enfoque Mobile First (Móvil Primero), donde el diseño y los estilos se piensan y aplican inicialmente para las pantallas más pequeñas, y luego se usan las media queries para añadir complejidad en pantallas más grandes.

Sintaxis mas moderna:

```css
@media screen and (width <= 600px) {
  /* Estilos que se aplicarán si la pantalla es de 600px o menos de ancho */
  body {
    background-color: lightblue;
  }
}
```

#### Video 4: Mobile First:

Aquí lo que haremos es adapatar la web para las media queries para los diferentes tamaños.

Ya la web ha ido desarrollandose en mobile first loq ue haremos es poner las media queries para tableta y desktop.

NOTA: cuando trabajamos con mobile first osea empezamos a trabajar con movil primero como es este caso veremos que debemos definir la media queries de una forma asi:

```css
/* Media queries */
/* Sintasis antigua para pantallas por encima 768px */
@media screen and (min-width: 768px) {
}

/* Sintasis moderna para pantallas >= 768px */
@media screen and (width >=768px) {
  .hidden-xs {
    display: block;
  }
}
```

Si es alreves y se viene de desktop para movil, sobre todo para proyectos mas antioguos veremos media queries asi:

```css
/* Media queries */
/* Sintasis antigua para pantallas por debajo 768px */
@media screen and (max-width: 768px) {
}

/* Sintasis moderna para pantallas >= 768px */
@media screen and (width <=768px) {
  .hidden-xs {
    display: block;
  }
}
```

Vamos a empezar con el header para poder ver todo el contenido en mayor tamaño: aqui hay dos sitios donde trabajar en components.css y header.css

#### components.css:

```css
/* Sintasis antigua para pantallas por encima 768px */
/* @media screen and (min-width:768px) {} */

/* Sintasis moderna para pantallas >= 768px */
@media screen and (width >=768px) {
  .hidden-xs {
    display: block;
  }
}
```

#### header.css:

```css
/* Estilos de los enlaces de nav */
.header .header__nav .header__nav__list {
  list-style: none;
  display: flex;
  align-items: center;
  gap: 10px;
}

/* Media queries */
/* Usamos sin el screem y vemos que funciona */
@media (width >=768px) {
  .header__image {
    width: 200px;
  }
}
```

Tema especifidad:

Si tenemos una clase en nuestro código css que es mas especifico que el que usamos en la media querie siempre gana el mas especifico.

Por ejemplo:

```css
/* Contenedor imagen */
.header .header__image {
  width: 120px;
}

/* Y en la media querie asi: */
@media (width >= 768px) {
  .header__image {
    width: 200px;
  }
}
```

Recomendacion: Atacar a las mismas clases que deseamos modificar en la media queries.

Tambien se añaden más media queries en los siguientes secciones:

#### banner.css:

```css
/* Media queries, sintaxis moderna */
@media (width >=800px) and (orientation: landscape) {
  .banner {
    height: 55vh;
  }
}

/* Media queries del hover, muy util al hacer hover cuando en el navegador hacemos la pantalla mas pequeña pero no es un movil o tablet que son tactiles. */
@media (hover: hover) {
  p:hover {
    color: yellow;
  }
}
```

Eso anterior también es una media query, pero en lugar de basarse en el tamaño de la pantalla, se basa en la capacidad del dispositivo para detectar hover (cuando el cursor pasa sobre un elemento).

En móviles, donde normalmente no hay cursor, esta regla no se aplicará

Aquí a continuación vemos los cambios realizados a la seccion del info.css.

#### info.css:

```css
/* Media queries */
@media screen and (width >= 768px) {
  .info .info__video video {
    top: 70px;
    width: 384px;
  }
  .info .info__video img {
    width: 628px;
  }
}

@media screen and (width >= 1024px) {
  .info {
    max-width: 1024px;
    display: flex;
    flex-direction: row-reverse;
    align-items: center;
  }
}
```

Hasta aquí la sección de cambiar lo que llevamos a las media queries para el resto de dispositivos.

Video 4 min:1:31:33.

Seguimos...
