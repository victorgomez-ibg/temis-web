# TEMIS Estudio Jurídico — estado de la página (10-nov-2026)

Rama `fotos-sesion-nov`, sin push ni merge. Nada publicado desde aquí.

## 0. Lo urgente: el borrador YA está en línea

- `temisestudiojuridico.com` resuelve a GitHub Pages (A 185.199.108-111.153, `www` → `victorgomez-ibg.github.io`; DNS en GoDaddy; dominio del 19-oct-2026 al 19-oct-2027).
- Pages publica desde `main` (`status: built`, HTTPS aprobado hasta 17-ene-2027). Hoy sirve el borrador v2 de `main` con la barra «BORRADOR» y el teléfono de REGUTT. Solo lo frena el `noindex`.
- El repo es **público**: subir esta rama expone las fotos de Marisol aunque no se fusione.
- **Decide Víctor:** dejarlo visible o despublicar Pages hasta el OK.

## 1. Imágenes

| Lugar | Estado | Origen |
|---|---|---|
| Foto principal (grupo, 4:3) | Vacío | Falta foto real del equipo. **No se sustituye con IA.** |
| El despacho por dentro (4:5) | Vacío | Falta escena real. **No se sustituye con IA.** |
| Retrato · Marisol (4:5) — va primero | **Puesto** | Foto real 6938 de la sesión de nov. (traje blanco), media figura, ajuste cálido ligero. `img/marisol-*` |
| Retrato · Jazmín (4:5) — va segunda | Vacío | Jazmín no está identificada en la sesión. **No se sustituye con IA.** |
| Fachada (3:2) | Vacío | Benito Juárez No. 8. **No se sustituye con IA.** |
| Servicios (ilustración 3:2) | Puesto | **GENERADA CON IA** (Gemini `gemini-3-pro-image`, 10-nov): balanza, libreta y rosas secas. Sin personas ni texto. `img/ilus-servicios-*` |
| Asesoría sin costo (ilustración) | Puesta | **GENERADA CON IA** (Gemini `gemini-3-pro-image`, 10-nov): mesa con dos tazas, flores y carpeta junto a la ventana. Sin personas ni texto. `img/ilus-apoyo-*` |
| Imagen para compartir (`og-temis.jpg`, 1200×630) | Puesta | Hecha con el sello del logo y la tipografía (Cormorant/Jost, OFL). Sin personas. |

- Las dos ilustraciones de IA llevan `alt=""` (decorativas) y no representan el despacho real. Si TEMIS prefiere no usar IA, se cambian por fotos propias en el mismo formato.
- El retrato de Jazmín debe igualar el de Marisol (fondo liso claro, media figura, de frente).
- Alternativas de Marisol: 6926 (mano en el mentón), 6916 o 6934 (cuerpo entero, más recorte).

## 2. Por confirmar (texto)

- Grado de Marisol: la página dice «Mtra.»; el 22-oct se confirmó «Lic. en Derecho», el 10-nov «Mtra.».
- Nombres de las otras tres titulares y las cuatro pasantes; cédulas.
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
- Pulido: «Saltar al contenido», `<main>`, sello transparente en la portada, favicon y apple-touch-icon.

## 4. Pendiente técnico

- Menú en móvil: por debajo de 900 px solo queda el botón de contacto.
- Fuentes por Google Fonts (externas). Para privacidad y velocidad, alojarlas en el repo.
- Sin página 404 propia.
- Imágenes del repo sin usar: `img/logo.jpg`, `img/temis-logo.jpg`. `img/sello.png` (217 KB) sigue sin commitear; de él salen `sello-hero.png` y los íconos.
- Al publicar: alta en Google Business Profile con los mismos datos.

## 5. Cómo se probó

Servidor local + Chrome headless (Puppeteer, perfil temporal), a 320, 375 y 1440 px: sin scroll horizontal, 0 peticiones fallidas, 0 imágenes rotas tras la carga diferida, las 24 piezas con aparición se muestran, el formulario valida y abre wa.me en otra pestaña, y la página se ve completa sin JS y con movimiento reducido.
