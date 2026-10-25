# Ficha técnica

## Stack

| Capa | Tecnología | Por qué |
|---|---|---|
| Framework | **React 18 + Vite** | interfaz reactiva y build de menos de un segundo |
| Lenguaje | **TypeScript** | contenido y props tipados |
| Estilos | **Tailwind CSS** | consistencia visual en un solo sistema |
| Rutas | **React Router** | cuatro vistas sin recargar |
| Animación | **Framer Motion** | entrada de bloques por scroll |
| Carrusel | **Swiper** | recorrido táctil del contenido |
| Visibilidad | **react-intersection-observer** | dispara animaciones solo cuando el bloque se ve |
| Iconos | **Lucide** | set ligero y consistente |

## Tamaño del proyecto

| Métrica | Valor |
|---|---|
| Archivos `.ts` / `.tsx` | 25 |
| Líneas de código | ~1.430 |
| Dependencias de producción | 7 |
| Rutas | 4 |
| Peso del build | ~300 KB |

## Verificación

```
npm run build  →  exit 0 · 0 sourcemaps · ~300 KB
npm run lint   →  sin errores
```

## Defectos corregidos en el escaparate público

| Defecto | Efecto | Corrección |
|---|---|---|
| Fondo del hero apuntando a un **video de Vimeo** de 2021 | sin red, hero gris sin imagen | se usa la fotografía local |
| Velo oscuro **antes** de la imagen en el DOM | la imagen tapaba el velo: texto sin contraste | reordenado |
| 2 fotos pedidas a Pexels en caliente | sin red, sin imágenes | descargadas y locales |

## Límites conocidos

| Límite | Motivo |
|---|---|
| Sin backend | el escaparate no depende de servicios |
| Formulario en modo demostración | no envía correo |
| Contenido de ejemplo | no representa publicaciones reales |

## Qué demuestra al cliente

- Un sitio de marca personal **rápido** (menos de 300 KB) y sin dependencias pesadas.
- Criterio de rendimiento: animaciones que no bloquean y medios locales.
- Capacidad de detectar por qué un hero "no muestra nada" y corregirlo sin rehacer el diseño.
