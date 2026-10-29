# Auditoría y Rediseño de UX/UI - App de Notas

## 1. Tabla de Auditoría Heurística de Nielsen

| Heurística                         | Problema identificado                                                                        | Solución aplicada                                                                                           | Gravedad |
| :--------------------------------- | :------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------- | :------- |
| **Visibilidad del estado**         | Al agregar o eliminar una nota no aparecía ninguna notificación confirmando la acción.       | Se implementó un mensaje dinámico (`"Nota agregada exitosamente"`) visible tras cada acción.                | Alta     |
| **Coincidencia con el mundo real** | Usaba términos ambiguos del sistema para clasificar y gestionar acciones.                    | Se cambió el lenguaje por expresiones claras como `"Título de la nota"`, `"Categoría"` y `"Eliminar nota"`. | Media    |
| **Control y libertad**             | Al hacer clic en borrar, la nota se eliminaba de inmediato sin dar opción de cancelar.       | Se añadió una ventana emergente de confirmación (`confirm()`) para cancelar la eliminación destructiva.     | Alta     |
| **Prevención de errores**          | Se podían registrar notas sin título ni contenido.                                           | Se activó la validación HTML5 (`required`) y la deshabilitación del botón si los campos están vacíos.       | Alta     |
| **Reconocer, no recordar**         | Los datos solicitados dependían únicamente de `placeholder`, perdiendo contexto al escribir. | Se agregaron etiquetas `<label>` permanentes en cada campo del formulario.                                  | Media    |

---

## 2. Justificación de Leyes de Usabilidad

- **Ley de Fitts:** El botón principal de guardado posee una altura superior a `44px` con un ancho expandido, facilitando el clic rápido y preciso sin errar el objetivo.
- **Ley de Hick:** Se agruparon las categorías de las notas en opciones predefinidas organizadas por tipo, reduciendo el tiempo de toma de decisiones.
- **Ley de Miller:** El formulario se estructuró en dos secciones delimitadas por `<fieldset>` ("1. Datos de la Nota" y "2. Clasificación"), evitando sobrecargar la memoria a corto plazo.

---

## 3. Accesibilidad y Estándares Visuales (WCAG 2.2)

- **Etiquetas y atributos:** Cada campo posee un `<label>` vinculado mediante `for` e `id`.
- **Imágenes accesibles:** Todas las imágenes cuentan con el atributo `alt` descriptivo.
- **Navegación por teclado:** Se activó la pseudo-clase `:focus-visible` con un borde naranja resaltado de `3px`.
- **Contraste de color:** Cumple con la relación mínima de contraste de `4.5:1` para texto sobre fondo.
- **Variables CSS:** La paleta de colores y espaciados están centralizados en la regla `:root`.
