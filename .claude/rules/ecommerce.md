# Patrones de e-commerce

## Precios y moneda
- Los precios se almacenan siempre en **céntimos** (enteros) para evitar errores de punto flotante.
  - Correcto: `precio = 1999` (19,99 €)
  - Incorrecto: `precio = 19.99`
- Formatear al mostrar con una función centralizada: `formatearPrecio(1999)` → `"19,99 €"`.
- El IVA se calcula y muestra por separado; no incluirlo en el precio base almacenado.

## Carrito
- El carrito persiste en `localStorage` como array de `{ idProducto, cantidad, precioUnitario }`.
- Nunca confiar en el precio enviado desde el cliente en el checkout — recalcularlo desde la fuente de verdad.

## Productos
- Cada producto tiene: `id`, `nombre`, `descripcion`, `precio` (céntimos), `stock`, `imagenes[]`, `categoria`.
- Si `stock === 0`, mostrar "Agotado" y deshabilitar el botón de añadir al carrito.

## Flujo de compra
1. Listado → Detalle de producto → Carrito → Checkout → Confirmación.
2. El checkout no debe requerir cuenta — permitir compra como invitado.

## Accesibilidad en componentes clave
- Botones de acción ("Añadir al carrito", "Comprar") deben tener `aria-label` descriptivo.
- Las imágenes de producto requieren `alt` con nombre del producto.
