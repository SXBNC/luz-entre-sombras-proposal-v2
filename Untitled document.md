## ***Boundary Test Data***

## **— Logic Points**

| Movimiento del jugador (Luna) Porque puede intentar moverse fuera del laberinto, chocar con paredes o usar inputs inválidos.  |
| :---- |
| **Inventario de objetos clave (Juguete, Pulsera Médica, recuerdos)** Porque hay límites y tipos de objetos que pueden romper la lógica narrativa. |
| **Sistema de vidas y finales (vidas, objetos recolectados, rutas ocultas)** Porque define si el jugador llega al final principal, alternativo o se queda en “Game Over”. |

## 

## **— Boundary Cases**

| Logic Point A: Movimiento del jugador |
| :---- |

| Boundary Input | Why It’s a Boundary |
| ----- | ----- |
| Movimiento fuera del laberinto | El jugador intenta salir del grid permitido |
| Movimiento contra un obstáculo | El jugador intenta atravesar una pared/sombra |
| Input inválido | Se presiona una tecla no asignada |

| Logic Point B: Inventario de objetos clave |
| :---- |

| Boundary Input | Why It’s a Boundary |
| ----- | ----- |
| Inventario vacío | No hay objetos para usar |
| Inventario lleno | Se intenta recolectar más de lo permitido |
| Objeto inválido | Se intenta guardar algo que no es coleccionable |

| Logic Point C: Sistema de vidas y finales |
| :---- |

| Boundary Input | Why It’s a Boundary |
| ----- | ----- |
| Vidas \< 0 | El jugador recibe más daño del que tiene |
| Vidas \= 0 | El jugador muere exactamente |
| Todos los objetos recolectados | Se activa el final alternativo |

## 

## **— Test Data Examples**

| Logic Point A: Movimiento |
| :---- |

| Boundary Input | Test Data Example |
| ----- | ----- |
| Movimiento fuera del laberinto | Luna intenta moverse a posición (-1, 4\) |
| Movimiento contra obstáculo | Luna intenta entrar en celda con muro en (3,3) |
| Input inválido | Jugador presiona tecla “Z” (no asignada) |

| Logic Point B: Inventario |
| :---- |

| Boundary Input | Test Data Example |
| ----- | ----- |
| Inventario vacío | Jugador intenta usar slot 0 sin objetos |
| Inventario lleno | Jugador intenta recolectar 6 objetos cuando el límite es 5 |
| Objeto inválido | Jugador intenta guardar “Sombra” en inventario |

| Logic Point C: Vidas y finales |
| :---- |

| Boundary Input | Test Data Example |
| ----- | ----- |
| Vidas \< 0 | Luna recibe daño y su HP \= \-1 |
| Vidas \= 0 | Luna pierde su última vida |
| Todos los objetos recolectados | Jugador obtiene Juguete \+ Pulsera Médica \+ Recuerdo final |

## 

## **— Expected Outcomes**

| Logic Point A: Movimiento |
| :---- |

| Boundary Input | Test Data | Expected Outcome |
| ----- | ----- | ----- |
| Fuera del laberinto | (-1,4) | Juego bloquea movimiento, Luna se queda en límites |
| Contra obstáculo | (3,3) | Movimiento cancelado, no atraviesa muro |
| Input inválido | “Z” | Input ignorado, no crash |

| Logic Point B: Inventario  |
| :---- |

| Boundary Input | Test Data | Expected Outcome |
| :---- | :---- | :---- |
| Vacío         | Slot 0             | Mensaje “No hay objeto” |
| Lleno          | 6 objetos        | Juego rechaza nuevo objeto, muestra “Inventario lleno” |
| Inválido      | “Sombra”         | Juego no guarda, evita corrupción |

### 

| Logic Point C: Vidas y finales |
| :---- |

| Boundary Input | Test Data | Expected Outcome |
| :---- | :---- | :---- |
| Vidas \< 0     | HP \= \-1    | Juego ajusta HP a 0, activa “Game Over” |
| Vidas \= 0 | HP \= 0 | Juego muestra animación de muerte y pantalla de “Game Over” |
| Todos objetos | Juguete \+ Pulsera \+ Recuerdo | Juego activa final alternativo |

### 

| Reflexión Logic Point más frágil: Sistema de vidas y finales (porque afecta directamente la narrativa y puede romper el flujo). Qué vigilar al programar: Evitar valores negativos y controlar límites de inventario. Caso más sorprendente: Que un objeto inválido pueda entrar al inventario y corromper la progresión.  |
| :---- |

