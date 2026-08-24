# Portfolio Web — Álvaro Gabriel Mamani

Portfolio personal desarrollado para presentar mi perfil profesional como **desarrollador web y diseñador**, mostrando mis habilidades, proyectos, formación y diferentes áreas de conocimiento.

El proyecto busca combinar un diseño moderno y minimalista con una estructura clara, responsive y enfocada en ofrecer una buena experiencia de usuario.

**Vercel URL:** ``

---

## Descripción

Este portfolio fue desarrollado como una aplicación web estática utilizando **HTML, CSS y JavaScript**, con el objetivo de crear una presentación profesional y accesible de mi perfil.

La estructura está organizada en diferentes secciones:

* **Home** — Presentación personal y perfil profesional.
* **Acerca de mí** — Información sobre mi perfil y experiencia.
* **Skills** — Presentación de las principales habilidades técnicas.
* **Diseño** — Habilidades relacionadas con diseño de interfaces y experiencia de usuario.
* **Frontend** — Tecnologías y conocimientos relacionados con el desarrollo frontend.
* **Backend** — Tecnologías y conocimientos relacionados con el desarrollo backend.
* **Formación** — Línea de tiempo con la formación y educación.
* **Proyectos** — Presentación de proyectos realizados.
* **Contacto** — Formulario y diferentes medios de contacto.

---

# Estructura del proyecto

El proyecto fue organizado buscando mantener una estructura sencilla y fácil de mantener.

La separación de responsabilidades permite mantener:

* **HTML** → estructura y contenido.
* **CSS** → diseño, responsive y animaciones.
* **JavaScript** → comportamiento e interactividad.

---

# Decisiones de diseño

El diseño del portfolio se construyó buscando un equilibrio entre **simplicidad, personalidad y profesionalismo**.

Se priorizaron:

* Interfaz limpia.
* Buena distribución del contenido.
* Jerarquía visual.
* Espaciado consistente.
* Elementos visuales sutiles.
* Adaptabilidad a diferentes dispositivos.
* Navegación sencilla.

La intención fue evitar sobrecargar la interfaz y permitir que el contenido principal, especialmente los proyectos y las habilidades, tenga protagonismo.

---

# Uso de CSS Grid

Se utilizó **CSS Grid** principalmente para organizar elementos que necesitan una estructura bidimensional.

Por ejemplo, se utilizó para:

* Distribuir las tarjetas de proyectos.
* Organizar las tarjetas de Skills.
* Dividir determinadas secciones en columnas.
* Crear estructuras responsive.

Un ejemplo utilizado en el proyecto es:

```css
.project-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 2rem;
}
```

El uso de `auto-fit` y `minmax()` permite que las tarjetas se adapten al espacio disponible sin necesidad de establecer manualmente una cantidad de columnas para cada resolución.

### ¿Por qué Grid?

Se eligió Grid cuando el contenido necesitaba controlar simultáneamente **filas y columnas**, especialmente en estructuras como las tarjetas de proyectos y Skills.

Esto permite obtener un diseño más flexible y facilita la adaptación a diferentes tamaños de pantalla.

---

# Uso de Flexbox

**Flexbox** se utilizó principalmente para distribuir elementos en una sola dimensión.

Por ejemplo:

```css
.skills-box {
    display: flex;
    justify-content: center;
    column-gap: 2.5rem;
}
```

También se utilizó para organizar elementos como:

* Menús de navegación.
* Botones.
* Iconos y textos.
* Elementos alineados horizontal o verticalmente.
* Componentes que necesitan centrado.

### ¿Por qué Flexbox?

Flexbox resulta especialmente útil cuando se necesita controlar la distribución de elementos en una fila o columna.

La combinación de **Grid + Flexbox** permite utilizar cada herramienta según el tipo de estructura que se necesita resolver.

---

# Responsive Design y Breakpoints

El portfolio fue desarrollado siguiendo un enfoque responsive para que pueda adaptarse a diferentes tamaños de pantalla.

