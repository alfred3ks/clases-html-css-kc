### Reto 1: Crear un proyecto de HTML y CSS:

- Entorno de trabajo VSCode y live server.
- Intro a HTML y estructura básica.
- Etiquetas básicas,
- Etiqueta HEAD.
- Intro s CSS.

#### ¿Que es HTML?

HTML (HyperText Markup Language) es el componente básico de la Web. Define el significado y la estructura de los contenidos web.
Ademas de HTML, generalmente se utilizan otras tecnologías para describir la apariencia/presentación de una pághina web(CSS) o funcionalidad/comportamiento (JavaScript).

HTML utiliza 'Marcado' para anotar texto, imágenes y otro contenido para mostrar en un navegador web. El marcado HTML incluye elementos especiales como:

```html
<head></head>
<title></title>
<body></body>
<header></header>
<footer></footer>
<article></article>
<section></section>
<p></p>
<div></div>
<span></span>
<img />
<aside></aside>
<audio></audio>
```

y muchos otros mas...

#### Etiquetas básicas:

- Paired: Con par, se les conocen como etiquetas contenedoras o etiquetas con par de apertura y cierre.

```html
<p>Hello World</p>
```

- Unpaired: Sin par, son etiquetas que no se cierran, se les llama etiquetas vacias o etiquetas sin cierre.

```html
<img />
<br />
<input />
```

#### Estructura básica:

```html
<!DOCTYPE html>
```

Es una declaración especial que se coloca al comienzo de un documento HTML para indicar al nevegador web que versión de HTML se esta utilizando. Esta declaración debe estar presente en todas las páginas HTML válidas.

```html
<html></html>
```

Envuelve todo el documento HTML y sirve como contenedor principal.

```html
<head></head>
```

Se utiliza para contener información y metadatos relacionados con el documento HTML, pero que no se muestra directamente en el navegador. Es decir, se utiliza para configurar y definir la estructura de la página, pero no para mostrar contenido visible.

```html
<body></body>
```

Se utiliza para delimitar el contenido principal de una página HTML.

Asi vemos como queda la estructura básica que vemos en un archivo HTML:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body></body>
</html>
```

NOTA: Esta estructura básica la podemos generar con VSCode con el shorcute html:5

Creamos nuestro primer archivo HTML index.html para empezar a ver cositas.

#### index.html:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

Esta etiqueta le dice al navegador cómo debe controlar las dimensiones y el escalado de la página web para que se vea correctamente en cualquier dispositivo, especialmente en móviles y tabletas. Esta etiqueta es la base para que tu sitio web sea móvil-amigable, permitiendo que el diseño se ajuste fluidamente a diferentes tamaños de pantalla.

```html
<html lang="es"></html>
```

La etiqueta html es la raíz de cualquier documento HTML, y el atributo lang="es" que mencionas sirve para indicar el idioma principal del contenido de toda la página.

NOTA: Vamos a usar la extension de Live Server de Ritwick Dey para poder ver la web en el navegador y cuando hagamos cambios estos se refresquen solos sin tener que hacerlo nosotros. Para lanzar la extension sobre el archivo .html boton derecho y buscar la opcion Open with Live Server.

#### Headings:

Los Headings (o encabezados) en HTML son etiquetas usadas para definir títulos y subtítulos en el contenido de una página web.

Su principal función es estructurar el contenido, dándole una jerarquía lógica. Van desde h1 hasta h6.

Importancia:

- Estructura Semántica: Indican a los navegadores y a los lectores de pantalla la estructura y la relación entre las diferentes partes del contenido.
- SEO (Optimización para Motores de Búsqueda): Ayudan a los motores de búsqueda (como Google) a entender de qué trata la página y cuáles son los temas más relevantes.
- Accesibilidad: Permiten a los usuarios de tecnologías de asistencia navegar rápidamente por el contenido saltando de un título a otro.

```html
<h1>Título 1</h1>
<h2>Título 2</h2>
<h3>Título 3</h3>
<h4>Título 4</h4>
<h5>Título 5</h5>
<h6>Título 6</h6>
```

#### DOM Tree:

Cuando una web es cargada, el navegador crea el Document Object Model de la página. El DOM. El modelo DOM HTML se construye como un árbol de objetos.

#### CSS: Ahora vamos a empezar a introducir el CSS ya mismo.

CSS es un lenguaje que especifica como se presentan los documentos a los usuarios: como se les aplica el estilo. Es un lenguaje en cascada.

El CSS (siglas en inglés de Cascading Style Sheets, u Hojas de Estilo en Cascada) es un lenguaje de estilo utilizado para describir la presentación de un documento escrito en HTML (o XML).

Su concepto clave es separar el contenido (HTML) del diseño (CSS).

La sintaxis para crear CSS es la siguiente:

```css
h1 {
  color: red;
}
```

- h1: selector.
- color: propiedad.
- red: valor.

#### Selectores:

```
- p{},
- #id{},
- .class{},
- *{},
- [atribute]{}
```

Existen varios tipos de selectores en HTMl pero vamos a tratar de quedarnos en tres:

- tag: ataca a la etiqueta directamente, por jemplo a un h1.
- class: ataca a todas aquellas etiquetas que lleven el atributo class
- id: ataca a aquella etiqueta unica que lleva el atributo id.

Para poder implementar o usar css para nuestras web lo podemos hacer de varias formas:

- En linea, nada recomendado, en la misma etiqueta HTMl usando el atributo style="" podemos incluir código CSS.

```html
<p style="color: red;">
  Lorem Ipsum is simply dummy text of the printing and typesetting industry.
  Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,
  when an unknown printer took a galley of type and scrambled it to make a type
  specimen book. It has survived not only five centuries, but also the leap into
  electronic typesetting, remaining essentially unchanged.
