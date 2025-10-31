### Reto 7: Crear formulario de registro:

Esto empieza en el video 4 min 1:31:45.

Vamos a crear el formulario de registro, donde veremos la etiqueta de formulario, la validacion que tenemos con html5.

La etiqueta form. Se utiliza para crear un formulario en una página web. Permite a los usuario ingresar y enviar datos, como texto, opciones seleccionadas o archivos al servidor web para su procesamiento.

Dentro de una etiqueta form se suelen usar varias etiquetas para recoger datos del usuario o para interactuar con el formulario. Las más comunes son:

Dentro de una etiqueta form se suelen usar varias etiquetas para recoger datos del usuario o para interactuar con el formulario. Las más comunes son:

1 - input: Campo de entrada. Puede tener distintos tipos:

- type="text" → texto
- type="email" → correo electrónico
- type="password" → contraseña
- type="number" → números
- type="checkbox" → casilla de verificación
- type="radio" → opción de selección única
- type="submit" → botón para enviar el formulario

2- textarea: Área de texto más grande (para comentarios o mensajes).
3 - select y option: Lista desplegable de opciones.
4 - button: Botón (puede enviar el formulario o hacer otra acción).
5 - label: Etiqueta que describe un input y mejora la accesibilidad.
6 - fieldset y legend: Agrupan campos relacionados con un título.
7 - datalist: Lista de sugerencias para un input tipo texto.

#### Etiquetas label y input:

Tienen como caracteristica que son inline-block. Se colocan una al lado de la otra.

Podemos relacionar un label con input por medio del atributo for del label y del id del input. Esto nos ayuda que al hacer click sobre el texto del label nos hace focus dentro de la caja del input.

```html
<div>
  <label for="email">Email</label>
  <input type="email" id="email" />
</div>
```

Recomendacion: encapsular los label y input dentro de un div. Ayuda mucho para poder maquetar mejor y muchos framework de lo hacen asi como bootstrap.

Más atributos que puede tener un input:

- placeholder: Nos mete el texto en el input, dentro de la caja. es mejor usar el label antes que el placeholder, pero depende de cada proyecto. placeholder='Ingresa tu email'
- value: Valor harcodeado por defecto, value="pepito@pepeito.com"
- disabled: Con esto desabilitamos el input. Caja deshabilitada.
- name: sirve para identificar el dato cuando se envia el formulario.

Descanso: video 4: 2:02:57

Seria interesante ya que sabemos que el label y input son de tipo inline-block, en el common.css ponerle que sena de tipo block:

#### common.css:

```css
label,
input {
  display: block;
}
```

#### Atributos del form:

- action: indica a donde se enviaran los datos del formaulario, por ejemplo una url o archivo del servidor. action="/registro.html".
- metod: Define como se enviaran los datos, tenemos de dos formas de tipo (get): en la url y de tipo (post): en el cuerpo de la peticion.

Es importante que los input que tengamos en el formulario tengan el atributo name="" con su respectivo nombre porque eso es lo que se enviara.

Cuando tengamos que enviar información sensible siempre usar metodo post.

Para ver los datos enviados en el cuerpo de la peticion lo podemos ver en la pestaña de network (red) al pulsar sobre la url de la pagina de envio vemos los encabezados y la carga util.

NOTA: Cuando tengamos un button dentro de un formulario su comportamiento es de tipo submit como el input de tipo submit, para evitar este comportamiento le debemos poner el atributo type que sea de tipo button. Asi no lanza el formulario.

```html
<button type="button">More about me</button>
```

Entre otros atributos que tiene este button tambien es de type reset, cuando deseamos resetear el formulario.

```html
<button type="reset">Reset</button>
```

#### input de tipo file:

En los input de tipo file podemos agregarle un atributo que nos permite decirle que solo acepta un tipo de archivo bien sea una foto o pdf, etc. No es una validacion es una mejora para la experiencia del usuario porque le muestra en su pc solo esos archivos. El atributo multiple nos permite agregar varia archivos.

```html
<input
  type="file"
  id="avatar"
  name="avatar"
  accept="image/png, image/jpeg"
  multiple
/>
```

#### Etiqueta fieldset:

La etiqueta fieldset se usa en formularios para agrupar campos relacionados dentro del form. Su objetivo es organizar el contenido y mejorar la accesibilidad y la estructura visual.

¿Para qué sirve?

Agrupa inputs que pertenecen a la misma categoría
Mejora la experiencia del usuario (más orden)
Ayuda a lectores de pantalla a entender secciones del formulario

