### Reto 2: Crear un footer:

Vamos a crear el footer para la web de codeflix.

Para organizar mejor el css dentro del proyecto codeflix vamos a meter todos los archivos de css dentro de una carpeta que llamaremos styles.

styles/common.css

Para el caso del footer veremos el concepto de nested tags, lo de anidar tags.

#### index.html:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- Estilos comunes -->
    <!-- Normalize siempre de primero para no pisar estilos -->
    <link rel="stylesheet" href="styles/normalize.css" />
    <link rel="stylesheet" href="styles/common.css" />
    <link rel="stylesheet" href="styles/footer.css" />
    <title>Codeflix</title>
  </head>
  <body class="main-bg">
    <h1>Codeflix</h1>
    <!-- footer -->
    <footer class="footer">
      <p>@2025 <em>Codeflix</em> Website</p>
      <!-- Convencion de BEM para las clases del css -->
      <p class="footer__company">Powered by keepcoding</p>
    </footer>
  </body>
</html>
```

En HTML, los elementos se clasifican según su comportamiento visual en block, inline y inline-block.

Los elementos block (de bloque) ocupan todo el ancho disponible del contenedor y siempre comienzan en una nueva línea. Permiten establecer márgenes, rellenos, anchura y altura. Se utilizan normalmente para estructurar secciones completas de una página, como párrafos o divisiones.

Los elementos inline (en línea) solo ocupan el espacio necesario para su contenido y no inician una nueva línea. No permiten definir anchura ni altura, pero sí márgenes y rellenos horizontales. Se usan principalmente para dar formato o estilo a partes específicas dentro de un texto.

Por último, los elementos inline-block combinan características de ambos tipos: se comportan como elementos en línea (colocándose uno junto a otro), pero permiten definir dimensiones, márgenes y rellenos completos como los elementos de bloque.

Ahora loq ue haremos es maquetar con css el footer, creamos dentro de styles el archivo footer.css y lo relacionamos con el index.html.

NOTA: Siempre que sea interesante heredar propiedades css hacerlo en la clase superior. Tener en cuenta esto.

Aqui vemos como aplicar las propiedades margin, padding, aliniar texto en horizontal, borde de elementos. etc

Tambien vemos los diferentes grados de especificidad para aplicar respectivas clases a los elementos.

#### footer.css:

```css
.footer {
  /* Anchos de elementos*/

  /* Alinear texto en horizontal */
  text-align: center;
  /* Dar estilos al texto del footer */
  font-style: italic;

  /* Padding */
  /*
  padding-top: 10px;
  T-R-B-L
  padding: 10px 10px 10px 10px;
  padding: 50px 10px 10px 10px;
  X-Y
  padding: 20px 0;
  */
  padding: 40px;

  /* Border */
  /* Borde punteado */
  /* border: 1px dashed crimson; */
  /* Borde solido */
  /* border: 1px solid crimson; */
  /* El radio del borde */
  /* border-radius: 5px; */

  /* Margin separacion entre elementos */
  /*
  margin: 80px;
  T-R-B-L
  margin: 10px, 10px, 10px, 10px;
  X-Y
  margin: 20px 0;
  margin-top: 80px;
  margin-bottom: 80px;
  */
}

/* Añadimos un grado mas de especificidad */
/* Se modificaran solo los parrafos que estan dentro de la clase footer */
.footer p {
  /* Eliminamos los margenes de los parrafos, propiedad no heredada */
  margin: 0;
}

/* Se modificaran solo los elementos que tengan la clase footer__company dentro de la clase footer mas especifico que el de arriba*/
.footer .footer__company {
  font-style: normal;
}
```

Unidades para márgenes y padding:

Absolutas:

- px,
- cm,
- in,
- pt.ipt = 1/72in

Relativas:

- em,
- rem,
- vw,
- vh
- %

Para eliminar los estilos por defecto de navegador usaremos las propiedades de margin, padding y box-sizing dentro de common.css asi:

#### common.css:

```css
* {
  box-sizing: border-box;
  /* Valores de nuestro reset */
  padding: 0;
  margin: 0;
}
```

Tambien es importante agregar un archivo normalize para arrancar de cero nuestro proyecto, este lo podemos encontrar en la web normalize.

https://necolas.github.io/normalize.css/

Agregamos el archivo normalize.css y lo enlazamos con nuestro archivo index.html.

Usamos una combinación del reset del common.css y del normalize.css.

NOTA: Al agregar los estilos en el head, primero siempre estas librerias que agreguemos para evitar que nos pisen nuestros estilos.

#### Variables en CSS:

Las variables en CSS permiten guardar valores reutilizables (como colores, tamaños o fuentes) para mantener un estilo coherente y fácil de modificar.

Se definen con un nombre precedido por dos guiones (--) dentro de un selector (normalmente :root para que sean globales) y se usan con la función var().

En resumen, las variables hacen que el código CSS sea más limpio, mantenible y flexible, ya que al cambiar el valor de una sola variable se actualiza automáticamente en todos los lugares donde se usa.

Tenemos que usar la palabrar :root{} dentro de los parentesis definir las varaibles con la convención --nombre-variable: valor.

Es importante saber que al nombrar las variables los dos primeros guiones son importantes colocarlos sino no va a funcionar.

Vamos dentro del archivo common.css introducir las variables de colores, tamaños de letras, y fuentes de nuestra app.

#### common.css:

```css
/* Variables  colores se pueden usar en todos los archivos*/
:root {
  --main-bg-color: #000000;
  --main-text-color: rgb(255, 255, 255);
}

