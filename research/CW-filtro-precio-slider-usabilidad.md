---
created: 2026-05-20
tags:
  - research
  - filtros
  - slider
  - precio
  - tarea-2.2
fuentes:
  - https://baymard.com/blog/slider-interfaces
  - https://www.nngroup.com/articles/gui-slider-controls/
  - https://uxplanet.org/mobile-ux-design-sliders-761ce4bb2a86
---

# Research — Usabilidad de Sliders de Precio en Filtros

## Diagnóstico del slider de Prodesa

El filtro de precio de Prodesa muestra: **Desde $140.948.000 — Hasta $2.200.000.000** en escala lineal, solo arrastrable, sin campos de texto.

Valentina quiere filtrar hasta $200M. Eso representa apenas el **9% del ancho total del slider** ($200M / $2.2B). En mobile, debe arrastrar la bolita derecha hasta casi el extremo izquierdo de la barra — una operación de precisión extrema en pantalla táctil.

---

## Problemas identificados por la investigación

### 1. Escala lineal inadecuada (Baymard)
- El **83% de los sitios usa escala lineal** a pesar de que los productos se concentran en un rango estrecho
- Cuando los precios se agrupan entre $140M y $300M, la escala lineal desperdicia el 90% del ancho del slider controlando solo el 2% de los productos disponibles
- **Consecuencia para Prodesa:** Valentina no puede seleccionar $200M con precisión — cada pixel representa ~$20M de variación

### 2. Sin campo de texto (Baymard)
- Los campos de texto actúan como **fallback para entrada precisa**
- Sin ellos, el usuario no puede escribir el valor exacto que tiene en mente ($200M)
- La ausencia de texto también genera ambigüedad sobre si hay uno o dos valores de control
- **Recomendación:** slider + campos editables "Desde $___" y "Hasta $___" sincronizados

### 3. Problema de touch target en mobile (NN/G + Baymard)
- El target táctil mínimo recomendado es **44x44px**
- Las bolitas de arrastre en mobile frecuentemente son más pequeñas
- En iOS/Android, los sliders HTML5 requieren a veces 2+ intentos para que el dedo "agarre" el handle
- **Consecuencia:** en mobile es incómodo y frustrante arrastrar con precisión — especialmente con un rango tan amplio

### 4. Más del 50% de usuarios malinterpretan los sliders dobles (Baymard)
- Muchos usuarios intentan hacer clic en un punto de la barra en vez de arrastrar las bolitas
- En el caso de Prodesa, hacer clic en la barra no hace nada útil — genera confusión

---

## Patrón recomendado

```
[slider visual]
Desde: [$________] Hasta: [$________]  ← campos de texto editables sincronizados
```

Adicional: histograma de distribución de proyectos sobre el slider (+20-30% engagement según Baymard).

---

## Impacto en Valentina

Valentina tiene un presupuesto mental claro: $200M. No puede escribirlo. Debe arrastrar una bolita en un rango de $2.2B con el pulgar en mobile. Alta probabilidad de:
- Seleccionar un rango incorrecto por falta de precisión
- Frustrarse y abandonar el filtro
- Desconfiar del precio mostrado en resultados

---

## Fuentes

- [Improve Form Slider UX With These 5 Requirements — Baymard](https://baymard.com/blog/slider-interfaces)
- [Slider Design: Rules of Thumb — NN/G](https://www.nngroup.com/articles/gui-slider-controls/)
- [Mobile UX Design: Sliders — UX Planet](https://uxplanet.org/mobile-ux-design-sliders-761ce4bb2a86)
