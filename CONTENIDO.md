# ALMORÍA PASTELERÍA — Contenido y especificación del prototipo

Carpeta del sitio: `C:\Users\honij\Documents\PoryectoMenuAlmoriaVe\ALMORIA_WEB\`

## 1. Marca
- Nombre: **Pastelería Almoría** (logo: "Almoría" manuscrita + "PASTELERÍA")
- Instagram: `@almoria_ve` → https://www.instagram.com/almoria_ve/
- Bio oficial: "¡Mejores Postres, Mejores Celebraciones!"
- Ubicaciones:
  1. **Tipuro** — CC Servimas
  2. **Centro** — diagonal a la Plaza Ayacucho
- Escuela de reposteros: `@escueladereposteros` → https://www.instagram.com/escueladereposteros/
- Seguidores: 30.400 (dato de referencia, no obligatorio mostrar)

## 2. Paleta de colores (obligatoria, del Word "Almoria Datos de los colores.docx")
| Uso | Color | Hex |
|---|---|---|
| Color principal | Vino tinto / borgoña | `#75151E` |
| Color secundario | Rojo intenso | `#D71935` |
| Fondo principal | Blanco cálido | `#FFFDF8` |
| Texto oscuro | Marrón vino / ciruela | `#4A1118` |
| Acento pastelero | Rosado suave | `#E9A0A8` |
| Acento gastronómico | Dorado panificado | `#D8943F` |
| Apoyo natural | Verde hoja | `#657B4B` |

Regla de uso: 60 % blanco cálido (fondos y espacios), ~25 % vino tinto (encabezados, botones,
categorías), acentos dorado/rosado/verde con moderación.

Colores medidos del PDF oficial del menú (coinciden con la paleta):
- Franja/cabecera granate `#76171B` (≈ `#75151E`)
- Fondo del patrón rojo `#B72032` (≈ `#D71935`)
- Tarjeta interior `#FFF8FA` (≈ `#FFFDF8`)

## 3. Recursos disponibles (en la carpeta del sitio)
- `assets/logo-almoria.png` — logo oficial recortado del menú (fondo granate, no recortar)
- `assets/fotos/foto-03.jpg`, `foto-04.jpg`, `foto-08.jpg`, `foto-12.jpg`, `foto-13.jpg`, `foto-14.jpg`, `foto-16.jpg`, `foto-19.jpg` — fotos usadas en portada y galería (el resto de las 22 fotos originales se descartó por peso/redundancia)
- `assets/menulibro/p01.jpg` … `p11.jpg` — las 11 páginas del PDF oficial del menú renderizadas a 1100 px de ancho (para `menu_libro.html`)
- **No hay teléfono/WhatsApp ni datos de pago reales**: los que aparecen en el sitio son **SIMULADOS y marcados como demo** (WhatsApp por local: Tipuro `wa.me/584120000001` → `0412-000-0001`, Centro `wa.me/584120000002` → `0412-000-0002`). Sustituir por los reales antes de publicar. **No hay datos de Pago Móvil en el sitio** (se eliminó el botón/modal de Pago Móvil).

