# Referencia visual

Coloca aquí la imagen o captura que se usará como objetivo de diseño.

## Uso

1. Copia el archivo a este directorio (`reference/`).
2. Nómbralo `reference.png` o `reference.jpg` (PNG para capturas con texto nítido).
3. Invoca el skill `web-design` indicando la ruta.

```bash
#ejemplo
cp ~/Desktop/mi-captura.png reference/reference.png
```

## Notas

- El archivo se lee como adjunto visual, no se analiza con OCR: la nitidez y el tamaño
  importan. Evita capturas escaladas por debajo de su resolución original.
- Si la referencia tiene varias vistas (desktop, móvil, estados), conviene nombrarlas
  `reference-desktop.png`, `reference-mobile.png`, etc., e indicar cuál es la principal.
- Mantén el archivo en el repositorio durante la prueba: sirve para reintentar la Fase 3
  sin volver a buscar la imagen.

## Evaluación

Al terminar la implementación, usa [`evaluation-checklist.md`](./evaluation-checklist.md) para
comparar el resultado contra la referencia.
