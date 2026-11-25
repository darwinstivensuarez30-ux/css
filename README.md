# suba actividad 3
# Catálogo de Productos

## Hallazgos: Centralización de Identidad Visual y Espaciado

**1. Variables declaradas**

En el :root declaré estas variables:

- Colores: --color-primario, --color-secundario, --color-fondo,
  --color-fondo-tarjeta, --color-texto, --color-texto-claro, --color-negro,
  --color-encabezado, --color-nav, --color-nav-texto, --color-aside,
  --color-enlace-aside, --color-footer, --color-enlace-footer,
  --color-boton, --color-boton-destacado
- Tipografía: --fuente-principal (Roboto de Google Fonts)
- Espaciados: --espaciado-pequeno (8px), --espaciado-medio (16px),
  --espaciado-grande (24px)

**2. Ventaja de reutilizar márgenes y rellenos**

Antes ponía un número distinto en cada selector y todo quedaba desparejo.
Ahora uso solo tres medidas, entonces todas las tarjetas tienen el mismo
espacio, y si quiero cambiarlo lo hago en un solo lugar.

**3. Cómo :root evita colisiones visuales**

Si cada selector tiene su propio color o medida, a medida que crece el CSS
se empiezan a ver cosas diferentes sin querer. Con :root todos leen el mismo
valor, así que la página se mantiene uniforme.

**Lo que vi en DevTools**

vi que solo hay que cambiar el color que quieras desde arriba y si esta vinculado a otra parte se le cambia porque arriba se hizo+

---
# subactividad 4
## Hallazgos: Pseudoclases y Pseudoelementos

**1. Diferencia entre pseudoclase y pseudoelemento**

La pseudoclase cambia cómo se ve un elemento cuando pasa algo, como :hover,
:active o :focus. El pseudoelemento crea contenido nuevo desde el CSS que no
está en el HTML. Usé ::before para el punto del menú y ::after para la
insignia de "¡Oferta!".

**2. Por qué :focus es importante para la accesibilidad**

Hay gente que navega con Tab y no con mouse. Si el enlace no se marca, no
saben dónde están. Por eso le puse un contorno y un fondo negro con :focus.

**3. Por qué decorar con ::before y ::after**

Así el HTML queda limpio, sin etiquetas vacías solo de adorno, y si quiero
cambiar la insignia lo hago en un solo lugar del CSS.

**Lo que vi en DevTools**

al activar hover vi que el boton cambiaba al pasar el cursor y con before y after que se le agrefaron 2 puntos en filtros y se agrego oferta al lado de compra



# subatividadb 5
## Hallazgos: Arquitectura BEM y Modularidad

### 1. ¿Qué significa BEM y cómo se escribe?

BEM significa **Block, Element, Modifier** (Bloque, Elemento, Modificador). Es una forma de ponerle nombre a las clases CSS para que se entienda a simple vista qué hace cada una y a qué parte de la página pertenece.

Se escribe así:

```
bloque__elemento--modificador
```

- **Bloque:** el componente completo e independiente. Ejemplo: `.card`
- **Elemento:** una parte que vive dentro del bloque, se une con doble guion bajo (`__`). Ejemplos: `.card__title`, `.card__price`, `.card__button`
- **Modificador:** una variación del bloque o elemento, se une con doble guion medio (`--`). Ejemplos: `.card--destacada`, `.btn--secundario`

En mi catálogo, la tarjeta de producto es el bloque `.card`, su título es `.card__title` y la tarjeta resaltada es `.card--destacada`.

### 2. ¿Por qué dividir el CSS en varios archivos facilita el trabajo colaborativo?

Antes tenía todo en un solo archivo `style.css` largo y difícil de leer. Ahora cada componente tiene su propio archivo (`tarjeta.css`, `botones.css` y `menu-lateral.css`) y todos se conectan con `@import`.

Esto ayuda al trabajo en equipo porque:

- Cada persona puede trabajar en un componente distinto sin pisar el trabajo de otra.
- Se reducen los conflictos en Git, ya que es menos probable que dos personas editen el mismo archivo.
- Es más fácil encontrar y corregir algo: si falla el botón, voy directo a `botones.css`.
- El proyecto puede crecer a miles de líneas sin volverse un caos.

### 3. ¿Cómo evita BEM la guerra de especificidad?

La especificidad es el "peso" que el navegador le da a cada selector para decidir cuál estilo gana. Un selector anidado como `.producto h2` pesa más que una sola clase, y para sobrescribirlo hay que escribir otro todavía más pesado, y así se genera una "guerra" difícil de controlar.

Con BEM todos los selectores son **una sola clase plana** (por ejemplo `.card__title`), y todos pesan lo mismo (10). Así:

- No hay anidamientos que se sobrescriban entre sí.
- El orden de la cascada es predecible: si dos reglas pesan igual, gana la que está después.
- Se evitan los `id` (peso 100), como el antiguo `#btn-destacado`, que fue reemplazado por el modificador `.btn--destacado`.
- Puedo agregar nuevos estilos sin miedo a que otro selector choque con ellos.

### Nota técnica sobre `@import`

La guía indica poner los `@import` debajo del `:root`. Sin embargo, en CSS un `@import` solo funciona si está **antes de cualquier otra regla**; si va después, el navegador lo ignora. Por eso los coloqué al inicio de `style.css`. Las variables del `:root` siguen disponibles en todos los módulos.