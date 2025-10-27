### Reto 5: Info Seccion:

En este reto vamos a crear la seccion de info, para esto estamos en el video 3, minuto: 2:38:18

Procedemos a hacer la maquetación en html:

#### index.html:

```html
<!--  seccion video -->
<section class="info">
  <!-- Texto -->
  <div class="info__text">
    <h2>Watch everywhere</h2>
    <p>
      Stream unlimited movies and TV shows on your, phone, tablet, laptop, and
      TV
    </p>
  </div>
  <!-- Video -->
  <div class="info__video">
    <img src="./assets/app/device-pile.png" alt="video image" />
    <video src="./assets/app/video-devices.m4v" muted autoplay loop>
      <source src="./assets/app/video-devices.m4v" type="video/mp4" />
    </video>
  </div>
</section>
```

#### info.css:

```css
/* Seccion info */
.info {
  width: 90%;
  /* Limitamos el ancho del contenido, el texto */
  max-width: 768px;
  /* Centramos el contenedor info*/
  margin: 0 auto;
  margin-top: 25px;
}

.info__text h2 {
  margin-bottom: 15px;
}

/* Contenedor del video e imagen */
.info .info__video {
  position: relative;
  display: flex;
  justify-content: center;
}

.info .info__video img {
  position: relative;
  z-index: 2;
  width: 274px;
}

.info .info__video video {
  position: absolute;
  z-index: 1;
  top: 30px;
  width: 175px;
}
```

Aqui lo que hemos visto la seccion del video, vemos como poner un video, su etiqueta y como poner los atributos para hacerlo en bucle.

Tambien podemos ver que para cuando queramos centrar un contenedor respecto a otro le tenemos que dar un tamaño, un width o max-width para poder usar las propiedades de margin: 0 auto;

Lo podemos ver en el contenedor .info:

```css
/* Seccion info */
.info {
  width: 90%;
  /* Limitamos el ancho del contenido, el texto */
  max-width: 768px;
  /* Centramos el contenedor info*/
  margin: 0 auto;
  margin-top: 25px;
}
```

Hasta aquí en el video 3 el apartado de seccion de info. min:3:54:20
