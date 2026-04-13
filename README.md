# Armador de Equipos

App web en HTML que permite guardar jugadores, seleccionar a quienes juegan un partido y armar equipos lo mas parejos posible segun calidad, posicion y arqueros.

## Como usar

1. Abrir `index.html` en el navegador.
2. Elegir el tipo de futbol (5, 7, 9, 11).
3. Cargar jugadores con nombre, calidad y posicion opcional.
4. Agregar jugadores guardados a la seleccion del partido.
5. Crear equipos y copiar el resultado.

## Pasos y funciones

### Paso 1. Tipo de futbol
- Selecciona el formato (5, 7, 9 o 11).
- La app calcula automaticamente la cantidad de equipos con los jugadores seleccionados.

### Paso 2. Sumar jugadores (guardados)
- Nombre obligatorio.
- Modo de calidad:
  - Basico: un valor general entre 1 y 10 (acepta decimales).
  - Avanzado: promedio de Defensa, Pase y Ataque (acepta decimales).
- Opcion de marcar arquero (no usa medidores de calidad).
- Posicion opcional (Defensa, Mediocampo, Ataque).
- Los jugadores se guardan en `localStorage` para reutilizarlos en otros partidos.

### Jugadores seleccionados
- Desde la lista de jugadores guardados, presiona "Agregar" para incluirlos en el partido actual.
- Los equipos se generan solo con los jugadores seleccionados.
- El boton "Crear nuevos equipos" limpia la seleccion sin borrar los jugadores guardados.

### Paso 3. Crear equipos
- Boton "Crear equipos" arma equipos lo mas parejos posibles.
- Reglas principales:
  - Intenta mantener la misma cantidad de jugadores por equipo.
  - Balancea por calidad (promedio por equipo).
  - Si hay posicion, distribuye para que sea lo mas justo posible.
  - Arqueros se reparten uno por equipo si hay suficientes.

### Paso 4. Copiar
- Boton "Copiar" genera un texto listo para pegar con el formato:

```
EQUIPO 1:
- Jugador A
- Jugador B

EQUIPO 2:
- Jugador C
- Jugador D
```

## Datos guardados
- Los jugadores guardados viven en `localStorage`.
- El listado permanece al recargar la pagina.

## Archivos
- `index.html`: app completa (HTML + CSS + JS).

## Notas
- Si hay un solo arquero, solo un equipo tendra arquero y el resto no.
- Si hay menos arqueros que equipos, se informa con un mensaje.