¿Cómo funciona?

Normalmente va acompañada de la etiqueta legend, que pone un título a ese grupo.

```html
<fieldset>
  <legend>Fav Category</legend>
  <div>
    <label for="shows">Shows</label>
    <input type="radio" name="category" id="shows" value="shows" />
    <label for="docus">Docus</label>
    <input type="radio" name="category" id="docus" value="docu" />
  </div>
</fieldset>
```

Detalles importantes:

- fieldset crea un borde alrededor del grupo (puedes estilizarlo con CSS)
- legend describe el contenido del fieldset (igual que un título)

En resumen:
fieldset = Agrupa campos relacionados del formulario
legend = Título del grupo

Importante:
El atributo name debe ser igual para que nos permita escoger uno u otra categoria para este caso, si no es igual y usamos el name como lo venimos usando permitira seleccionar todos los radio.

Para saber que opcion escoge el usuario necesita el atributo los inputs value="".

#### Textarea:

El textarea es una etiqueta de HTML que se usa para crear un campo de texto de varias líneas en un formulario.

Sirve cuando el usuario debe escribir texto largo, como comentarios, descripciones o mensajes.

Características:

- Permite escribir más de una línea.
- El usuario puede redimensionarlo (según el navegador).
- No usa type como los inputs.
- Se puede controlar su tamaño con rows y cols, aunque hoy en día suele hacerse con CSS.

Uso típico:

Formulario de contacto, caja de comentarios, mensajes, reseñas, etc.

```html
<div>
  <label for="bio">Bio</label>
  <textarea
    name="bio"
    id="bio"
    placeholder="Add yor bio"
    cols="50"
    rows="10"
  ></textarea>
</div>
```

#### input checkbox:

Un input de tipo checkbox es un campo de formulario en HTML que permite al usuario seleccionar una o varias opciones activándolas o desactivándolas con un clic.

¿Para qué sirve?

Para casos donde el usuario puede elegir más de una opción.
Ejemplo típico: aceptar términos, seleccionar intereses, preferencias, etc.

Sintaxis

```html
<input type="checkbox" name="opcion1" value="pizza" /> Pizza
```

Comportamiento:

- Cada checkbox funciona independientemente.
- Se puede marcar ✅ o desmarcar ❌.
- Si varios tienen el mismo name, enviarán múltiples valores.

Ejemplo con varios checkboxes:

```html
<p>Selecciona tus hobbies:</p>

<label> <input type="checkbox" name="hobby" value="leer" /> Leer </label>

<label> <input type="checkbox" name="hobby" value="deporte" /> Deporte </label>

<label> <input type="checkbox" name="hobby" value="musica" /> Música </label>
```

Si es un checkbox para aceptar las condiciones, normalmente significa que el usuario debe marcarlo ✅ antes de continuar (por ejemplo, para registrarse o enviar un formulario).

Sirve para indicar que el usuario acepta los términos y condiciones o la política de privacidad.

Un ejemplo:

```html
<label>
  <input type="checkbox" name="terminos" required />
  Acepto los términos y condiciones
</label>
```

Importante:
Se usa el atributo required para que el formulario no pueda enviarse hasta que el usuario lo marque.
Legalmente, suele ser obligatorio en formularios donde se recopilan datos personales.

¿Por qué un checkbox?

Porque el usuario debe dar su consentimiento explícito.
No se puede marcar automáticamente ni estar preseleccionado (por leyes de protección de datos como GDPR en Europa).

El atributo value en un input (incluido un checkbox) indica el valor que se enviará al servidor cuando ese campo esté seleccionado o completado.

En un checkbox, value especifica qué texto o dato se enviará si el usuario marca la casilla.

```html
<input type="checkbox" name="terminos" value="aceptado" required /> Acepto los
términos y condiciones
```

Si no colocas value, el navegador envía por defecto: on

Tip importante:

Siempre es buena práctica poner un value descriptivo, para saber qué ha marcado el usuario.

#### Etiqueta de tipo select:

Una etiqueta de formulario que crea un menú desplegable donde el usuario puede elegir una opción (o varias, si se permite).

Dentro del select van las opciones usando option.

¿Para qué sirve?

Para seleccionar una opción entre varias (países, géneros, categorías, etc.).
Puede permitir múltiples selecciones usando multiple.

```html
<div>
  <label for="country">Country</label>
  <select name="country" id="country" required>
    <option>Select one country</option>
    <option value="es">España</option>
    <option value="usa">USA</option>
  </select>
</div>
```

