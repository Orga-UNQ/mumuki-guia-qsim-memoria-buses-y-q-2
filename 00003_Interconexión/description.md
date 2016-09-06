## Conectarse para sobrevivir

La memoria principal y la unidad de control son circuitos que deben comunicarse para intercambiar datos y direcciones.

> ¿Cómo se comunican? 

A través de un medio de transmisión compartido entre la CPU y la Memoria Principal que se denomina **Bus del sistema**. El bus de sistema es un conjunto de señales que permite:

* transmitir datos desde y hacia la memoria
* transmitir direcciones hacia la memoria
* transmitir señales de control desde y hacia la memoria principal 

El bus de sistema está formado por tres buses para cumplir los diferentes objetivos y reciben los nombres:
* Bus de direcciones 
* Bus de datos
* Bus de control

![VN con bus del sistema](https://raw.githubusercontent.com/Orga-UNQ/mumuki-guia-qsim-memoria-buses-y-q-2/master/images/vn-con-buses.png "Von Neumann")

Cada bus tiene una determinada cantidad de líneas (*ancho del bus*) y cada línea transmite un bit a la vez. Entonces el ancho del bus determina cuántos bits se pueden transmitir en paralelo (o sea, al mismo tiempo). En el caso del bus de direcciones, el ancho determina el **espacio direccionable**, y en el caso del bus de datos determina el **tamaño de palabra**.

En el siguiente ejemplo se tienen 8 celdas, por lo que el bus de direcciones debe ser de 3 bits de ancho. Las celdas contienen todas 8 bits, por lo que el bus de datos debe ser de 8 bits de ancho.

![Memoria 8x8](https://raw.githubusercontent.com/Orga-UNQ/mumuki-guia-qsim-memoria-buses-y-q-2/master/images/memoria8x8.png "memoria 8x8")

### Para pensar

Suponer que se tiene un bus de direcciones de 4 bits y un bus de datos de 8 bits 
¿Que tamaño máximo tiene, **en bytes**?
