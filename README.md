# Xact-Vu Construction Landing Page

Landing page estática de una sola página para la oferta **Visita de Inspección Pro** de Xact-Vu Construction & Restoration en Edmonton, Alberta.

## Archivos

- `index.html`: página completa con Tailwind CDN, Google Fonts, Meta Pixel placeholder, estilos y JavaScript embebido.
- `README.md`: instrucciones de edición, deploy, formulario y tracking.

## Placeholders a reemplazar

Busca estos valores en `index.html`:

- `TU_PIXEL_ID`: reemplazar por el Meta Pixel ID real.
- `https://YOUR-WEBHOOK-URL.com/leads`: reemplazar por el webhook real del formulario.
- `(780) 000-0000` y `+17800000000`: reemplazar por el teléfono real visible y el enlace `tel:`.
- `[Reemplazar dirección]`: reemplazar por la dirección física real.
- `info@xact-vu.com`: reemplazar por el correo real.
- `Desde $X/semana`, `Desde $X/quincena`, `Desde $X/mes`: reemplazar cuando existan cuotas reales.
- Enlaces de `Política de privacidad` y `Términos`: reemplazar `href="#"` por URLs reales.

## Imágenes requeridas

Sube las imágenes dentro de una carpeta `assets/` junto a `index.html`:

- `assets/hero-aerial-roof-edmonton.webp`: hero aerial de techo terminado en Edmonton, `1920x1080`, WebP.
- `assets/shepherds-care-kensington-aerial.webp`: aerial de Shepherd's Care Foundation - Kensington Village, `1600x900`, WebP.
- Logo de Xact-Vu: SVG o PNG transparente. Actualmente el header usa un placeholder textual `XACT-VU`.
- Mapa de áreas servidas: opcional, WebP o PNG. La página incluye un placeholder visual.

Recomendacion: comprime las imágenes antes de subirlas. Para Lighthouse mobile 90+, intenta que el hero pese menos de 300-450 KB y la imagen institucional menos de 250-350 KB.

## Deploy rápido en Netlify

1. Abre `https://app.netlify.com/drop`.
2. Arrastra la carpeta que contiene `index.html`, `README.md` y `assets/`.
3. Espera a que Netlify genere la URL.
4. Prueba la página en mobile y desktop.

También puedes subir la misma carpeta a Vercel o Cloudflare Pages como sitio estático sin build command.

## Vista local

Para probar la landing en tu máquina:

```powershell
npm run dev
```

Luego abre:

```text
http://127.0.0.1:5173/index.html
```

## Conectar el formulario

El formulario envia un `POST` JSON a la constante:

```js
const LEAD_WEBHOOK_URL = 'https://YOUR-WEBHOOK-URL.com/leads';
```

### Opción Formspree

1. Crea un formulario en Formspree.
2. Copia el endpoint, por ejemplo `https://formspree.io/f/xxxxxxx`.
3. Reemplaza `LEAD_WEBHOOK_URL` con ese endpoint.
4. Verifica que el envio reciba los campos correctamente.

### Opción Make.com

1. Crea un scenario nuevo.
2. Usa el módulo `Webhooks > Custom webhook`.
3. Copia la URL generada.
4. Reemplaza `LEAD_WEBHOOK_URL`.
5. Conecta los datos a email, Google Sheets, CRM o SMS.

### Opción Zapier

1. Crea un Zap con trigger `Webhooks by Zapier > Catch Hook`.
2. Copia la URL del hook.
3. Reemplaza `LEAD_WEBHOOK_URL`.
4. Agrega acciones como email, Slack, CRM o Google Sheets.

## Verificar Meta Pixel

1. Reemplaza `TU_PIXEL_ID` en el script y en el bloque `noscript`.
2. Instala la extensión **Meta Pixel Helper** en Chrome.
3. Abre la landing publicada.
4. Confirma que se dispara `PageView`.
5. Haz clic en el teléfono y confirma el evento `Contact`.
6. Envia un lead de prueba con un webhook real y confirma el evento `Lead`.

## Notas de contenido editable

El código incluye comentarios como:

- `<!-- HERO SECTION -->`
- `<!-- OFFER STACK -->`
- `<!-- CONVERSION FORM SECTION -->`
- `<!-- FORM WEBHOOK: reemplazar URL en JavaScript al final del archivo -->`
- `<!-- EDITAR CONTENIDO: teléfono global, disponibilidad y datos de contacto -->`

Usa esos marcadores para editar textos, imágenes y placeholders sin tocar la estructura principal.

## Checklist antes de publicar

- Pixel real configurado.
- Webhook real probado.
- Teléfono real en texto y enlaces `tel:`.
- Imagen hero optimizada.
- Imagen Shepherd's Care optimizada.
- Términos y politica de privacidad enlazados.
- Cuotas de financiamiento reemplazadas.
- Prueba de envio en mobile.