## 3.1. Archivos del sitio
- `index.html` — portada: hero (logo + mosaico de 4 fotos con **dos viñetas: "Tipuro" abajo a la izquierda y "Centro" centrada justo debajo de la primera foto — la superior izquierda**), Explora (Menú, Instagram, WhatsApp — 3 placas; **sin Pago Móvil**), galería de 4 fotos con lightbox, **CTA de Cursos** (banda vino "¿Estás interesado en nuestros cursos?" → `cursos.html`), Ubícanos (2 sedes), **CTA de postulación** (al final: título "¿Quieres trabajar en Almoría?", copy sin la palabra "nosotros", **un único botón** "Postúlate" abre `#trabajaModal` "Postúlate en Almoría" con la lista de habilidades y contacto demo `talento@almoria.demo` + `0412-000-0000`, seleccionables), pie. En móvil el botón hamburguesa del header **solo muestra las rayitas** (sin texto "Menú"). El subtítulo del selector de local de menú dice "El menú ofrece una navegación en formato de libro"; el intro de EXPLORA dice "Explore la propuesta culinaria exclusiva de cada uno de nuestros espacios: Elija la ubicación de su preferencia". Nav: Inicio · Explorar · Galería · **Cursos** · Ubícanos (scroll-spy incluye `#cursos`). **Un solo enlace a Instagram** (`@almoria_ve`, en Explora); en el pie solo queda el de la Escuela de Reposteros. **Selector de local** (modal `#sedeModal`): al pulsar "Menú" (hero, placa EXPLORA o pie) pregunta "¿Qué menú quieres ver?" → `menu_libro.html?sede=tipuro` / `?sede=centro`; al pulsar la placa "WhatsApp" pregunta "¿De qué local escribes?" → `wa.me/584120000001` / `wa.me/584120000002` (demo, pestaña nueva).
- `cursos.html` — página aparte de **cursos de repostería**: fotos (foto-13/16/04), requisitos (mayor de edad · intensivo de 3 meses · sede del Centro) y bloque "¿Dónde deberías ir?" (dirección de la sede Centro + Google Maps + WhatsApp demo `wa.me/584120000002`). Sin JavaScript; enlaces de vuelta a `index.html`.
- `menu.html` — menú interactivo: 19 categorías / 103 productos, buscador, scroll-spy.
- `menu_libro.html` — propuesta de **menú tipo libro**, con page-flip, indicador de página y sonido. **Menú por local**: lee `?sede=tipuro|centro` (recuerda la última en `sessionStorage`), muestra badge "Menú de Tipuro/Centro" (arriba a la izquierda), actualiza título y genera las hojas con JS desde la config `SEDES` (hoy ambas sedes apuntan a `assets/menulibro/p01–p11.jpg` compartido; cambiar `folder` a `assets/menulibro/tipuro` y `.../centro` cuando lleguen los 2 PDFs). Sin `?sede=` y sin sesión previa muestra el **gate** de elección local (título "¿Qué menú quieres ver?", subtítulo en 2 líneas: "Explore la propuesta culinaria exclusiva de cada uno de nuestros espacios: Elija la ubicación de su preferencia" + "El menú ofrece una navegación en formato de libro").

## 4. Estructura mínima del prototipo (2 páginas)

### 4.1 `index.html` — Página de inicio
Secciones: header fijo con navegación · hero (logo + Almoría + claim + foto) ·
"EXPLORA" (placas/botones: MENÚ, INSTAGRAM, UBICACIÓN ×2) · cita o claim destacado ·
galería de fotos · ubicaciones (Tipuro y Centro) · footer con redes.
CTA principal: abrir el menú (`menu.html`).

### 4.2 `menu.html` — Menú interactivo
Debe contener TODO el contenido del apartado 5. Navegación por categorías cómoda en móvil
(pills/scroll horizontal o acordeón), buscador opcional, indicador de sección, botón "Volver al
inicio" (a `index.html`). Precios siempre con coma decimal (ej. `4,50`).

## 5. Menú oficial (transcrito del PDF "MENU 2026 L2.pdf") — verbatim

### DESAYUNOS
- AREPA RELLENA — 3,99 — *Queso Blanco y Jamón / Pollo (Reina Pepiada) / Carne Mechada +1,00 / Atún +1,00*
- VENEZOLANO — 7,99 — *2 Arepas, Carne Mechada, Queso Blanco, Tajadas y 2 Huevos*
- CACHITO — 2,99
- PASTELITO DE HOJALDRE — 2,99

### OMELETTE
- CLÁSICO — 6,99 — *Queso Mozzarella, Jamón de Pavo y Aguacate*
- POLLO / CARNE — 7,99 — *Pollo o Carne Mechada con Queso Mozzarella*
- Nota: *(TODOS ACOMPAÑADOS CON TOSTADAS)*

