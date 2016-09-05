## Idea

La memoria principal es un circuito construido a base de celdas que permite almacenar información binaria mientras se tiene alimentación eléctrica. Es decir que **es volátil*.*

La información binaria que contiene son **instrucciones de programas** (codificadas según la especificación de algún lenguaje, como Q1) o bien son **datos**.

### Operaciones sobre la memoria

La memoria es un circuito que provee dos servicios: Lectura de una celda y escritura de un dato en una celda.

La **lectura** tiene los siguientes pasos:

1. La memoria recibe una señal de lectura
2. Recibe un número de celda
3. Entrega el contenido de la celda correspondiente
4. Activa una señal de control para indicar su finalización

La **escritura** tiene los siguientes pasos:

1. La memoria recibe una señal de escritura
2. Recibe  un número de celda
3. Recibe un dato a escribir
4. Actualiza el contenido de la celda correspondiente con el dato recibido
5. Activa una señal de control para indicar su finalización


### Las direcciones

Cada celda se identifica mediante una combinación de bits, denominada **dirección**. Esa cadena es traducida, dentro del circuito de la memoria a la selección de una única celda. 

¿Se te ocurre cómo es el circuito que hace ese trabajo de traducción?


Exacto! un **decodificador**.

![direccion-activacion.png](https://raw.githubusercontent.com/Orga-UNQ/mumuki-guia-qsim-memoria-buses-y-q-2/master/images/direccion-activacion.png "traduccion de la dirección a la elección de una celda")

Pero además de seleccionar una celda a partir de su dirección, debemos indicarle de que operación se trata (lectura o escritura).


### El circuito de una pequeña memoria

Veámos gráficamente un ejemplo de memoria con 4 celdas de 4 bits cada una:

![Circuito de una memoria de 4 celdas y 4 bits por celda](https://github.com/Orga-UNQ/mumuki-guia-qsim-memoria-buses-y-q-2/blob/master/images/memoria4x4.png?raw=true "memoria 4x4")

Descripción de las entradas:

* a0 y a1 construyen la dirección de la celda 
* L=1 cuando se quiere leer el contenido de la celda
* E=1 cuando se quiere escribir un nuevo contenido en la celda 

### Vista abstracta de la memoria

De ahora en mas, las memorias (o alguna parte de ellas) serán graficadas de manera abstracta como se ejemplifica en el siguiente gráfico, que corresponde a la misma memoria analizada arriba.

![Memoria abstracta](https://raw.githubusercontent.com/Orga-UNQ/mumuki-guia-qsim-memoria-buses-y-q-2/master/images/memoria-abstracta.png "memoria abstracta")


### Pequeño ejercicio

 Si la memoria tiene 8 celdas, cada una de 1 byte (contiene 8 bits): ¿Que tamaño deben tener las direcciones?