S# Práctica 1 Entorno de desarrollo Linux

## Descripción

Este proyecto corresponde a la Práctica 1 de la asignatura Sistemas Informáticos Industriales.
El proyecto es un juego de tenis para dos jugadores desarrollado en C++ utilizando OpenGL y GLUT.

## Modificaciones realizadas

El programa inicial mostraba los objetos del juego, pero estos no se movían.
Se ha añadido el movimiento de las raquetas en el método 'Raqueta::Mueve(float t)'. La posición vertical de cada raqueta se actualiza utilizando su velocidad.
También se ha añadido el movimiento de la esfera en el método 'Esfera::Mueve(float t)'. La posición de la esfera se actualiza en los ejes X e Y utilizando su velocidad.
Estas modificaciones permiten que el juego deje de ser estático y que los objetos se muevan durante la ejecución.
Controles: 
Jugador 1	W / S
Jugador 2	O / L
## Práctica 2: Comunicación mediante tuberías FIFO

En esta práctica se ha implementado la comunicación entre el juego de tenis y un proceso logger mediante una tubería FIFO

- Se ha creado el programa logger
- Logger crea y abre la FIFO /tmp/fifo para lectura
- CMundo abre la FIFO para escritura
- Cuando un jugador consigue un punto, tenis envía un mensaje al logger
- Logger muestra por pantalla los puntos de cada jugador
- Cuando un jugador alcanza 3 puntos, tenis termina y logger también finaliza
- Se ha modificado CMakeLists.txt para compilar logger
