---
name: web-design
description: 'Use when replicating or building a web interface from a visual reference, screenshot, mockup, or design specification. Covers reference analysis, layout and component breakdown, and implementation with semantic HTML, modern vanilla CSS, and responsive design without frameworks. Trigger phrases: replicar este diseno, implementar esta captura, analizar esta imagen, construir este layout, pixel perfect UI, build this layout.'
---

# web-design

Convierte una referencia visual en una implementación web. Trabaja en **tres fases con
pausa obligatoria** entre ellas: nunca escribas código antes de que el análisis sea aprobado.

## Fase 1 — Analizar (sin escribir archivos)

1. Localiza y lee la referencia con `read` (imagen) o con `read` (spec escrita). No asumas
   contenido que no está en la referencia.
2. Extrae y registra:
   - **Layout**: qué regiones existen, su orden de lectura y cómo se distribuyen
     (grid/flex/columnas).
   - **Jerarquía visual**: qué elemento domina, qué es secundario, qué es terciario.
   - **Tokens**: colores (hex aproximados), escala tipográfica con pesos, radios, sombras,
     familia tipográfica y su respaldo.
   - **Componentes repetidos**: lo que aparece más de una vez es un componente, no HTML repetido.
   - **Estados**: hover, focus, active, disabled, y cualquier estado condicional visible.
3. Señala explícitamente lo que **no** se puede leer de la referencia (texto real, contenido de
   imágenes, datos dinámicos) y qué suposición estás haciendo.

## Fase 2 — Presentar el análisis y esperar aprobación

Entrega el análisis como texto en la conversación. **No crees ni edites archivos en esta fase.**

Detente ahí. Espera la aprobación explícita del usuario. Si el usuario corrige algo, ajusta el
análisis y vuelve a presentarlo; no avances a implementar hasta que lo apruebe.

## Fase 3 — Implementar

Solo tras la aprobación. Estructura del proyecto:

```
index.html    estructura y contenido
styles.css    todos los estilos
script.js     comportamiento, solo si la referencia es interactiva
```

Reglas de implementación:

- **Vanilla únicamente**: nada de frameworks, bundlers, CDNs ni dependencias. HTML, CSS y JS
  nativos.
- **Tokens como custom properties**: declara en `:root` los valores de la Fase 1 y consume esas
  variables. No repitas literales de color, tamaño o spacing en el resto de la hoja.
- **Componente repetido = una sola definición** de estilo, reutilizada por todos sus usos.
- **Responsive mobile-first**: define estilos para el viewport móvil y usa `min-width` para los
  breakpoints superiores.
- **Semántica primero**: `header`, `nav`, `main`, `section`, `article`, `footer`, y elementos de
  formulario nativos. No uses `div` para lo que ya existe como elemento con semántica.
- **Accesibilidad de contraste**: texto sobre fondo al menos 4.5:1. Estados de focus visibles, sin
  `outline: none` sin sustituto.
- **Scripting mínimo**: si la referencia es estática, `script.js` queda vacío o no se crea. No
  añadas interactividad, animaciones ni animaciones de entrada que no estén en la referencia.
- **No inventes contenido**: el texto y los datos son marcadores de posición explícitos
  (`Título de ejemplo`), nunca relleno de relleno tipo lorem que simule el diseño real.
- **No toques lo que no se pidió**: solo `index.html`, `styles.css`, `script.js`. No crees
  archivos adicionales, no añadas configuración, no refactorices código existente.

## Antes de declarar terminado

Verifica de forma explícita:

- [ ] La estructura sigue el orden de lectura de la Fase 1.
- [ ] No hay literales repetidos donde debía haber custom properties.
- [ ] No hay scroll horizontal en móvil.
- [ ] Cada elemento interactivo tiene estado de focus visible.
- [ ] Los colores de texto cumplen contraste.
- [ ] No hay frameworks, dependencias ni archivos extra.
- [ ] No hay interactividad o animaciones ausentes en la referencia.
