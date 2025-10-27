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
@media screen and (max-width: 600px) {
  /* Estilos que se aplicarán si la pantalla es de 600px o menos de ancho */
  body {
    background-color: lightblue;
  }
}
```

El conocimiento y uso de las media queries es fundamental en el desarrollo web moderno, en particular bajo el enfoque Mobile First (Móvil Primero), donde el diseño y los estilos se piensan y aplican inicialmente para las pantallas más pequeñas, y luego se usan las media queries para añadir complejidad en pantallas más grandes.

Sintaxis mas moderna:

```css
@media screen and (max-width <= 600px) {
  /* Estilos que se aplicarán si la pantalla es de 600px o menos de ancho */
  body {
    background-color: lightblue;
  }
}
```
