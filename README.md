# Avengers Landing — ejercicio de clase

Landing page construida con **HTML + CSS + Bootstrap 5.3**, sin frameworks de JS
y sin build step. Es el archivo que vamos armando en clase: este repositorio
siempre tiene la última versión vista.

La regla del proyecto: **Bootstrap resuelve el LAYOUT** (grid, utilidades,
componentes) y **`styles.css` resuelve la IDENTIDAD** (color, ritmo, tipografía,
profundidad).

## Cómo abrirlo

Con la extensión **Live Server** de VS Code (recomendado: los `iframe` de YouTube
y Google Maps a veces fallan con `file://`).

Sin extensiones:

```bash
python3 -m http.server 8000
# abrir http://localhost:8000
```

## Estructura

```
index.html        Página principal (HTML completo, ya provisto)
otrapagina.html   Página secundaria
styles/
  styles.css      Lo que escribimos en clase
assets/img/       Imágenes del proyecto
```

El HTML ya está escrito. El trabajo de la clase es el CSS.

## Estado actual

`styles.css` está organizado en secciones numeradas. Vamos por acá:

| Sección | Estado |
|---|---|
| 1. Tokens (variables CSS) | hecho |
| 2. Base (reset y tipografía) | hecho |
| 3. Navbar | hecho |
| 4. Hero (CSS Grid en capas) | hecho |
| 5. Secciones | hecho |
| 6. Tarjetas | hecho |
| 7. Formularios | hecho |
| 8. Footer | hecho |
| 9. Responsive | hecho |
| 10. Movimiento reducido | hecho |

El CSS está completo. La sección 10 respeta a quien configuró su sistema para
ver menos animación: no es un extra, es una preferencia que la persona ya tomó
y que el navegador nos pasa.

## Los comentarios `PASO N`

En el `<head>` de `index.html` y al final del `<body>` hay comentarios del tipo
`<!-- PASO 2: aca va a ir Bootstrap -->`. Marcan **dónde** va cada cosa y en qué
paso de la clase la agregamos. No los borren: son el mapa del `<head>`.

## Lo que más se rompe

**El orden de los `<link>` importa.** Bootstrap va primero, `styles.css` después.
Los dos definen variables en `:root`, así que tienen la misma especificidad y
gana el último en llegar. Si invierten el orden, Bootstrap pisa todos los tokens
propios y la página se ve clara aunque el CSS esté bien escrito.

Otras dos que van a aparecer:

- **El botón hamburguesa no abre nada** → falta el `<script>` de Bootstrap, que va
  al final del `<body>`, no en el `<head>`.
- **El ícono de la lupa no aparece** → los íconos de Bootstrap son una *fuente*,
  no una imagen. Sin el `<link>` de `bootstrap-icons` no hay nada que dibujar.

---

> **Regla de oro de la clase:** nadie escribe una línea hasta que puede explicar
> qué hace. Si abren el editor antes de entender el concepto, están copiando,
> no aprendiendo.
