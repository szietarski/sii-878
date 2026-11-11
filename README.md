# Práctica 1 Entorno de desarrollo Linux

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

## Práctica 3: Comunicación mediante archivo proyectado en memoria

En esta práctica se ha implementado la comunicación entre el juego de tenis y un proceso bot mediante un fichero proyectado en memoria.

- Se ha creado la estructura DatosMemCompartida para compartir la pelota, la raqueta1 y la acción a realizar
- El programa tenis crea el fichero compartido utilizando open y ftruncate y lo proyecta en memoria mediante mmap
- El programa bot abre el mismo fichero y accede a los datos mediante mmap
- Tenis actualiza la posición de la pelota y de la raqueta1
- El bot decide automáticamente la acción de la raqueta1 según la posición de la pelota
- La acción puede ser: 1 arriba, 0 nada o -1 abajo
- Se ha añadido el programa bot al CMakeLists.txt
- Al ejecutar la práctica funcionan simultáneamente los procesos tenis, logger y bot