### ADICIONALES
- HUEVO 0,75 · TOCINETA 2,00 · QUESO MOZZARELLA 1,30 · JAMÓN AHUMADO 1,30 · JAMÓN DE PAVO 1,30 · AREPAS 1,00 · TOSTADAS 1,00 · AGUACATE 1,00 · POLLO O CARNE 2,00
  (en el PDF: HUEVO se escribe "0.75", el resto con coma — unificar en coma decimal)

### SÁNDWICHES
- SÁNDWICH CLÁSICO — 6,50 — *Jamon de Pavo, Queso Emmental, Queso Mozzarella, Lechuga, Tomate y Salsas Tradicionales*
- SÁNDWICH GRATINADO — 8,99 — *Pechuga de Pollo Asada, Queso Crema, Tomates Secos, Pesto y Salsas Tradicionales*

### CROISSANTS
- CROISSANT TRADICIONAL — 7,50 — *Queso Paisa, Jamón de Pavo, Tomate y Lechuga*
- CROISSANT FRANCÉS — 7,99 — *Jamón de Pavo, Queso Crema y Tomates Secos*
- CROISSANT AMERICANO — 7,99 — *Huevos a Gusto, Tocineta, Mermelada y Mantequilla*

### ENSALADAS
- ENSALADA CESAR — 8,99 — *Lechuga, Aderezo Cesar, Parmesano, Tocineta Chip y Crotones*
- ENSALADA CESAR C/POLLO — 11,99 — *Lechuga, Pollo a la Plancha o Crispy, Aderezo Cesar, Queso Parmesano, Tocineta Chip y Crotones*

### PLATOS FUERTES (incluyen 2 contornos: Ensalada César, Vegetales Salteados, Papas Fritas o Puré)
- PECHUGA A LA PARMESANA — 14,99 — *Pechuga de Pollo en Salsa Napole Gratinada*
- LOMITO ASADO A TÉRMINO — 16,99 — *200 Gr. de Lomito en Salsa Smoked*
- PECHUGA CRISPY GRATINADA — 14,99 — *Pechuga de Pollo Empanizada con Topping de Queso Mozzarella al Gratén*
- CORTES SALTEADOS — 16,99 — *Cortes de Carne / Cortes de Pollo, salteados en vegetales marinados en salsa del Medio Oriente*
- PECHUGA A LA PLANCHA — 11,99 — *Pechuga de Pollo a la Plancha condimentada con Pimienta y Sal*

### SNACKS
- RACIÓN DE PAPAS FRITAS — 4,50
- TEQUEÑOS (8 UND) — 7,99
- PAPAS MIX — 10,99 — *300 gr papas fritas con queso fundido, tocineta, pollo crispy y salsa*
- TENDERS DE POLLO — 8,99 — *Tenders de pollo acompañados de papas fritas y salsa*
- CANASTA DE PLÁTANO — 9,99 — *6 canastas rellenas de ensalada de pollo, atún o carne mechada*

### CROISSANT BURGUER
- CROISSANT CHICKEN — 11,99 — *Pechuga de pollo crispy, cebolla caramelizada, queso kraft, tocineta, tomates secos y salsa Almoría especial* — nota: *(Cada croissant viene acompañado con 150 gr de papas fritas)*

### DOGS
- DOG GO — 3,00 — *Pan, salchicha Plumrose, papitas y salsas tradicionales*
- DOG CHEESE — 4,50 — *Pan, salchicha Plumrose, queso cheddar, trocitos de tocineta, papitas y salsas tradicionales*
- DOG ALMORÍA — 4,50 — *Pan, salchicha Plumrose, papitas, chimichurri y topping de salsa de ajo*
- DOG SWEET BACON — 5,50 — *Pan, salchicha Plumrose, queso crema, papitas y topping de mermelada de tocineta*
- Nota: *(Todos vienen acompañados con 100 gr. de papas fritas excepto el DOG GO)*

### #COMPARTECONALMORÍA
- COMBO 1 — 18,99 — *6 Tequeños, 200 gr papas fritas, 6 tenders de pollo y 3 canastas de plátano*