/* aplicamos los estilos con las varaibles */
.main-bg {
  color: var(--main-text-color);
  background-color: var(--main-bg-color);
}
```

Hasta aqui llega el video 1 con el reto 2. Este continua con el video 2 para terminar el reto 2.

Seguimos...

A partir de aquí el video 2.

#### Ancho de elementos:

Aqui vemos el concepto de caja para el box-sizing, para esto tenemos dos opciones:

- content-box, -> valor por defecto en navegadores.
- border-box.

En CSS, estos términos se refieren al modelo de caja y cómo se calcula el tamaño total de un elemento:

- content-box (valor por defecto):

El ancho y alto (width, height) solo incluyen el contenido. El padding, el border y el margin se suman aparte.
→ Resultado: el tamaño total del elemento será mayor que el especificado.

- border-box:

El ancho y alto incluyen el contenido, el padding y el borde, pero no el margin.
→ Resultado: el tamaño total del elemento se mantiene igual al valor definido, más fácil para diseñar layouts precisos.

En resumen:

content-box = tamaño + padding + border
border-box = tamaño incluye padding y border.

Para nuestro proyectos a partir de ahora poner esta unidad en el css y asi nos aseguramos que sea siempre border-box asi tendremos el mejor control de las cajas.

#### common.css:

```css
/* Reset estilos del navegador para todos los elementos */
* {
  box-sizing: border-box;
  /* Valores de nuestro reset */
  padding: 0;
  margin: 0;
}
```

Ahora si ponemos un ancho de un elemento veremos por medio del inspector de elementos que siempre medira el total del ancho que le ponemos y independiente del padding que tenga o el borde.

#### Variables en css:

Ahora volvemos a hablar del tema de las variables en el css.

En CSS, las variables (también llamadas custom properties) permiten guardar valores reutilizables, como colores, tamaños o fuentes.

El selector especial :root representa el elemento raíz del documento (normalmente html).
Se usa para definir variables globales accesibles desde todo el CSS.

Por ejemplo:

```css
:root {
  --color-principal: #007bff;
  --tamaño-texto: 16px;
}
```

```css
body {
  color: var(--color-principal);
  font-size: var(--tamaño-texto);
}
```

En resumen:
:root = nivel global (como una variable global).
--nombre = define la variable.
var(--nombre) = la usa en el CSS.

#### Colores en CSS:

En CSS se pueden aplicar colores de varias formas para elementos como texto, fondos o bordes. Las maneras más comunes son las siguientes:

Primero, se puede usar un nombre de color como “red”, “blue” o “black”. Son nombres predefinidos por el navegador.

```css
color: red;
```

Otra forma es usar un código hexadecimal, que combina números y letras para representar el color.

```css
color: #ff0000;
```

También se puede usar el formato RGB o RGBA, donde se indica la cantidad de rojo, verde y azul en valores del 0 al 255. La variante RGBA permite además definir la transparencia del color. La transparencia va de 0 a 1.

```css
color: rgb(255, 0, 0);
color: rgba(255, 0, 0, 0.5);
```

Otra opción es el formato HSL o HSLA, que define el color por tono, saturación y luminosidad. Al igual que RGBA, la versión HSLA permite ajustar la transparencia.

```css
color: hsl(0, 100%, 50%);
color: hsla(0, 100%, 50%, 0.5);
```

En resumen, se pueden poner colores usando nombres, códigos hexadecimales, valores RGB o HSL, y sus versiones con transparencia RGBA y HSLA.

Existe tambien una propiedad css para dar opacidad a un color, va desde 0 a 1, puede dar el caso que tengas un color y agregandole la opacidad este baja su intensidad.

```css
/* aplicamos los estilos con las varaibles */
.main-bg {
  color: var(--main-text-color);
  background-color: var(--main-bg-color);
  opacity: 0.75;
}
```

Esta es una propiedad que se puede ver en banner para darle una opacidad a una imagen de fondo.

#### Medidas relativas:

En CSS, las medidas relativas son aquellas cuyo tamaño depende de otro valor, como el tamaño de fuente del elemento o el tamaño de la ventana.
A diferencia de las medidas absolutas (como px), las relativas se adaptan mejor a distintos dispositivos y pantallas.

Algunos ejemplos comunes son:

- em: depende del tamaño de fuente del elemento padre.
- rem: depende del tamaño de fuente del elemento raíz (html).
- % (porcentaje): se calcula según el tamaño del contenedor.
- vw / vh: representan un porcentaje del ancho (vw) o alto (vh) de la ventana del navegador.

1rem = 16px

En resumen, las medidas relativas permiten que el diseño sea más flexible y adaptable.

Usar medidas en (em) y en (rem )son mas usado para el tema de la tipografia o texto de la web.

Para el uso de (rem) tengo esta manera de hacerlo y es mas intuitivo:

Reset estilo básicos navegador:

Este es el contenido del archivo reset para los estilos por defecto del navegador:

```css
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

