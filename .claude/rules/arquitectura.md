# Arquitectura del proyecto

## Estructura de carpetas objetivo

```
prototipo-tienda-online/
├── src/
│   ├── componentes/     # Componentes reutilizables de UI
│   ├── paginas/         # Vistas completas (inicio, producto, carrito, checkout)
│   ├── servicios/       # Llamadas a API y lógica de negocio
│   ├── utilidades/      # Funciones puras reutilizables
│   └── estilos/         # CSS/SCSS globales y variables
├── public/              # Assets estáticos (imágenes, favicon)
├── sdd/                 # Documentación de diseño y planificación
└── CLAUDE.md
```

## Principios
- Separar lógica de negocio (servicios/) de la lógica de presentación (componentes/).
- Los componentes no llaman directamente a APIs; usan funciones de `servicios/`.
- Preferir composición sobre herencia.

## Estado de la aplicación
- El carrito y la sesión de usuario son estado global — centralizar en un único lugar.
- El resto del estado es local al componente que lo necesita.

## Routing
- Rutas principales: `/`, `/producto/:id`, `/carrito`, `/checkout`, `/confirmacion`.