### CAFÉS
- ESPRESSO 1,50 · CAFÉ NEGRO 1,50 · GUAYOYO 1,50 · MARRÓN 3,50 · CON LECHE 3,50 · CAPPUCCINO 3,50 · MOCACCINO 4,00 · LATTE VAINILLA 3,50 · LATTE ALMORÍA 3,50 · BOMBÓN 3,50 · AFFOGATO 3,50 · MACCHIATO 2,50 · CHOCOLATE CALIENTE CON CHANTILLY 4,50 · ICED COFFE 4,50

### BEBIDAS
- AGUA MINERAL 330 ML 1,20 · AGUA MINERAL 530 ML 1,50 · AGUA GASIFICADA 2,00 · REFRESCO 250 ML 1,00 · REFRESCO 1 LT 1,50 · MALTA 250 ML 1,20 · TODDY 3,50
- JUGOS NATURALES 3,00 — *Fresa / Parchita / Lechosa*
- LIMONADA 3,00 — *(Clásico o con Hierba Buena)*
- NESTEA 2,00 — *(Durazno)*
- JUGO VERDE 4,50

### INFUSIONES
- CALIENTES 2,00 · FRÍAS 4,00 — *Té Verde / Té Negro / Flor de Jamaica / Manzanilla / Frutos Rojos*

### MILKSHAKES
- FRESA 6,99 · OREO 6,99 · COOKIES & CREAM 6,99 · BROWNIE 6,99

### POSTRES FRÍOS
- CHEESECAKE PLAIN — 4,50
- CHEESECAKE — 7,00 — *Arequipe / Nutella / Fresa / Pistacho +3,50 · CON HELADO +1,00*
- MILHOJAS AREQUIPE 3,50 · QUESILLO 5,00 · TORTA QUESILLO 5,00 · PIE DE LIMÓN 4,50 · PIE DE PARCHITA 4,50 · TRES LECHES TRADICIONAL 6,00 · TRES LECHES DE AREQUIPE 6,00 · TRES LECHES DE CHOCOLATE 6,50 · TRES LECHES DE COCO 6,00 · MARQUESA DE CHOCOLATE 6,00 · MARQUESA DE OREO 7,00 · MARQUESA PASTELADA 6,00 · MARQUESA DE AREQUIPE 6,00

### CROISSANTS DULCES
- CROISSANT DE FRESA — 9,99 — *Relleno de crema pastelera, fresas y chantilly con topping de Nutella*

### GALLETAS
- GALLETA ALFAJOR 1,00 · GALLETA AVENA CON GOTAS DE CHOCOLATE 0,50 · GALLETAS CHIPS 0,75 · ALFAJOR GLASEADO 2,00 *(Merengue Italiano, chocolate oscuro, chocolate blanco)* · GALLETA NEWTON 0,85 · GALLETA PALMERITAS MINI (3 UND) 2,00 · GALLETA PASTA SECA (10 UND) 2,00 · GALLETA POLVOROSA 0,50

### POSTRES
- BROWNIE 5,50 · BROWNIE CON HELADO 6,50 · BROOKIE 5,50 · TRUFON 5,50 · FRESA CON CREMA 5,50 · TARTA DE MANZANA 6,00 · TARTA DE MANZANA CON HELADO 7,00 · TORTA DE PIÑA 5,99 · TORTA DE ZANAHORIA 6,99 · TORTA DE CHOCOLATE 7,99

## 6. Requisitos técnicos (heredados del proyecto anterior `PAGINAGUIA\`)
- HTML5 semántico en español (`<html lang="es">`), CSS y JS embebidos, sin build ni dependencias
  obligatorias (Google Fonts permitido).
- Design tokens en `:root` (CSS custom properties), espaciado/radios/sombras consistentes.
- Accesibilidad: skip-link, `:focus-visible`, `aria-label`, contraste AA, `prefers-reduced-motion`,
  navegación por teclado en el menú.
- Responsive mobile-first (360 px → desktop).
- Referencia de estilo: `PAGINAGUIA\index.html` y `PAGINAGUIA\Cuaderno.html` (mismo nivel de
  calidad, distinto contenido y paleta).
