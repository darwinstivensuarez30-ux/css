1. Fuentes Tipográficas (Google Fonts)
Playfair Display: Utilizada como la fuente principal (serif) para todo el cuerpo del documento (body), con un rango de peso de 400 a 900 y soporte para cursivas.

Redaction 10: Importada en los estilos (aunque no aplicada de forma global en el selector analizado).

2. Paleta de Colores (:root)
Tu diseño define una paleta basada en variables CSS con tonos tierra, olivo y acentos llamativos:

--color_primario (#6c7a6c): Tono gris-verdoso (usado en enlaces del menú de navegación y como fondo en el elemento <aside>).

--color_secundario (#4f4d46): Tono gris oscuro/marrón (usado en el fondo del footer y como color de fondo en los botones de compra).

--color_fondo (#a4ba36): Verde lima brillante (utilizado para el color de los títulos principales <h2> dentro de <main>).

--color_texto (#0d0d0f): Casi negro (utilizado para el color de los textos en los enlaces del <aside> y el footer).

3. Estructura y Estilos por Elementos
body: Cuenta con un espaciado de relleno (padding) de 20px y tipografía Playfair Display.

header: Tiene configurada una imagen de fondo (css-image-styling.jpg) adaptada mediante background-size: cover y centrada. Sus enlaces de navegación heredan el color primario y no muestran subrayado.

aside y footer:

El <aside> utiliza el color primario como fondo y textos oscuros.

El footer utiliza el color secundario como fondo y textos oscuros.

article: Posee un fondo gris (#787569) y sus encabezados de nivel 2 (h2) destacan con el color de fondo (--color_fondo).

.btn-comprar (Botón de compra):

Color de texto: Verde brillante (rgb(24, 160, 9)).

Fondo: Color secundario (#4f4d46).

Espaciado interior: 8px vertical y 12px horizontal.

Bordes: Esquinas redondeadas con un radio de 4px