</p>
```

- En la cabecera, en el head, usando la etiqueta style.

```html
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Clase - 1</title>
  <!-- En la cabecera -->
  <style>
    h1 {
      color: red;
    }
  </style>
</head>
```

- Mediante un archivo externo y por medio la etiqueta link asociarlo a nuestro html dentro de la etiqueta head.

```html
<head>
  <link rel="stylesheet" href="main.css" />
</head>
```

##### main.css:

```css
h1 {
  color: red;
}
```

Como vemos para usar el css podemos atacar directamente a la etiqueta, h1, h2, ... Pero tambien podemos usar el atributo class="" y id="". Esto es lo mas comun cuando usamos con la etiqueta style en el head y con un archivo externo.

La explicación breve sobre class e id en CSS es la siguiente:

Ambos son selectores que te permiten aplicar estilos a elementos específicos de tu HTML, pero tienen diferencias clave en su uso y unicidad.

1. Selectores class (Clase):

- Uso en HTML: Se define con el atributo class="".

- Uso en CSS: Se selecciona con un punto (.nombre-de-la-clase).

- Unicidad: Una misma clase puede ser aplicada a múltiples elementos en una misma página.

Propósito: Ideal para aplicar un estilo reutilizable o un patrón de diseño a varios elementos (como botones, tarjetas, o mensajes de alerta).

2. Selectores id (Identificador):

- Uso en HTML: Se define con el atributo id="".

- Uso en CSS: Se selecciona con un símbolo de número o almohadilla (#nombre-del-id).

- Unicidad: Un id debe ser único en toda la página HTML. Solo un elemento puede tener un id específico.

Propósito: Ideal para identificar un elemento único y estructural (como la cabecera principal, el menú de navegación, o un footer) o para ser usado como ancla o punto de referencia en JavaScript.

Nota: OJO con la especifidad al aplicar estilo:

#### Especificidad:

La especificidad en CSS determina qué reglas tienen prioridad cuando varias afectan al mismo elemento.
Cada selector tiene un “peso” y el navegador aplica la regla con mayor especificidad.

En orden de menor a mayor prioridad:

- Selectores de tipo o elemento (p. ej. div, p)
- Selectores de clase, atributo o pseudoclase (p. ej. .btn, [type="text"], :hover)
- Selectores de ID (p. ej. #header)
- Estilos en línea (p. ej. style="color:red")
- ¡important! (!important) sobreescribe todo lo anterior. NO RECOMENDADO!!!!

Si hay empate, gana la última regla escrita en el CSS por la cascada.

--- Descanso: 2:06:53

Para este apartado vamos a crear ya la página con que vamos a trabajar para hacer el ejercicio. Lo llamaremos codeflix.

Hemos creado el archivo index.html con el esqueleto básico usando el shortcode html:5, ademas se ha creado el archivo common.css.

#### index.html:

```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- Estilos comunes -->
    <link rel="stylesheet" href="common.css" />
    <title>Codeflix</title>
  </head>
  <body>
    <h1>Codeflix</h1>
  </body>
</html>
```

#### common.css:

```css
.main-bg {
  color: white;
  background-color: black;
}
```

Nota:
Aquí podemos ver que hemos puesto a la etiqueta main la clase main-bg, que es un color de texto blanco y el fondo negro. Si añadimos dentro del main un parrafo y le ponemos un texto dentro vemos como ese texto se pinta de blanco, aqui vemos como el texto del parrafo hereda el color del main. Lo vemos en el inspector de elementos en el apartado de Styles/estilos. Heredado de body.main-bg.

Esto suele pasar con algunas propiedades, no con todas, sobre todo pasa con las relacionadas con el texto.

Para saber si la propiedad es heredable lo podemos ver en la MDN Reference, nos colocamos sobre el código de css, en este caso el color, y vemos como el editos nos ayuda y nos permite enlazar con la MDN Reference. Ahi veremos un cuadro donde dice si es heredable o no.

OJO muy interesante la documentación de la MDN Reference.

Hasta aqui el reto 1. Seguimos...
