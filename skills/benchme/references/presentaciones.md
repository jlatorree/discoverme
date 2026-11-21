# Presentaciones HTML

Las presentaciones las genera el skill **frontend-slides**. benchme prepara el pedido y lo invoca.

## 1. Pregunta al usuario

- ¿Qué versión: completa, ejecutiva o ambas?
- ¿Tienes un design.md (el sistema de diseño de tu empresa)?
  - Sí → pide la ruta.
  - No → que describa el estilo que quiere, o que frontend-slides le muestre sus propuestas.

## 2. Invoca frontend-slides con todo resuelto

Pásale estas respuestas para que no las vuelva a preguntar:

- **Propósito**: presentación interna.
- **Contenido**: listo. El archivo es el informe vigente (completa) o la ejecutiva.
- **Densidad**: alta, de lectura, para la completa; baja, de exposición, para la ejecutiva.
- **Extensión**: la completa, una idea por sección o subsección (unas 15–25 diapositivas); la ejecutiva, 5–8.
- **Estilo**:
  - Con design.md: úsalo como receta de diseño, igual que una plantilla ya elegida, y salta la exploración de estilos. Pide una diapositiva de muestra antes del deck completo.
  - Sin design.md: la descripción del usuario, o la exploración de estilos de frontend-slides.
- **Reglas del benchmark**, con cualquier estilo:
  - La primera diapositiva de contenido es el mensaje principal.
  - Las posturas y las etiquetas de evidencia se conservan, con un color neutro y distinto por postura.
  - Las diferencias se presentan como opciones, y el deck compara posturas.
  - Las fuentes van en las notas o en una diapositiva final.

## 3. Guarda

Guarda según `../../../motor/guardado.md`, con la versión del informe de origen en la ficha o al inicio del archivo.

frontend-slides produce decks 16:9. Si el usuario quiere el informe completo como página web con scroll, invoca el skill **frontend-design** con el informe vigente, el mismo design.md o estilo, y las mismas reglas del benchmark. Si frontend-design no está en la lista de skills, ofrece instalarlo con `claude plugin install frontend-design@claude-plugins-official`.
