RECICLAZARAGOZA ONE PAGE

Zona: Zaragoza (España)

Marca: ReciclaZaragoza
Logo e isotipo: assets/logo-reciclazaragoza.png y
assets/favicon-reciclazaragoza.png (proporcionados por el cliente).
Ambos archivos traen fondo casi blanco con ligero tinte verde-azulado
(#eff5f5, capturas, no PNG transparente). La cabecera y el footer se
han igualado a ese mismo tono para que el logo no muestre una caja
visible.

Colores: paleta rebrandeada al verde azulado del logo (#179988) en
vez del naranja/azul marino de la plantilla original (PuntoRecicla).

Dominio: https://reciclajeequiposinformaticos.com.es/
(CONFIRMADO por el cliente. Corregido en canonical, og:url, JSON-LD,
robots.txt y sitemap.xml — antes apuntaban a
reciclajedeordenadores.com.es en http:// sin cifrar, el dominio de la
versión de Madrid, PuntoRecicla.)

Teléfono caja y botones: +34 910 05 47 24 / +34 914 46 85 03
(mantenidos tal cual, según indicación del cliente)

IMPORTANTE — dirección física:
No se proporcionó una dirección real para Zaragoza. Se ha quitado la
dirección de Madrid (C. Joaquín María López, 26) y el bloque de
Metro/aparcamiento (específico de Madrid, sin sentido en Zaragoza).
La caja de información ahora muestra "Zona de servicio: Zaragoza
capital y alrededores" en su lugar. El enlace y el iframe de Google
Maps se han mantenido sin cambios (según indicación del cliente),
aunque siguen apuntando a la ubicación de Madrid — revisar si debe
sustituirse por una ficha de Google Business de Zaragoza.

El correo SMTP no aparece visible en la web; solo se usa en /api/contacto.
Variables Vercel compartidas: SMTP_HOST, SMTP_PORT=465, SMTP_SECURE=true, SMTP_USER, SMTP_PASS, CONTACT_EMAIL.

Google Analytics:
G-P97Y7NE5B7

HISTORIAL: el repositorio era multipágina (8 páginas /servicios/ de
reciclaje y destrucción de datos) y se convirtió a one-page; esas
páginas fueron eliminadas en commits anteriores. Como ya no existen
en el sitemap actual, se ha añadido middleware.mjs para redirigir
(301) cualquier URL antigua a la home, evitando 404 en enlaces
indexados o backlinks antiguos. Excluye /api/* y cualquier ruta con
extensión de archivo. Se añadió "@vercel/functions": "^2.0.3" a
package.json como dependencia de esta función.

REVISIÓN ADICIONAL (esta pasada):
- Ya estaba bien: banner de cookies (ya corregido en un commit
  anterior), sección SEO "Guía", menú móvil, borde blanco del chat,
  api/contacto.js con SMTP + nodemailer, teléfonos (no se han
  tocado). No se ha modificado ninguno de estos.
- Meta robots: no existía. Añadido.
- Schema.org: faltaba sameAs — añadido, reutilizando los mismos
  enlaces de Google Maps y YouTube que ya aparecían en la propia
  página (sin resolver el aviso pendiente sobre si esa ficha de Maps
  corresponde a Zaragoza o sigue siendo la de Madrid).
- .navcall: el texto largo ("Atención Telefónica 24 horas 365 días")
  deformaba la píldora del menú. Acortado a solo el número (mismo
  número, +34 914 46 85 03) y añadido white-space:nowrap como
  salvaguarda.
- H1 de portada reescrito, corto, directo y totalmente afirmativo
  (sin interrogación ni condicionales — el anterior tenía 20
  palabras): "Tu ordenador ya no se usa. Aquí cuidamos tus datos."
  Tamaño del H1 aumentado: clamp(38-56px) → clamp(46-74px) en
  escritorio, 39px → 48px en móvil.

AVISOS RESUELTOS EN ESTA PASADA:
- Dominio confirmado por el cliente: https://reciclajeequiposinformaticos.com.es/
  (corregido en canonical, og:url, JSON-LD, robots.txt, sitemap.xml;
  también se aprovechó para pasarlo a https://).

AVISO PENDIENTE (heredado, sin confirmar):
- El enlace/iframe de Google Maps sigue sin confirmarse si corresponde
  a una ubicación de Zaragoza o si sigue apuntando a Madrid; no se ha
  tocado.

REVISIÓN ADICIONAL (checklist unificado de la familia, a petición del cliente):
- H1 verificado: "Tu ordenador ya no se usa. Aquí cuidamos tus
  datos." es afirmativo, corto, y con estructura distinta a la del
  repo hermano PuntoRecicla ("Reciclamos tus equipos. Protegemos toda
  tu información."). No se ha tocado.
- BUG REAL — el botón CTA de teléfono no tenía icono, a diferencia del
  de WhatsApp. Añadido (verificado con cuidado el cierre de las
  etiquetas </a>: 18 aperturas / 18 cierres).
- BUG REAL — la casilla de política de privacidad existía pero el
  texto no enlazaba a ningún sitio. Añadido el enlace estándar de la
  familia a https://kelatos.com/privacy-policy/, resaltado en el tono
  cian de la paleta (var(--cyan), #18a6c9) en vez de var(--blue), que
  en esta plantilla rebrandeada es en realidad un verde-negro oscuro
  y no un azul visible.
- BUG REAL — texto decorativo gigante ".data:after" ("DATOS", 190px)
  sin ninguna reducción de tamaño en tablet/móvil, mismo bug ya
  corregido en el repo hermano PuntoRecicla (plantilla compartida).
  Añadida (100px tablet, 64px móvil).
- Añadido "Sábados, domingos y días festivos estamos cerrados" debajo
  del horario.
- No se ha añadido franja de aviso de servicio técnico independiente:
  no aplica a este negocio (reciclaje de equipos y destrucción de
  datos, sin el enfoque de reparación de marcas concretas del resto
  de la familia).
- Verificado sin bugs: no existe ninguna etiqueta rotada tipo
  hero-chip (.shape es una forma decorativa sin texto); Cal.com ya
  estaba presente; schema.org ya usaba correctamente el teléfono de la
  caja de información; formulario correctamente conectado a
  /api/contacto.
