# Nomenclaturas y Metodologías
*(Uno de los problemas básicos es el cómo nombrar las clases, y para ello debemos conocer estas dos terminologías)*
// servirá en html, css y también js

## Nomenclaturas

### Selectores en CSS
Un selector en css nos permite seleccionar una etiqueta de html según tipo de etiqueta, clase, id, atributo.
- Cuanto más complejo sea un selector más especificidad tiene.
- Los más específicos son mucho mas dificiles de controlar, que nos menos específicos.

### ¿Cómo nombrar las clases en HTML?
El nombre de las clases nos deben permitir:
- Entender que cuál es la etiqueta.
- Entender en dónde se encuentra.
- Tener un código robusto al trabajar en equipo.

Y para este problema tenemos una solución: `la convención`.

### ¿Que es una convención en CSS?
Es una norma o práctica que es aceptada por acuerdo general. En CSS algunos desarrolladores han aceptado algunas convenciones en cómo escribir nombres/variables: 
(4 nomenclaturas clasicas)

***Nombres de variantes de escritura (y selectores)***

- UPPERCASE, lowecase, Title case
- camel case: `miClase`
                *la primera letra de cada palabra va en mayúscula, exceepto la primera que es en minúscula.*
- pascal case:`MiClase`
                *todas las primeras letras de la palabra van en mayúscula, incluso la primera.*
- kebab case: `mi-clase` (archivos)
                *cada palabra va separada por un guión - .*
- snake case: `mi_clase`
                *cada palabra va separada por una barra baja _.*


`Estas convenciones` nos van a ayudar en este caso a poder escribir de manera más eficiente HTML y CSS y `son la base de lo que denominamos METODOLOGÍAS`.

## Metodologías 
Cuando hablamos de metodologías, nos encontramos que dentro de CSS hay problemas comunes:

- Malas prácticas como selectores, especificidad muy alta...
- ¿Qué nombre le pongo a una etiqueta?

Y para resolver este problema existen varias soluciones como:
    - Como escribir nomenclaturas básicas (header, wrapper...)
    - Metodologías

### DIFERENCIA entre Arquitectura y Metodología

***Metodología***
forma de trabajar exclusivamente en el código CSS

***Arquitectura***
estructurar las carpetas de un proyecto, además de trabajar con cualquier metodología

Cualquier metodología y arquitectura tienen como objetivo cumplir que CSS sea:
- comprensible
- predecible
- reutilizable
- escalabre
- modular

Hay que comprender y tener en mente siempre esta diferencia: `arquitectura` se centra en la organización de carpetas; `metoddología` se centra en cómo nombrar las clases.

*(muchos blogs y tutoriales muchas veces toman a la arquitectura y a la metdología como lo mismo, pero no es así)*

### ¿Qué es una METODOLOGÍA en CSS?
es un método a seguir para conseguir un objetivo concreto. 
Dicho objetivo en CSS es ponerle `nombre a las clases` y en términos generales se pueden dividir en dos ***"conceptos"***: 

- Bloque o estructura
- Funcionalidades o herramientas

### ¿Cuántas metodologías existen?

## Metodología BEM
es una metodologóa que se centra en el concepto de bloque o estructura. Es decir, las reglas de cómo definir clases se basan en la estructura de HTML teniendo en cuenta:
- `Bloque` es la <contenedora>
- `Elemento` son las <hijas> de la <contenedora>
- `Modificador` son <hijas> con propiedades diferentes.

**Web oficial: http://getbem.com**

### Sintaxis de BEM
los nombres de las clases no usan ningún tipo de nomenclatura como PascalCase o kebab-case y solo se usan `class`, no id.

                      Carácter            Sintaxis

`bloque`              no tiene             .bloque

`elemento`               _ _            .bloque__elemento
                  (doble guión bajo)   

`modificador`            --             .bloque__elemento--modificador
                 (doble guión medio)


*bloque: que tiene sintaxis normal, que no comienza ni por mayuscula ni por minúscula

*elementos: una etiqueta que sea item de esa etiqueta bloque.

*modificador: cuando tenemos varios de ellos donde uno solo sea diferente.

Ejemplo

HTML con BEM
```html
<ul class = "menu">
    <li class = "menu__li"></li>
    <li class = "menu__li"></li>
</ul>
```
*"menu_ _ li": como la clase solo es una (por utilizar la doble barra baja) en este caso la espeficidad de esta etiqueta es mínima*

CSS con BEM
```css
.menu {}
.menu__li{}
```
### Ventajas vs Desventajas de BEM
`ventajas` en el código de día a día:
- Los nombres de las clases en CSS son fáciles.
- Muy pensado para usar como procesadores. (SCSS)

`desventajas`:
- El HTML queda muy largo.


## SUIT CSS
es una metodología que parte del concepto de funcionalidad/utilidades (aunque también tiene en este caso el concepto de bloques, en el cual nos sentraremos) o herramientas, es decir, los nombres de las clases se basan en propiedades como color, centrar...

Y está recomendado para usar con ReactJS y las clases se organizan en base a:
- Utilidades
- Componentes


### Sintaxis de SUIT
en la sintaxis de cada elemento, debemos de tener en cuenta el tipo de nomenclatura que debemos de aplicar

                             Carácter            Nomenclatura            Sintaxis
`Utilidad`                       u-              camelCase             u-propiedad
`Namespace`                   - (antes)          camelCase             body-Header
`Componente`                                     PascalCase            Header
`Elemento (descendiente)`     -(después)         camelCase             Header-h1
`Modificador`                    --              camelCase             Header-h1--negro
`State de un componente`          .              camelCase             Header.isActive

*utilidad: para añadir utilizar, por ejemplo centrarlo con flex.
*namespace: es definir la etiqueta contenedora, es decir, donde se encuentra una etiqueta bloque.
*componente: o etiqueta contenedora, que es a la cual se le estan aplicando los estilos
*elemento(descendiente); de una etiqueta item
*modificador: se habla del doble guion para definirlo, es igual que en BEM donde se trata de un elemento diferente al resto.
*state de componentes: es utilizado mucho dentro de frameworks, el punto es la manera sintactica de diferenciarlo, independientemente de que si sea una clase o no. Por ejemplo si queremos que un header este activo es Header.isActive

Ejemplo de suit aplicado a bloque

HTML con SUITCSS
```html
<ul class = "Menu">
    <li class = "Menu__li"></li>
    <li class = "Menu__li"></li>
</ul>
```

CSS con SUITCSS
```css
.Menu {}
.Menu__li{}
```
### Ventajas vs Desventajas de SUITCSS
`ventajas`
- muy pensado para usar con procesadores (SCSS)
- por regla general se recomienda usar con ReactJS

`desventajas`
- es más dificil usarlo en una web clásica


## Diferencia BEM - SUITCSS

por ejemplo, un menú es exactamente igual aplicando bem y suit, pero la diferencia sería que en suit la etiqueta contenedora se la nombra en la clase con la primera letra en MAYÚSCULA, y los elementos también.

