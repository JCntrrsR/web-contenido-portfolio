# Arquitectura

> Documento de vitrina: explica **cómo está construido** el sitio sin publicar el código.

## Decisión principal: sitio estático de una sola página por ruta

No hay backend ni base de datos, y no hacen falta. El producto es una **carta de presentación
comercial**: tiene que cargar rápido, verse bien en móvil y dejar claro cómo contratar.

React con Vite permite construir la interfaz con componentes y, aun así, entregar HTML y poco más,
porque cada ruta es un fragmento independiente.

## Estructura

```
App (Router)
├── Portada      → presentación + cifras + llamada a suscribirse
├── Servicios    → qué produce y para quién
├── Nosotros     → trayectoria
└── Contacto     → propuesta comercial
```

Cada ruta se compone de **secciones** reutilizables (hero, tarjetas, carrusel, cierre). Cambiar una
sección cambia todas las apariciones.

## Decisiones que sostienen el producto

**El fondo del hero es una imagen local, no un video remoto.**
Un video alojado en un servicio externo convierte la primera impresión en una dependencia: si el
enlace caduca o la red falla, el visitante ve un bloque gris. Con imagen local el hero nunca falla,
y pesa una fracción.

**El orden de las capas importa.**
El velo oscuro debe pintarse **después** de la imagen. Si va antes, la imagen lo cubre y el texto
queda sobre la foto sin contraste, ilegible.

**Las animaciones se disparan por visibilidad.**
El revelado por scroll usa un observador: el bloque no anima hasta que entra en pantalla. En una
captura o impresión, el contenido no debe quedar invisible.

**Cero dependencias pesadas.**
Siete librerías en total. El sitio no necesita más: cada una añadida se paga en tiempo de carga.

## Rendimiento

| Medida | Valor |
|---|---|
| Peso del build | ~300 KB |
| Dependencias | 7 |
| Sourcemaps en producción | desactivados |
| Imágenes | locales y comprimidas |

## Construcción

```
npm run build  →  compila TypeScript y agrupa
npm run lint   →  reglas de estilo y errores comunes
```
