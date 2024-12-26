# Comprobaciones Finales

Pasos

## Validadores
 Nos permiten saber si no rompemos ninguna regla de validación de cada lenguaje o si alguna cosa que escribimos no sigue las reglas.

Paginas como:
- [W3C Validator HTML](https://validator.w3.org/?authuser=0)
- [W3C Validator CSS](https://jigsaw.w3.org/css-validator/)

- [CSS Code Quiality](https://www.projectwallace.com/css-code-quality) (pegar sin el reset ya que no cuenta)


### Analisis de rendimiento y especificidad
Debemos analizar tanto la estructura de CSS como su performance.

Páginas:
- [Yellow Lab tools](https://yellowlab.tools/)

- [CSS Specificity Graph Generator](https://jonassebastianohlsson.com/specificity-graph/)
/ *la linea debe ser lo más recta posible*


### Lighthouse
Podemos usar la herramienta de Google Chrome que es el repositorio unlighthouse.

Página: 
- [Unlighthouse](https://unlighthouse.dev/)


### Accesibilidad
Para hacer un análisis más específico de la usabilidad podemos usar wave y para los colores otra web que nos permite confirmar si tienen el contraste suficiente.

Página: 
- [Wave](https://wave.webaim.org/)
- [Color Contrast](https://dequeuniversity.com/rules/axe/4.7/color-contrast)


## Links básicos
Para mejorar la optimización de nuestra web debemos de añadir ciertas etiquetas:

```html
<!--Configula la url principal-->
<link rel="canonical" href="http://www.midominio.com"/>

```

**¿Qué hace?**
Le indica a los motores de búsqueda (como Google) cuál es la URL "oficial" o "principal" de la página actual. Esto es importante para evitar problemas de contenido duplicado cuando una misma página puede ser accesible a través de diferentes URLs.

¿Por qué es útil? Ayuda a los buscadores a indexar correctamente tu sitio web y a mostrar la versión correcta de tu página en los resultados de búsqueda.


```html
<!--Configula la url base de todos los HREF Y SRC-->
<base href="/">
<base src="/">
```

**¿Qué hace?**
Establece una URL base para todos los enlaces (href) y fuentes (src) que no tengan una URL completa especificada.
¿Por qué es útil? Simplifica la escritura de los enlaces en tu HTML, ya que no tienes que escribir la URL completa cada vez. Por ejemplo, si tienes un enlace a una imagen dentro de una carpeta "images" y utilizas <base href="/">, puedes escribir <img src="images/imagen.jpg"> en lugar de <img src="http://www.midominio.com/images/imagen.jpg">.


## Imágenes
Se deben:
- Optimizarlas con photoshop
- Optimizarlas con TinyPNG
- Añadir Loading Lazy
- Anadir en CSS aspect-ratio

```css
img {
    aspect-ratio: auto; /* para solventar problemas lighthouse*/
}
```

## Archivos externos
Debemos descargarnos los siguientes elementos para mejorar el rendimiento.

- Descargar las tipografías de Google Fonts
- Descargar cualquier librería como Bootstrap / Tailswind
- Descargar cualquier librerpía como jQuery

    `Bootstrap:` Es una de las librerías CSS más populares, que proporciona un framework completo para crear interfaces de usuario responsivas.

    `Tailwind CSS:` Es una utilidad de bajo nivel de primera clase para construir interfaces de usuario personalizadas.

    `jQuery`: Es una librería JavaScript que simplifica la manipulación del DOM (Document Object Model) y la creación de interacciones dinámicas.












