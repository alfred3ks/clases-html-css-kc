### Reto 2: Crear un footer:

Vamos a crear el footer para la web de codeflix.

Para organizar mejor el css dentro del proyecto codeflix vamos a meter todos los archivos de css dentro de una carpeta que llamaremos styles.

css/common.css

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

Seguimos.