Los atributos de select name es importante y del option el value para poder enviar la información al servidor.

Luego vamos a poner a los input el atributo required para hacer que no se puede enviar el formulario sin que sea rellenado el campo.

Aquí acaba el video 4.

#### Video 5: Validaciones:

Vamos a hacer las validaciones con html5 de los componentes del formulario.

Aqui vemos algunas de los atributos que podemos aplicar a nuestros elementos del formulario para hacer validaciones:

- checked,
- disabled,
- max,
- maxlength,
- pattern,
- readonly,
- required,
- size,
- step,
- value,
- data-\*
- min, etc.

NOTA: Si colocamos el atributo novalidate al form, nos quita todas las validaciones que pongamos por html5, esto es util al trabajar con validaciones por codigo en js.

Aquí tenemos un input de tipo número donde vemos que podemos limitar el max y min que debe tener este campo. Aqui vemos los atributos max="" y min="".

#### Input de type number:

```html
<!-- number -->
<div>
  <label for="age">Age</label>
  <input
    type="number"
    id="age"
    placeholder="Add your age"
    name="age"
    required
    min="18"
    max="65"
  />
</div>
```

#### Etiqueta textarea:

Usamos atributo maxlength para limitar el maximo de contenido que vamos a permitir en el campo. Con el minlength podemos decirle el minumo que podemos meter

```html
<!-- textarea -->
<div>
  <label for="bio">Bio</label>
  <textarea
    name="bio"
    id="bio"
    placeholder="Add yor bio"
    cols="50"
    rows="10"
    required
    minlength="10"
    maxlength="240"
  ></textarea>
</div>
```

#### Etiqueta select:

En esta etiqueta vemos como el primer option debe llevar un value vacio las propiedades de disabled para que no pueda ser enviado al servidor y selected para que sea el que se muestre en el formulario esta opcion. Y por supuesto el select llevara su required.

```html
<!-- Select -->
<div>
  <label for="country">Country</label>
  <select name="country" id="country" required>
    <option value="" disabled selected>Select one country</option>
    <option value="es">España</option>
    <option value="usa">USA</option>
  </select>
</div>
```

#### input de tipo tel:

Para este vemos como usamos la propiedad pattern y title para validar este input, aqui entra las expresiones regulares para validar. El atributo title complementa al patter porque le da informacion al usuario que patron debe seguir.

```html
<!-- Phone -->
<!-- pattern usamos una expresion regular para validar el telefono -->
<div>
  <label for="phone">Phone</label>
  <input
    type="tel"
    id="phone"
    name="phone"
    required
    pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
    title="format is 600-600-1234"
  />
</div>
```

Hasta aquí vemos las validaciones que llevara este formulario nos quedaria asi tras agregar tambien las clases:

#### sign-in.html:

