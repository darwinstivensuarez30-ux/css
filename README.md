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

al activar hover vi que el boton cambiaba al pasar el cursor y con before y after que se le agrefaron 2 puntos en filtros y  se agrego oferta al lado de compra