Se incorporaron diferentes **breakpoints** para modificar la distribución de los elementos dependiendo del dispositivo.

Los principales puntos considerados fueron:

```css
@media screen and (max-width: 992px)
```

```css
@media screen and (max-width: 768px)
```

```css
@media screen and (max-width: 576px)
```

```css
@media screen and (max-width: 350px)
```

Estos breakpoints permiten, entre otras cosas:

* Pasar de varias columnas a una sola.
* Reducir espacios y márgenes.
* Adaptar el tamaño de las imágenes.
* Modificar el tamaño de las tarjetas.
* Evitar desbordamientos horizontales.
* Mejorar la legibilidad en dispositivos pequeños.

La prioridad no fue únicamente hacer que el contenido "entre" en una pantalla pequeña, sino mantener una experiencia visual cómoda y coherente.

---

# Variables CSS

Para mantener la consistencia visual se utilizaron **variables CSS**.

Por ejemplo:

```css
:root {
    --body-color: ...;
    --container-color: ...;
    --title-color: ...;
    --text-color: ...;
    --acento-color: ...;
}
```

También se utilizaron variables para tamaños de fuente y espaciados:

```css
--normal-font-size
--small-font-size
--smaller-font-size
--tiny-font-size

--mb-1
--mb-1-5
--mb-2
```

### ¿Por qué utilice variables?

Me permiten modificar aspectos generales del diseño desde un único lugar.

Por ejemplo, si se desea cambiar el color principal del portfolio, se puede modificar:

```css
--acento-color
```

en lugar de buscar y reemplazar manualmente el color en todas las reglas CSS.

Esto mejora la:

* Consistencia visual.
* Mantenibilidad.
* Escalabilidad.
* Facilidad de modificación.

---

# Identidad visual

El diseño utiliza una estética minimalista con una combinación de colores neutros y un color de acento para destacar elementos importantes.

### Color de acento

Se utiliza un tono dorado/amarillo como color de acento:

```css
rgba(225, 161, 2, ...)
```

Este color se utiliza principalmente para:

* Elementos destacados.
* Detalles visuales.
* Estados activos.
* Elementos de navegación.
* Algunos componentes de la interfaz.

El objetivo es utilizar el color de acento de forma moderada para mantener una apariencia profesional.

### Tipografía

La tipografía se mantiene consistente en todo el sitio y se utilizan diferentes tamaños para establecer una jerarquía visual.
Se eligió de **Google-fonts** la fuente **Nunito Sans**, ya que es formal pero con bordes suaves, transmite cercanía sin perder seriedad.

Se diferencian principalmente:

* Títulos.
* Subtítulos.
* Texto principal.
* Texto secundario.
* Información complementaria.

El uso de variables permite modificar estos tamaños de manera centralizada.

---

# Animación de la imagen de perfil

Como elemento visual distintivo se incorporó una animación en la imagen de perfil.

La imagen utiliza una forma orgánica mediante `border-radius` y cambia progresivamente de forma utilizando `@keyframes`.

```css
.home-img {
    background: url('./assets/unnamed.file3.jpg') no-repeat center;
    background-size: cover;

    box-shadow:
        inset 0 0 0 9px rgba(225, 161, 2, 0.1);

    order: 1;

    width: 300px;
    height: 300px;

    animation:
        profile__animate
        8s ease-in-out
        infinite
        .1s;
}
```

La animación fue definida mediante:

```css
@keyframes profile__animate {

    0% {
        border-radius:
            60% 40% 30% 70% /
            60% 30% 70% 40%;
    }

    50% {
        border-radius:
            30% 60% 70% 40% /
            50% 60% 30% 60%;
    }

    100% {
        border-radius:
            60% 40% 30% 70% /
            60% 30% 70% 40%;
    }
}
```

### ¿Por qué se incorporó?

La animación busca darle personalidad al portfolio sin recurrir a elementos excesivamente llamativos.

El movimiento es lento y continuo, por lo que funciona como un detalle visual que aporta dinamismo sin distraer del contenido.

