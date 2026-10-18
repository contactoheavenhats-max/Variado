# Proyecto: Web del drop JC Hats × Los Tucanes de Tijuana

Contexto completo para continuar en otra sesión (laptop, desktop app o web). Lee todo esto antes de trabajar.
Idioma de trabajo: español. Cliente: JC Hats México (contacto.heavenhats@gmail.com).

## Qué es
Web de lanzamiento (Shopify) de **una sola gorra Total Black** en colaboración con **Los Tucanes de Tijuana** (gira "Tucanes Time Tour 2026"). Diseño **móvil primero**.
Rama de trabajo: `claude/jc-hats-tucanes-transcription-qwgdqw` (repo `contactoheavenhats-max/Variado`). No crear PR si no se pide.

## Brief (notas manuscritas del cliente, fecha 16/10/26 — imagen en `reference/notas-manuscritas-web-tucanes.png`)
**Página de cuenta regresiva (cerrada)**: cerrada 30 min o 1 h antes del drop. Banner con preview del drop, contador, logo Tucanes.
**Inicio**: solo banner fijo con el video de los Tucanes, directo a venta. Header transparente, logo Tucanes e íconos. Nada más en el inicio; botón para comprar. Opcional: 2–3 secciones más abajo sobre la gorra.
**Página Gorra Tucanes**: display muy bueno con muy buenas fotos. Upsells: 3 → 1 de pareja, 1 de trío y el principal **"Only The Best"** con 5 gorras (o 4 + más colaboraciones), Edición Limitada. Video abajo. Secciones sobre la colaboración.
**Pendientes del brief**: carrito, checkout, otras páginas, formas de pago.
Lecturas dudosas: "trasp." = transparente; "Only The Best" (primera palabra se lee Ohly/Only); "5 gorras o 4 de más colaboraciones" ambiguo.

## Decisiones de diseño tomadas
- Fondo: **gradiente con los colores de la gira** (cartel en `reference/`): `linear-gradient(180deg,#0b0705 0%,#2a1a0e 45%,#6b4421 100%)`. Al cliente le gusta mucho. Texto crema `#f5ead6`, secundario `#c9b28a`/`#ecdcc0`, acento dorado `#f0b860`, pie `#050302`.
- Tipografía: Roboto Mono (cuerpo) + Rock Salt (títulos manuscritos), como el tema actual de la tienda.
- **Logo Tucanes** (`design-canvas/assets/logo-tucanes.png`, 360 px, se ve pixelado si se agranda): activo en TODA la web (header centrado con grid `1fr auto 1fr`, 60 px móvil / 88 px escritorio, y pie). **Logo JC Hats solo en el menú.**
- Hero del inicio: foto "Level Up" con grado cálido ámbar (`hero-level-up-warm.jpg`), solo en el hero. Es placeholder; falta el video de los Tucanes.
- **Botones de comprar**: pastilla dorada con degradado metálico (`#ffe29a → #f0b860 → #b87a2c`), texto oscuro, flecha →, sombra y hover que eleva; en móvil ancho completo. Secundarios "Agregar": contorno dorado, se rellena al hover. Clase `a.cta` / `button.cta-o` en el `<helmet>` de cada artboard.
- Gorra de ejemplo para la página de producto: **Club Black** (toda negra), 5 fotos (`1_95, 2-…113841.614, 3_99, 4_92, 5_93`). Fotos con fondo blanco → van en tarjeta clara.
- Paquetes en producto: 1 gorra, Pareja (2), Trío (3), **Only The Best (5, preseleccionado)**. Precios son `$[PRECIO]`.

## Diseño (canvas)
Artifact en claude.ai (privado, cuenta del cliente): https://claude.ai/artifact/8tvgX8L72dBisFTT7Db2bb
Tipo "Design" (artboards `.dc.html` + `canvas.json`). Copia local de todo en `design-canvas/project/`. Para editar: leer el artifact con Artifact `read`, editar archivos bajo `project/` y publicar con la misma `url`. Instrucciones del formato: las devuelve el propio artifact (SKILL.md / reference/format.md).
Artboards: escritorio `Main` (inicio), `Menu`, `Carrito`; móvil `Movil-Inicio`, `Movil-Menu`, `Movil-Carrito`, `Movil-Producto`. Enlazados para Play (comprar → producto → carrito; menú "Gorra Tucanes" → producto).
Imágenes subidas al artifact (`/_blob/<id>` solo válido dentro del artifact; originales en `design-canvas/assets/`):
- logo JC `18ff323b9ff06a6cef1177468b2d20c0` · logo Tucanes `4a05fccb1b1310452d2be291c720fb8b`
- hero cálido `845f2be3517e6b8086b6ee671fc57874` · cartel Tucanes (crop) `6c8234b802d32d59e88dd341f6c01fc0` · banner AV `4700f46b064a8c827f54690a65c8e6f3`
- Club Black: frente `8c4b31859b619158294a17245f6e43c5`, lateral `834e0c764ed1cec770f4f4452f5a9409`, trasera `528027e6b8eec3c33ac4450f7870696f`, 3/4 `6ac70ca378da99b39b67da3bd419f299`, interior `86aa13ae3cfc2698ee8a90742047105e`
- (otros: Devil Denim `4019a33ff99b75c8b1845840c0445954`, Pearls `8a4ab3f4623e4f25ce22f9a600994daf`)

## Tienda actual (referencia)
Copia estática del preview de Shopify (tema actual de JC Hats, inicio con banner "El AV", colección Level Up, etc.) en `tucanes-preview/` (`index.html` local + `assets/`, `original.html` sin modificar). Preview original: https://k9vuhe0uqkhel6fk-27963326538.shopifypreview.com (puede expirar). Es el tema real: la implementación final conviene hacerla en el código del tema (Liquid), no en la copia estática. La página del drop de los Tucanes aún no está en el preview.

## Estado y siguientes pasos
Hecho: transcripción del brief, copia del preview, canvas con inicio/menú/carrito (escritorio y móvil) y producto móvil.
Siguiente: producto en escritorio; cuenta regresiva (cerrada) móvil/escritorio; checkout y formas de pago; reemplazar placeholders (video Tucanes, fotos de la gorra Total Black real, textos de la colaboración, precios, logo Tucanes en alta/PNG sin fondo); conectar el paquete elegido con el carrito; luego pasar a Shopify.
Placeholders marcados con `[CORCHETES]` en el diseño. Pendiente aclarar con el cliente: si "Only The Best" son 5 gorras iguales o con otras colaboraciones.

## Accesos (qué se hereda y qué no)
No hay credenciales en este repo ni deben añadirse. Los conectores (GitHub, Shopify, Gmail, Google Drive, Higgsfield, Supermetrics, etc.) están ligados a la **cuenta de claude.ai** del cliente: en una sesión nueva con la misma cuenta aparecen solos. El repo requiere la app de GitHub de Claude instalada (ya lo está). El artifact solo lo abre su dueño salvo que lo comparta desde Share.