html {
  font-size: 62.5%;
}
```

La explicación para poner el 62.5%.

Lo normal si poner esto es que 1rem = 16px. Para poner multiplos de 10 podemos hacer la cuenta:

16px ----> 100%

10px ----> x

x = 62.5%.

Ahora cuando declaremos las propiedades del font-size podemos decir que 1.6rem = 16px.

Vale como lo vamos hacer para futuros proyectos definimos en el common.css en el root asi, ponemos los colores y agregamos lo de la fuente para html:

#### common.css:

```css
/* Variables  colores se pueden usar en todos los archivos*/
:root {
  --main-bg-color: #000000;
  --main-text-color: rgb(255, 255, 255);
  --main-brand-color: #e50914;
  --main-brand-color-light: #e44c54;
}

/* Reset estilos del navegador para todos los elementos */
* {
  box-sizing: border-box;
  /* Valores de nuestro reset */
  padding: 0;
  margin: 0;
}

html {
  font-size: 62.5%;
}
```

Ahora se han reseteado todos los valores para las tipografias de la web tenemos que darle el tamaño nosotros a cada elementos. Recordando que 1rem = 16px.

Para la clase vamos a seguir la explicación del profesor que lo pone asi:

#### common.css:

```css
/* Variables  colores se pueden usar en todos los archivos*/
:root {
  --main-bg-color: #000000;
  --main-text-color: rgb(255, 255, 255);
  --main-brand-color: #e50914;
  --main-brand-color-light: #e44c54;
  font-size: 16px;
}

/* Reset estilos del navegador para todos los elementos */
* {
  box-sizing: border-box;
  /* Valores de nuestro reset */
  padding: 0;
  margin: 0;
}
```

De esta manera los texto tendra una base de 16px y a partir de ahi jugamos nosotros si queremos que sean menor o mayor pues le asignamos la propiedad al que queramos variar.

#### Mas propiedades del texto:

Para esto vamos a ver como podemos agregarle mas propiedades por medio de css al texto, lo seguimos haciendo en el footer:

#### footer.css:

```css
/* Añadimos un grado mas de especificidad */
/* Se modificaran solo los parrafos que estan dentro de la clase footer */
.footer p {
  /* Eliminamos los margenes de los parrafos, propiedad no heredada */
  /* Al usar el common.css esto es redundante */
  /* margin: 0; */

  /* Medidas relativas al root 1 rem = 16px*/
  font-size: 1rem;
  /* Mas propiedades para texto */
  /* Le damos peso al texto */
  /* font-weight: bold; */
  /* Transformamos el texto a mayuscula */
  /* text-transform: uppercase; */
  /* valor de line-height que va de 1 a 2, puede ir esta configuracion en el common.css*/
  /* line-height: 1.5; */
}
```

Ahora para terminar el reto 2 vamos a agregar un configuracion al common.css para el tipo de letra. font-family: OJO lo normal es no usar mas de dos fuentes en el proyecto.

#### common.css:

```css
/* Variables  colores se pueden usar en todos los archivos*/
:root {
  --main-bg-color: #000000;
  --main-text-color: rgb(255, 255, 255);
  --main-brand-color: #e50914;
  --main-brand-color-light: #e44c54;
  font-size: 16px;
  /* font-size: 62.5%; */
  /* tipo de letra por default */
  font-family: sans-serif;
}
```

Más adelante veremos como agregar fuentes desde Google.

Hasta aqui el reto 2 video 2 minuto 1:22:54

Seguimos...