---

# Iconos

Se utilizaron librerías de iconos para complementar visualmente diferentes elementos de la interfaz.

* Boxicons
* Google icons
* Unicons
  
Los iconos se utilizan en:

* Navegación.
* Skills.
* Contacto.
* Formación.
* Botones.
* Elementos informativos.

La intención es mejorar el reconocimiento visual de cada elemento sin depender exclusivamente del texto.

---

# Formulario de contacto

El portfolio incorpora un formulario para que los visitantes puedan enviar consultas o mensajes.

El formulario solicita:

* Nombre.
* Correo electrónico.
* Mensaje.

La implementación del envío puede realizarse mediante un servicio externo de formularios (formspree), evitando la necesidad de desarrollar un backend específico para esta funcionalidad.

---

# Uso de Inteligencia Artificial

Durante el desarrollo del proyecto se utilizó **Inteligencia Artificial como herramienta de apoyo**, principalmente para resolver problemas técnicos, analizar errores y explorar alternativas de implementación.

La IA no se utilizó únicamente para generar código, sino también como herramienta de aprendizaje y consulta.
No se realizo uso de **Agentes de IA** 

### Resolución de problemas

Se utilizó IA para analizar problemas relacionados con:

* CSS.
* Responsive Design.
* Breakpoints.
* Desbordamientos.
* Flexbox.
* CSS Grid.
* Formularios.
* HTML.
* Organización del código.
* Estructura de componentes.

Por ejemplo, cuando determinados elementos producían desbordamiento horizontal en dispositivos pequeños, se analizaron las posibles causas y se revisaron propiedades como:

```css
width
max-width
padding
margin
grid-template-columns
gap
```

---

### Ajustes de diseño

También se utilizó IA para recibir sugerencias sobre:

* Distribución de elementos.
* Espaciado.
* Tamaños.
* Colores.
* Tipografía.
* Diseño responsive.
* Organización visual de las secciones.
* Animaciones.
* Experiencia de usuario.

Estas sugerencias fueron evaluadas y adaptadas al diseño final del proyecto.

---

### Generación de ideas

La IA también fue utilizada como herramienta para obtener diferentes propuestas de:

* Textos para el portfolio.
* Descripciones de habilidades.
* Presentación profesional.
* Organización de secciones.
* Ideas de diseño.
* Mejoras en la experiencia de usuario.

Las propuestas generadas fueron revisadas y modificadas para adaptarlas al estilo y objetivos del proyecto.

---

### IA como herramienta de aprendizaje

Uno de los objetivos principales fue utilizar la IA para **comprender los problemas y no simplemente copiar soluciones**.

El proceso utilizado fue:

```text
Problema
   ↓
Análisis
   ↓
Consulta a IA
   ↓
Propuestas de solución
   ↓
Prueba en el proyecto
   ↓
Corrección / adaptación
   ↓
Resultado final
```

De esta manera, la IA funcionó como una herramienta de asistencia durante el proceso de desarrollo, mientras que las decisiones finales sobre estructura, diseño y código fueron evaluadas y adaptadas al proyecto.

---

# Tecnologías utilizadas

* HTML5
* CSS3
* JavaScript
* CSS Grid
* Flexbox
* Responsive Design
* CSS Variables
* Animaciones CSS
* GitHub
* Vercel — deployment

---

# Estado del proyecto

**En desarrollo**

El portfolio continúa en proceso de construcción y puede recibir nuevas mejoras relacionadas con:

* Diseño.
* Responsive Design.
* Accesibilidad.
* Animaciones.
* Nuevos proyectos.
* Optimización.
* Funcionalidades de contacto.

---

# Deployment

El proyecto será desplegado utilizando **Vercel**.

 **Portfolio:**
``

---

# Autor

**Álvaro Gabriel Mamani**

Desarrollador Web & Diseñador

Este portfolio representa mi proceso de aprendizaje, desarrollo y crecimiento profesional en el área del desarrollo de software y diseño web.
