# TEMIS Estudio Jurídico — estado de la página (10-nov-2026)

Rama `fotos-sesion-nov`, sin push ni merge. Nada publicado desde aquí.

## 0. Lo urgente: el borrador YA está en línea

- `temisestudiojuridico.com` resuelve a GitHub Pages (A 185.199.108-111.153, `www` → `victorgomez-ibg.github.io`; DNS en GoDaddy; dominio del 19-oct-2026 al 19-oct-2027).
- Pages publica desde `main` (`status: built`, HTTPS aprobado hasta 17-ene-2027). Hoy sirve el borrador v2 de `main` con la barra «BORRADOR» y el teléfono de REGUTT. Solo lo frena el `noindex`.
- El repo es **público**: subir esta rama expone las fotos de Marisol aunque no se fusione.
- **Decide Víctor:** dejarlo visible o despublicar Pages hasta el OK.

## 1. Imágenes

Criterio (Víctor, 10-nov): las mujeres de la sesión de fotos también son de TEMIS. Jazmín es la «G» de la lámina quien-es-quien (confirmado el 10-nov). Con nombre solo Marisol, Jazmín, Katie Reséndiz, Ana Karen Maqueda y Olivia Trejo; las demás (C, L, M), solo como ambiente y sin nombre. Nada de fotos con hombres. Ana Karen A. Ledesma no va.

| Lugar | Foto | Notas |
|---|---|---|
| Foto principal (4:3) | Seleccion-34, recortada a la derecha | Seis mujeres: Olivia (B), C, Marisol (A), Ana Karen Maqueda (D), Jazmín (G) y Katie (E). El hombre del extremo derecho queda fuera del recorte sin dejar ninguna parte de él. Alt sin nombres. |
| Socias · Marisol (4:5), primero | 6938 (traje blanco) | Media figura. |
| Socias · Jazmín (4:5), segunda | Seleccion-44, **original del fotógrafo** (3648×5472, `_insumos/`, fuera del repo) | La eligió ella. Media figura, mismo ajuste cálido que Marisol; exportada a 640/960 px (WebP + JPG). |
| Colaboradoras · Lic. Katie Reséndiz González | Seleccion-24 | Colaboradora (confirmado por Víctor, 10-nov). |
| Colaboradoras · Lic. Ana Karen Maqueda García | Seleccion-22 | Colaboradora (confirmado por Víctor, 10-nov). |
| Colaboradoras · Olivia Denisse Trejo Hernández | Seleccion-16 | Colaboradora (confirmado por Víctor, 10-nov). |
| Asesoría sin costo (4:5) | Seleccion-56, **original del fotógrafo** (3648×5472, `_insumos/`, fuera del repo) | Las dos socias juntas: Marisol de pie (vestido rojo) y Jazmín sentada (traje rojo); el texto alternativo las nombra. Exportada a 640/960/1280 px. Sustituye a Seleccion-57 y a la ilustración de IA. |
| Contacto (4:3) | Seleccion-41 | Olivia y C, sonrientes. Alt sin nombres. |
| Servicios (3:2) | **GENERADA CON IA** (Gemini `gemini-3-pro-image`, 10-nov) | Balanza, libreta y rosas secas, sin personas ni texto. |
| El despacho por dentro (4:5) | **GENERADA CON IA** (Gemini `gemini-3-pro-image`, 10-nov, variante 2 de 3) | Consulta en una mesa junto a la ventana; la abogada de espaldas, la clienta desenfocada; sin texto ni logos. Texto alternativo: «Imagen ilustrativa…». **Reemplazable por foto real del despacho.** Las variantes 1 y 3 están en `_insumos/` (fuera del repo). Exportada a 640/960/1280 px. |
| Fachada (3:2) | Vacío | Benito Juárez No. 8. No se sustituye con IA. |
| Imagen para compartir (1200×630) | `og-temis.jpg` | Sello y tipografía, sin personas. |

- Todas las fotos llevan el mismo ajuste cálido ligero (ganancia R 1.055 · G 1.035 · B 1.005) para que el fondo gris azulado del estudio pase a blanco cálido. Los retratos son 4:5 de media figura; el encuadre de Olivia es un poco más cerrado porque la toma original es de cuerpo entero.
- Fuente: ~/Projects/regutt-web/fotos-sesion/seleccion (sesión del 10-nov). Los nombres salen de equipo-ref/EQUIPO.md.

