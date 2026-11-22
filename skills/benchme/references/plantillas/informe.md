# Plantilla del informe madre

Títulos en lenguaje de negocio; los nombres de los marcos van dentro del texto. Cada afirmación cita su evidencia `[E#]`.

```markdown
---
tipo: benchmark        # con brainme: tipo: entregable
tema: <tema>
version: N
fecha: AAAA-MM-DD
modo: ligero | completo
profundidad: ligera | sistémica | transición
---
# Benchmark: <tema>

## 1. Mensaje principal
Una afirmación, no un tema; se escribe al final. Decisión que informa: …

## 2. Brief
Resumen del brief y las hipótesis iniciales del equipo, textuales.

## 3. Con quién nos comparamos y por qué
Tabla: alternativa · rol · motivo. Exclusiones y fantasmas, con su motivo.

## 4. Criterios
Ligados a lo que el cliente intenta lograr y a cómo decide. Pesos explícitos, y si el orden cambia con otros pesos razonables.

## 5. Qué hace cada alternativa
Un resumen por perfil: dónde juega y cómo gana, qué está viendo, sus elecciones, su durabilidad y sus supuestos (o "abierto").

## 6. Mapa de posicionamiento
Lienzo o curvas de valor con ejes justificados, si se usó la lente.

## 7. Qué igualar, en qué diferenciarnos, qué vigilar y qué ignorar
Tabla: ítem · postura · razón · ¿difícil de copiar? · evidencia.

## 8. Explicaciones alternativas y supuestos clave
Explicaciones rivales y qué evidencia las distingue; hipótesis del equipo frente a la evidencia; steelman de la opción descartada.

## 9. Implicaciones
Paradoja central (si el usuario la incluyó). Opciones, cada una con qué tendría que ser cierto, su barrera y la prueba que la resolvería.

## 10. Qué vigilar
Suposiciones, indicadores, tripwires y su acción, señales, cuándo hablar con personas, cadencia.

## 11. Lo que no sabemos
Vacíos, evidencia baja o caducada, tareas de primera mano pendientes, límites éticos.

## 12. Anexo
Método. Registro de evidencia (o su enlace). Registro de cambios: qué cambió desde la versión anterior y por qué.
```

**Modo ligero:** secciones 1, 3, 5 (breve), 7 y 11, con su número. El contraste de las hipótesis del usuario y el steelman van breves en la 7, y el registro de cambios al final de la 11.

## Control de calidad

- [ ] El mensaje principal es una afirmación.
- [ ] Cada ítem de la sección 7 tiene postura y evidencia.
- [ ] El informe compara posturas: sin ganador, sin puntaje total, sin brechas en rojo.
- [ ] Las hipótesis del usuario aparecen y se contrastan.
- [ ] El steelman está escrito.
- [ ] Toda evidencia citada existe en el registro, con fecha.
- [ ] La sección 11 dice lo que no se sabe.
- [ ] Desde la segunda versión, hay registro de cambios.
