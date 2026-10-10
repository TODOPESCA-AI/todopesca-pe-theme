# todopesca-pe-theme

Tema Shopify de **todopesca.pe** (tienda Shopify "Todo Pesca", moneda PEN). Tema propio "TodoPesca v2", estética blanco y negro, sin dependencias externas: no tiene carpeta `assets/`, el CSS y el JS viven dentro de cada archivo `.liquid`.

Este repo está conectado al tema de Shopify mediante la integración nativa de GitHub: lo que entra a la rama conectada se sincroniza solo con el tema, y lo que se edita en el editor de temas de Shopify se commitea solo a la rama.

## Flujo de trabajo (obligatorio)

1. Nunca trabajar directo en `main`. Crear una rama por cambio: `fix/...`, `feat/...`.
2. Probar en un tema de vista previa (no publicado) antes de tocar el tema en vivo.
3. Héctor aprueba solo después de ver **capturas reales** de las pantallas afectadas, en desktop y móvil. Sin capturas, no hay merge.
4. El merge a `main` publica el cambio. Un PR equivale a un cambio, con una descripción clara de qué cambia y por qué.

## Reglas de negocio y de marca

- WhatsApp comercial: **+51 907 665 800** (en enlaces `wa.me/51907665800`). Nunca usar el número antiguo +1 682 338 7457 ni números personales.
- Correo comercial: ventas@todopescashop.com.
- Español latinoamericano neutro: "tú/tienes/elige", nunca voseo.
- Los nombres de colores de los señuelos se dejan **en inglés**, tal cual vienen del fabricante (ej. "Chigomori Red Head").
- Sugoi se presenta como marca independiente de gama media. No mencionar que pertenece a TodoPesca.
- No mencionar la marca "Fantasy".
- No agregar logos, marcas de agua ni nombres de marca nuevos sin indicación expresa.
- DUO International: TodoPesca es distribuidor exclusivo para Perú, Chile y Ecuador. El posicionamiento es técnico, frente a imitaciones.

## Convenciones técnicas

- Etiquetas de producto con efecto en el tema: `preventa`/`reserva` (botón "Reservar" y aviso de preventa), `ocultar-precio` (muestra "Consultar precio" y quita el carrito).
- La descripción del producto se divide en `<h4>Especificaciones técnicas</h4>`: la parte de abajo va a la pestaña "Detalles técnicos". Los metafields `specs.*` y `simms_specs.*` tienen prioridad sobre esa parte.
- `snippets/cdn-w.liquid` redimensiona las URLs del CDN de Shopify (`w`) y convierte a JPEG progresivo (`f: 'pjpg'`) solo fotos sin transparencia.
- `snippets/seo-structured-data.liquid` genera Open Graph y JSON-LD (Product, Organization). Al tocar precios o variantes, validar que el JSON-LD siga siendo JSON válido.
- `sections/libro-reclamaciones.liquid` cumple el DS 011-2011-PCM y sus modificatorias. No quitar los datos del proveedor: TPGROUP S.A.C., RUC 20615215971.
- `templates/search.bss.b2b.liquid` lo usa la app B2B. No modificar.
- Los archivos JSON con encabezado `/* IMPORTANT: ... auto-generated */` también los escribe el editor de temas. Editar con cuidado y evitar conflictos.

## Historial

- 2026-10-10: versión inicial del repo desde el tema publicado "TodoPesca v2 — Correcciones 10-10". Incluye: WhatsApp nuevo en la ficha y el footer, SKU visible por variante, precio, foto y URL por variante, Open Graph y JSON-LD, fuentes sin bloqueo, CSS limpio, Libro de Reclamaciones con datos del proveedor y constancia, hero móvil en JPEG (-90 % de peso) y filtros de marca con Sugoi y ODZ.