## 2. Por confirmar (texto)

- Grado de Marisol: la página dice «Mtra.»; el 22-oct se confirmó «Lic. en Derecho», el 10-nov «Mtra.».
- Quiénes completan las cinco titulares y las cuatro pasantes; cédulas.
- Teléfono (es el de REGUTT: 441 130 4944), horario y correo.
- «Desde 2017» y «2019»: origen del dato no verificado (por eso no está en el JSON-LD).
- Zonas de atención y «llevamos juicios en la capital».
- Aviso de privacidad, razón social y responsable de datos: **sin esto el formulario no debe recibir datos de clientes**.

## 3. Arreglado en esta rama

- **Encabezado móvil:** «Estudio Jurídico» y «Consulta tu caso» en una sola línea a 320, 375 y 1440 px (medido con rangos de texto).
- **Contraste AA:** `--oro-txt` #866020 para dorados pequeños (≥4.66:1 incluso sobre rosa-2), `--tinta-3` #6f635c (≥5.4:1), botón oro con texto tinta sobre un degradado más claro (≥4.77:1 en todo el degradado), `.oro-txt` grande con degradado oscuro (≥3.2:1).
- **Formulario:** ya no afirma que WhatsApp se abrió. Dice «Te llevamos a WhatsApp con tu mensaje listo… Si no se abrió, toca aquí» con el mismo enlace wa.me. Valida nombre y 10 dígitos, errores con `role="alert"`, aviso con `role="status"`.
- **SEO:** canonical, Open Graph y Twitter (`summary_large_image`), JSON-LD `LegalService` solo con datos de la página (nombre, dirección, zonas, áreas, socias; sin teléfono, horario, correo ni año), `robots.txt` (permite rastrear para que Google lea el noindex) y `sitemap.xml`. **El `noindex` sigue mientras sea borrador**; al publicar se quita junto con la barra `.draft`.
- **Servicios:** siete áreas con íconos SVG de línea propios (familia, civil, administrativo, agrario, laboral, contratos, gestión notarial). Familia como tarjeta principal. Solo los textos que ya estaban.
- **Asesoría sin costo:** íconos propios por caso e ilustración.
- **Movimiento** (solo transform/opacity, 300–700 ms, ease-out): aparición escalonada al bajar (IntersectionObserver), entrada del hero, elevación y dibujo de íconos al pasar el cursor, cabecera que se compacta al bajar, subrayado del menú, pulso discreto del botón de WhatsApp. Con `prefers-reduced-motion` no se anima nada. Sin JS o si el script no arranca en 2.5 s, todo queda visible (probado).
- **Orden de socias:** Marisol primero y Jazmín después (tarjetas y JSON-LD).
- **Tarjeta de Jazmín** (audio de WhatsApp del 10-nov; transcripción en `_insumos/`, fuera del repo): «Mtra. Jazmín Balbuena Arriaga» (apellido confirmado por Víctor el 10-nov; antes decía «Arteaga»), socia fundadora con áreas familiar, gestión notarial y civil; formación: maestra en Derecho con énfasis en juicios orales (licenciada en Derecho), diplomado en el Código Nacional de Procedimientos Civiles y Familiares por el Centro de Estudios Jurídicos Carbonell y otro por la UAQ. Ya figura en el JSON-LD.
- Pulido: «Saltar al contenido», `<main>`, sello transparente en la portada, favicon y apple-touch-icon.

## 4. Pendiente técnico

- Menú en móvil: por debajo de 900 px solo queda el botón de contacto.
- Fuentes por Google Fonts (externas). Para privacidad y velocidad, alojarlas en el repo.
- Sin página 404 propia.
- Imágenes del repo sin usar: `img/logo.jpg`, `img/temis-logo.jpg`. `img/sello.png` (217 KB) sigue sin commitear; de él salen `sello-hero.png` y los íconos.
- Al publicar: alta en Google Business Profile con los mismos datos.

## 5. Cómo se probó

Servidor local + Chrome headless (Puppeteer, perfil temporal), a 320, 375 y 1440 px: sin scroll horizontal, 0 peticiones fallidas, 0 imágenes rotas tras la carga diferida, las 24 piezas con aparición se muestran, el formulario valida y abre wa.me en otra pestaña, y la página se ve completa sin JS y con movimiento reducido.
