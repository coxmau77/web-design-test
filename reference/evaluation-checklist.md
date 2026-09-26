# Checklist de evaluación manual

Compara el resultado renderizado contra la referencia original en `reference/`.
Marca cada ítem. El objetivo no es perfectionismo: es detectar **qué parte del Skill
necesita ajuste**, y para eso importa distinguir entre:

- **Fallo de análisis** → el Skill leyó mal la referencia (Fase 1).
- **Fallo de implementación** → leyó bien pero ejecutó mal (Fase 3).

## Estructura y layout

- [ ] El orden de lectura coincide con el de la referencia.
- [ ] Las regiones principales están donde deben estar respecto a la referencia.
- [ ] Las proporciones entre bloques se parecen a la original.
- [ ] La alineación de los elementos internos es consistente.

> Nota: el orden de las regiones de la referencia, y no el del código.

## Tokens

- [ ] Los colores se acercan a los de la referencia.
- [ ] La escala tipográfica y los pesos coinciden.
- [ ] El espaciado entre secciones es proporcional.
- [ ] Los radios y sombras se parecen.

## Comportamiento

- [ ] En viewport móvil (~390px) no hay scroll horizontal.
- [ ] En desktop (~1440px) la composición escala correctamente.
- [ ] El orden de columnas se invierte correctamente si la referencia lo hace.
- [ ] Los estados hover/focus son visibles y coherentes con la referencia.

## Accesibilidad

- [ ] El contraste de texto es al menos 4.5:1.
- [ ] Los elementos interactivos son alcanzables por teclado.
- [ ] El foco es visible al navegar con tabulador.
- [ ] Los elementos usan etiquetas semánticas, no `div` genéricos.

## Contenido

- [ ] El texto visible está marcado como marcador de posición, no inventado.
- [ ] No hay contenido, secciones o interacciones que la referencia no tenga.
- [ ] No hay interactividad o animaciones añadidas.

## Higiene técnica

- [ ] Solo existen `index.html`, `styles.css` y `script.js`.
- [ ] No hay frameworks, CDNs ni dependencias.
- [ ] Los valores repetidos están en custom properties en `:root`.
- [ ] `script.js` está vacío si la referencia es estática.

## Resultado

Anota los tres fallos más relevantes y clasifícalos:

| # | Qué falló              | ¿Fallo de análisis o de implementación? | Sección del SKILL.md a ajustar |
|---|------------------------|------------------------------------------|--------------------------------|
| 1 |                        |                                          |                                |
| 2 |                        |                                          |                                |
| 3 |                        |                                          |                                |

El tercer paso de la tabla es el que importa: cada fila debe terminar en una instrucción
concreta del `SKILL.md`. Si no puedes señalar qué instrucción cambiar, el hallazgo no es
accionable y conviene descartarlo.
