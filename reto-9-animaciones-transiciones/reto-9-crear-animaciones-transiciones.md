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
