# Referencia de diseño: variante negra

**Esto NO es la web a construir.** Es material de referencia. La web real es el tema de Shopify de JC Hats que se modifica en local con Shopify CLI. De estos diseños se van **tomando elementos sueltos**, uno por uno, cuando el cliente lo pida.

Base elegida: **fondo negro** con elementos blancos y resaltes azules. La variante café (gradiente de la gira) queda **descartada**. Las variantes verde, azul y blancas existieron solo en el artifact y no se usan.

## Qué hay aquí
- `negro/screens/` — capturas de cada pantalla y estado (leerlas primero, son lo más rápido):
  `01-inicio`, `02-menu`, `03-producto-1-gorra`, `04-producto-pareja-selector`, `05-producto-trio-selector`, `06-producto-only-the-best`, `07-carrito`, `08-carrito-con-descuento`, `09-selector-gorras`, `10-galeria-fondo-fotos`.
- `negro/src/` — código fuente de cada pantalla (HTML/CSS/JS de diseño, formato `.dc.html` del canvas; no son Liquid ni corren solos). Sirven para copiar medidas, CSS, animaciones y lógica. Los textos con `[CORCHETES]` son placeholders.
- Las imágenes salen de `../../design-canvas/assets/` (logos Tucanes y JC, 5 fotos de la gorra Club Black usadas como relleno).

## Tokens (variante negra)
- Fondo `#000000`. Texto `#ffffff`; secundarios `#b0b0b8`, `#8a8a92`, `#e6e6ea`.
- Tarjetas/paneles: blanco translúcido `rgba(255,255,255,.05–.07)` con borde `rgba(255,255,255,.1–.25)`.
- Resalte azul: relleno `#0202ba`; bordes/brillos/selección `#2020f0` (sobre negro `#0202ba` solo se ve tenue; para texto resaltado se usa blanco).
- Fotos de producto: tarjeta clara con degradado `#f4f4f6 → #d9d9df → #b9b9c4` y la foto con `mix-blend-mode: multiply` (las fotos originales tienen fondo blanco).
- Tipografía: Roboto Mono (400/500/700) + Rock Salt para títulos manuscritos.
- Botón principal: pastilla `border-radius:999px`, relleno `#0202ba`, texto blanco, sombra `0 10px 28px rgba(32,32,240,.5), 0 3px 0 #00007a`, hover sube 2 px. Móvil: ancho completo.
- Pastilla de descuento: fondo blanco, texto negro, 12 px, negrita (700), cuelga del borde superior de la tarjeta.

## Piezas que se pueden tomar (cuando se pida)
1. **Upsells de producto**: barra "1 Gorra" + 2 tarjetas (Pareja, Trío) + barra larga "Only The Best" con borde animado.
   Precio base de maqueta $999: Pareja −10 % ($1,798), Trío −20 % ($2,398), Only The Best −35 % ($3,247). Abren con "1 Gorra" seleccionada.
2. **Selector de gorras** (Pareja/Trío): búsqueda + pastilla de secciones (Más nuevas, Best sellers, Colaboraciones, Denim, Clásicas), 5 gorras y "Ver más"; no muestra la gorra que se está viendo; los cuadros "+" se llenan con la foto elegida.
3. **Detalle de Only The Best**: texto de la colección (limitada, firmada por Mr. JC) + 5 tarjetas (Tucanes de Tijuana grande, Marca Registrada, Edición Especial, Enigma Norteño, Natanael Cano) con pastilla de color.
4. **Carrito**: franja "tu carrito vence en 10:00", "X y otros 1,493 ya compraron", entrega estimada con corte a las 7 am (solo lógica, no se muestra la hora), "Completa tu pedido" (2da gorra −10 %, 3ra −20 %, Only The Best −35 %), subtotal con descuento por paquete.
5. **Fondo de fotos** claro con degradado y gorra negra encima (galería y miniaturas).
6. **Footer**: logo Tucanes, correo "No te pierdas el siguiente drop", enlaces, redes, formas de pago (placeholders).
7. **Animaciones ligeras**: `pop` (aparece subiendo y desvaneciéndose), `pip` (rebote al llenarse un "+"), `bar` (rebote al seleccionar), aro con `conic-gradient` animado con `@property --ang`. Respetan `prefers-reduced-motion`.

## Pendiente de resolver en Shopify (no lo resuelve el diseño)
- Descuentos por cantidad (10/20/35 %): descuentos automáticos de Shopify o una función de descuento.
- El selector de gorras necesita productos/colecciones reales y orden por novedad y ventas.
- Fotos reales de la gorra Total Black y de cada colaboración; textos, precios y formas de pago reales.