```html
<!-- Formulario -->
<form action="registro.html" method="post" class="form">
  <!-- Email -->
  <!-- Envuelvo el label y input en un div -->
  <div class="form__element">
    <!-- El label y el input los relacionamos por el for y id, el atributo name muy importante -->
    <label for="email" class="form__label">Email</label>
    <input
      class="form__input"
      type="email"
      id="email"
      placeholder="Add your email"
      name="email"
      required
    />
  </div>
  <!-- age -->
  <div class="form__element">
    <label for="age" class="form__label">Age </label>
    <input
      class="form__input"
      type="number"
      id="age"
      placeholder="Add your age"
      name="age"
      required
      min="18"
      max="65"
    />
  </div>
  <!-- password -->
  <div class="form__element">
    <label for="password" class="form__label">Password</label>
    <input
      class="form__input"
      type="password"
      id="password"
      placeholder="Add your password"
      name="password"
      required
    />
  </div>
  <!-- phone -->
  <!-- pattern usamos una expresion regular para validar el telefono -->
  <div class="form__element">
    <label for="phone" class="form__label">Phone</label>
    <input
      class="form__input"
      type="tel"
      id="phone"
      placeholder="Add your phone"
      name="phone"
      required
      pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
      title="format is 600-600-1234"
    />
  </div>
  <!-- File -->
  <div class="form__element">
    <label for="avatar" class="form__label">Choose a profile image</label>
    <input
      class="form__input"
      type="file"
      id="avatar"
      name="avatar"
      accept="image/png, images/jpg"
      required
    />
  </div>
  <!-- La etiqueta fieldset, nos crea como un borde, para agrupar elementos fuera del contexto-->
  <!-- fieldset -->
  <fieldset class="form__element">
    <legend>Fav category</legend>
    <div>
      <label for="shows" class="form__label">Shows</label>
      <input
        class="form__input"
        type="radio"
        id="shows"
        name="category"
        checked
        value="shows"
      />
      <label for="docus" class="form__label">Docus</label>
      <input
        class="form__input"
        type="radio"
        id="docus"
        name="category"
        value="docus"
        required
      />
    </div>
  </fieldset>
  <div class="form__element">
    <label for="bio" class="form__label">Bio</label>
    <textarea
      name="bio"
      id="bio"
      cols="30"
      rows="10"
      placeholder="Add your bio"
      minlength="10"
      maxlength="240"
    ></textarea>
  </div>
  <!-- Checkbox -->
  <div class="form__element form__element--checkbox">
    <input class="form__input" type="checkbox" id="remember" name="remember" />
    <label for="remember" class="form__label">Remember me</label>
  </div>
  <!-- Muy usado en las web pero dificil de dar estilos el select -->
  <!-- Select -->
  <div class="form__element">
    <label for="country" class="form__label">Country</label>
    <select name="country" id="country" required class="form__input">
      <option value="">Select one country</option>
      <option value="es">España</option>
      <option value="usa">USA</option>
    </select>
  </div>
  <!-- Añadimos el elemento button, atributo type="button" elimina su comportamiento por defecto dentro del formulario que es submit, aqui usamos el de reset -->
  <!-- Boton de envio, ojo al atributo, por defecto es submit si esta dentro del formulario -->
  <div>
    <button class="btn btn--secondary" type="reset">Reset</button>
    <input class="btn" type="submit" value="Sign in" />
  </div>
</form>
```

Ahora vamos a poner los estilos de este formulario. creamos el archivo sign-in.css dentro de la carpeta styles:

#### sign-in.css:

```css
/* Agregamos la imagen de fondo*/
.container {
  background-image: url(../assets/app/catalog.jpg);
}

/* Estilos del cuerpo del form */
.card {
  padding: 40px 20px 50px 20px;
  max-width: 320px;
  margin: 0 auto;
  /* Mejor rgba que opacidad */
  background-color: rgba(0, 0, 0, 0.9);
}
```

Resto de css lo metemos en common.css:

#### common.css:

```css
/* Estilos de botones */
.btn {
  color: var(--main-text-color);
  background-color: var(--main-brand-color);
  padding: 10px;
  border-radius: 5px;
  border: 1px solid var(--main-brand-color);
}

/* Agregamos la variante del boton reset más especifico */
.btn.btn--secondary {
  background-color: transparent;
  border-color: var(--main-text-color);
}

/* Ocultar elementos */
.hidden-xs {
  /* El compoente se borra del layout */
  display: none;
  /* El componente se hace invisible pero no se quita del layout */
  /* visibility: hidden; */
}

/* Damos estilos a los input del formulario */
.form__element {
  display: flex;
  flex-direction: column;
  margin-bottom: 12px;
}

/* Estilos del checkbox */
.form__element--checkbox {
  flex-direction: row;
  align-items: center;
}

/* Vemos como somos especificos con el checkbox */
.form__element--checkbox input[type='checkbox'] {
  margin-right: 5px;
}

/* Estilos a los labels */
.form__label {
  margin-bottom: 10px;
  font-size: 1.2rem;
  font-weight: 400;
}

/* Estilos del input */
.form__input {
  padding: 16px 12px;
  border-radius: 5px;
  /* Poner en las variables ojo este color */
  background: #333333;
  border: none;
  color: var(--main-text-color);
}

/* Agregamos estilos a los placeholder */
.form__input::placeholder,
textarea::placeholder {
  /* Aqui igual llevar este color a las variables */
  color: #cbcbcb;
}

.form__element .form__textarea {
  padding: 10px 5px;
}

/* Sintasis antigua para pantallas por encima 768px */
/* @media screen and (min-width:768px) {} */
/* Sintasis moderna para pantallas >= 768px */
@media screen and (width >=768px) {
  .hidden-xs {
    display: block;
  }
}
```

NOTA: aqui vemos como colocar los estilos a un input que tenga un placeholder:

```css
/* Agregamos estilos a los placeholder */
.form__input::placeholder,
textarea::placeholder {
  /* Aqui igual llevar este color a las variables */
  color: #cbcbcb;
}
```

Hasta aqui el formulario, video 5 min: 
