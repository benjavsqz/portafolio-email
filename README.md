# Correo a prueba de Outlook

Cinco plantillas de correo HTML escritas a mano, con la justificación técnica de cada decisión
y una matriz de soporte por cliente de correo.

**→ [Ver el portafolio](https://benjavsqz.github.io/portafolio-email/)**

## Las plantillas

| Archivo | Tipo | Qué resuelve |
|---|---|---|
| [`01-confirmacion-reserva.html`](01-confirmacion-reserva.html) | Transaccional | Confirmación de pedido con abono parcial del 50% y saldo pendiente |
| [`02-carrito-abandonado.html`](02-carrito-abandonado.html) | Ciclo de vida | Recuperación de carrito con contenido personalizable y salida alternativa |
| [`03-campana-promocional.html`](03-campana-promocional.html) | Campaña | Tres columnas que se apilan sin depender de media queries, con hero oscuro |
| [`04-hero-imagen-fondo.html`](04-hero-imagen-fondo.html) | Pieza visual | Imagen de fondo con texto encima, resuelta con VML para Outlook y color de respaldo |
| [`05-catalogo-visual.html`](05-catalogo-visual.html) | Pieza visual | Portada, fichas de producto con foto y cinta de estado, con respaldo para imágenes bloqueadas |

## Técnicas aplicadas

- **Tablas anidadas** con `role="presentation"` — Outlook para Windows renderiza con el motor de Word desde 2007
- **CSS crítico inline** — la app móvil de Gmail elimina el bloque `<style>`
- **Botones bulletproof con VML** dentro de condicionales `<!--[if mso]>` — Word ignora `border-radius` y `padding` en un `<a>`
- **Diseño base de una columna** — Yahoo y varias versiones de Gmail ignoran las media queries, así que la query mejora pero no sostiene
- **Modo oscuro en dos dialectos** — `prefers-color-scheme` y el atributo `[data-ogsc]` que inyecta Outlook.com
- **Preheader oculto** — controla el texto que la bandeja muestra junto al asunto
- **Sin dependencia de imágenes** — logo en texto y bloques de color en celdas, para que el mensaje se entienda con las imágenes bloqueadas
- **Altura táctil mínima de 46 px** en botones y enlaces del pie
- **Fondos de imagen a prueba de balas** — `background=` + `background-image` + `v:rect`/`v:fill` para Outlook, sobre un `bgcolor` de respaldo
- **Imágenes al doble de resolución** con `width`/`height` en atributos y `max-width:100%` en CSS, y `alt` con estilo propio

## Uso

Son archivos HTML planos, sin dependencias ni compilador. Se abren, se editan y se cargan
en cualquier plataforma de envío.

La marca *Rutas del Sur* es ficticia y existe sólo para dar contenido real a la muestra.

---

Benjamín Vásquez Aguiló · [shifters.cl](https://shifters.cl)
