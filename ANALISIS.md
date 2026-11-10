# TEMIS Estudio Jurídico — estado de la página (10-nov-2026)

Revisión de `index.html` (borrador v2) en la rama `fotos-sesion-nov`. Nada publicado.

## 0. Lo urgente: el borrador YA está en línea

- `temisestudiojuridico.com` resuelve a GitHub Pages (A 185.199.108-111.153, `www` → CNAME `victorgomez-ibg.github.io`; NS de GoDaddy, dominio registrado el 19-oct-2026, vence el 19-oct-2027).
- GitHub Pages está **activo** desde `main` (`status: built`, HTTPS aprobado hasta 17-ene-2027, `https_enforced: true`). `https://temisestudiojuridico.com` responde 200 y sirve el borrador v2 tal cual: barra «BORRADOR», recuadros rosas, bloques amarillos y un formulario que manda a WhatsApp con el **teléfono de REGUTT**.
- Lo único que lo frena es `<meta name="robots" content="noindex,nofollow">`. Cualquiera que escriba el dominio lo ve.
- El repo es **público**: si se sube esta rama, las fotos de Marisol quedan públicas en GitHub aunque no se fusione.
- **Decisión para Víctor:** o se deja así sabiendo que es visible, o se despublica Pages hasta tener el OK (eso es un cambio en GitHub; no lo toqué).

## 1. Fotos

| Recuadro | Estado | Nota |
|---|---|---|
| Foto principal (grupo, 4:3) | Vacío | Pide a varias abogadas juntas. No hay foto de grupo de TEMIS. |
| El despacho por dentro (4:5) | Vacío | Pide una consulta real. No la hay. |
| Retrato · Jazmín (4:5) | Vacío | Jazmín **no** está identificada en la sesión. |
| Retrato · Marisol (4:5) | **Puesto** | 6938 (traje blanco), recorte de media figura, ajuste cálido ligero. `img/marisol-{600,960}.{jpg,webp}` (13–66 KB). |
| Fachada (3:2) | Vacío | Benito Juárez No. 8, de día, con el logo. |

- Cuando llegue el retrato de Jazmín, debe igualar el de Marisol (fondo liso claro, media figura, de frente). Si Jazmín no puede hacer sesión igual, hay que decidir si se rehace el de Marisol para que la pareja combine.
- Alternativas de Marisol listas si no gusta la 6938: 6926 (mano en el mentón, más cercana), 6916 o 6934 (cuerpo entero, habría que recortar más).

## 2. Por confirmar (texto)

- Grado de Marisol: la página dice «Mtra.»; el 22-oct Víctor dijo «Lic. en Derecho», el 10-nov «Mtra.». Falta decidir.
- Nombres de las otras tres abogadas titulares y de las cuatro pasantes; si se publican cédulas.
- Teléfono: es el mismo de REGUTT (441 130 4944). ¿TEMIS tiene línea propia?
- Horario y correo (el Facebook dice «siempre abierto»).
- «Desde 2017» y «en 2019 le dimos formalidad»: de dónde sale el dato (no verificado aquí).
- Aviso de privacidad, razón social y responsable de datos: **sin esto no debe recibir datos de clientes** (el propio pie lo dice).
- Las zonas (Ezequiel Montes, San Juan del Río, San Joaquín, Querétaro) y «llevamos juicios en la capital»: confirmar con las socias.

## 3. Problemas técnicos

- **Encabezado en móvil (375 px):** «ESTUDIO JURÍDICO» y el botón «Consulta tu caso» se parten en dos líneas; la barra fija crece a ~90 px. Arreglo: ocultar el subtítulo bajo 420 px o acortar el botón a «Consulta».
- **Menú en móvil:** `nav` se oculta por debajo de 900 px y no hay menú alternativo. Solo queda el botón de contacto. Aceptable para una página corta; valorar un menú simple.
- **Formulario:** el mensaje «Se abrió WhatsApp con tu mensaje escrito» se muestra al hacer clic aunque WhatsApp no se abra (en escritorio sin WhatsApp no pasa nada). Cambiar a «Te llevamos a WhatsApp…» o comprobarlo. El error no tiene `aria-live`. No valida que el teléfono tenga 10 dígitos.
- **Imágenes sin usar:** `img/logo.jpg`, `img/temis-logo.jpg` (en el repo) y `img/sello.png` (217 KB, sin commitear, tampoco lo commiteé) no se usan. El favicon es `sello.jpg` (760×640, 43 KB): conviene un `favicon.png` 32/180 px.
- **Fuentes:** Google Fonts por red externa (Cormorant y Jost). Para rendimiento y privacidad, alojarlas en el repo.
- Sin `custom_404`, sin `robots.txt` ni `sitemap.xml` (404).

## 4. SEO (para cuando se publique)

- Quitar `noindex`.
- Falta `link rel="canonical"`, etiquetas Open Graph (`og:title`, `og:image`… hoy compartir el enlace en WhatsApp sale sin imagen) y JSON-LD `LegalService` con dirección, teléfono y horario (cuando estén confirmados).
- Título y descripción están bien orientados («Abogadas en Cadereyta de Montes»).
- Alta en Google Business Profile con la misma dirección y teléfono que la página.

## 5. Accesibilidad (WCAG 2.1 AA)

| Elemento | Contraste | Pasa |
|---|---|---|
| Texto cuerpo `--tinta-2` sobre blanco | 7.78 | Sí |
| Eyebrows `--oro-3` (#a9792c, 11 px mayúsculas) sobre blanco | 3.85 | **No** (texto pequeño pide 4.5) |
| `--tinta-3` (#8a7d75) sobre blanco / rosa-1 | 3.98 / 3.68 | **No** (micro, dt, etiquetas del formulario) |
| Texto blanco del botón oro sobre el degradado | 1.35–3.24 | **No** (las zonas claras del degradado) |
| Bloques amarillos `.pendiente` | 6.79 | Sí |

- Arreglo sugerido: `--oro-3` → `--oro-4` (#7d5a1f, 6.26) en textos pequeños; oscurecer `--tinta-3` a ~#736760; texto del botón oro en `--tinta` o degradado más oscuro.
- Bien: `lang="es"`, foco visible, etiquetas envolviendo los campos, `alt` en el retrato nuevo, `prefers-reduced-motion`, objetivos táctiles de 48 px.
- Pendiente: no hay `<main>`; el aviso de borrador va antes del encabezado (se quita al publicar).

## 6. Probado

- Servidor local (`python3 -m http.server`) + Chrome headless (Puppeteer): 375 px (DPR 2) y 1440 px.
- Sin scroll horizontal en ninguno (`scrollWidth` = ancho de ventana), 0 peticiones fallidas, todas las imágenes cargan. En móvil se sirve `marisol-960.webp`, en escritorio `marisol-600.webp`.
