### Reto 8: Crear css grid.

Video 5: min 2:34:32.

¿Que es grid?

CSS Grid es un sistema de diseño en CSS que permite crear distribuciones en dos dimensiones (filas y columnas) de manera fácil y flexible.
Sirve para organizar elementos en una página formando cuadrículas, pudiendo controlar tamaños, espacios y posiciones con precisión.

En pocas palabras: CSS Grid te permite construir estructuras completas de layout, como cabecera, contenido, sidebar y pie, usando filas y columnas.

Cuándo usar Grid:

- Para layouts complejos.
- Para estructuras con filas + columnas.
- Cuando quieres control preciso del diseño.

Para usar grid usaremos la propiedad display:grid;

Vamos a ver como usar grid en en ejemplo que llamaremos ejemplo-css-grid.

Vamos a maquetar en nuestro proyecto codefix usando css grid el apartado de mostrar el grid de peliculas: Video 5 min 3:36:00.

#### index.html:

```html
<!-- Grid de peliculas -->
<section class="shows">
  <!-- Series -->
  <section>
    <h2>Newest</h2>
    <ul class="shows__list">
      <li>
        <figure>
          <img src="./assets/series/serie_1.jpg" alt="Spy master" />
          <figcaption>spy masters</figcaption>
        </figure>
      </li>
      <li>
        <figure>
          <img src="./assets/series/serie_2.jpg" alt="House of dragon" />
          <figcaption>House of dragon</figcaption>
        </figure>
      </li>
      <li>
        <figure>
          <img src="./assets/series/serie_3.jpg" alt="Love & death" />
          <figcaption>Love & death</figcaption>
        </figure>
      </li>
      <li>
        <figure>
          <img src="./assets/series/serie_4.jpg" alt="Succession" />
          <figcaption>Succession</figcaption>
        </figure>
      </li>
    </ul>
  </section>
  <!-- Documentales-->
  <section>
    <h2>Docus</h2>
    <ul class="shows__list">
      <li>
        <figure>
          <img
            src="./assets/docus/docu_1.webp"
            alt="Secret of wild australia"
          />
          <figcaption>Secret of wild australia</figcaption>
        </figure>
      </li>
      <li>
        <figure>
          <img src="./assets/docus/docu_2.webp" alt="Strange creatures" />
          <figcaption>Strange creatures</figcaption>
        </figure>
      </li>
      <li>
        <figure>
          <img src="./assets/docus/docu_3.webp" alt="Africa's hunters" />
          <figcaption>Africa's hunters</figcaption>
        </figure>
      </li>
      <li>
        <figure>
          <img src="./assets/docus/docu_4.webp" alt="Shark squad" />
          <figcaption>Shark squad</figcaption>
        </figure>
      </li>
    </ul>
  </section>
</section>
```

Agregamos la hoja de estilos dentro de la carpeta styles:

```css
.shows {
  width: 90%;
  max-width: 1220px;
  margin: 0 auto;
}

.shows h2 {
  margin: 15px 0;
}

.shows__list {
  list-style: none;
  display: grid;
  /* grid-template-columns: 1fr 1fr; */
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
  padding: 0;
}

.shows .shows__list img {
  width: 100%;
}

.shows .shows__list figure {
  margin: 0;
}

/* Media queries */
@media screen and (width>=768px) {
  .shows__list {
    grid-template-columns: repeat(4, 1fr);
  }
}
```

#### Etiqueta figure:

La etiqueta figure se usa para envolver contenido visual o ilustrativo que está relacionado con el contenido principal, pero que puede entenderse por sí mismo.
Normalmente se utiliza para imágenes, gráficos, ilustraciones, fragmentos de código o tablas que quieras destacar como elemento independiente dentro del documento.

Suele ir acompañada de figcaption, que sirve para poner una descripción o pie explicativo del contenido incluido dentro de figure.

En resumen, figure agrupa un elemento ilustrativo y su posible pie descriptivo, mejorando la estructura semántica y la accesibilidad del contenido.

Aqui acaba el video 5.
