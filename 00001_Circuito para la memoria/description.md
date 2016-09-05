## Idea

La memoria principal es un circuito construido a base de celdas que permite almacenar información binaria mientras se tiene alimentación eléctrica. Es decir que **es volátil*.*

La información binaria que contiene son **instrucciones de programas** (codificadas según la especificación de algún lenguaje, como Q1) o bien son **datos**.

### Las direcciones
Cada celda se identifica mediante una combinación de bits, denominada **dirección**. Esa cadena es traducida, dentro del circuito de la memoria a la selección de una única celda. 

¿Se te ocurre cómo es el circuito que hace ese trabajo de traducción?


Exacto! un **decodificador**.

![direccion-activacion.png](https://raw.githubusercontent.com/Orga-UNQ/mumuki-guia-qsim-memoria-buses-y-q-2/master/images/direccion-activacion.png "traduccion de la dirección a la elección de una celda")
### El circuito de una pequeña memoria

Veámos gráficamente un ejemplo de memoria con 4 celdas de 4 bits cada una:

![Circuito de una memoria de 4 celdas y 4 bits por celda](https://github.com/Orga-UNQ/mumuki-guia-qsim-memoria-buses-y-q-2/blob/master/images/memoria4x4.png?raw=true "memoria 4x4")

Descripción de las entradas:

* a0 y a1 construyen la dirección de la celda 
* L=1 cuando se quiere leer el contenido de la celda
* E=1 cuando se quiere escribir un nuevo contenido en la celda 
