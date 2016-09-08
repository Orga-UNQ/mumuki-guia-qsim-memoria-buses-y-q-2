Suponga el siguiente estado inicial de los registros:

| R0 | 000F | 00AB | R5 |
|----|------|------|----|
| R1 | 0013 | 000A | R6 | 
| R2 | 0085 | 0009 | R7 |
| R3 | 00E2 | 2001 | R8 |

Y suponga que en la memoria:

* la celda ```2000``` tiene el valor **2001**
* la celda ```2001``` tiene el valor **FF00**
* la celda ```200B``` tiene el valor **0050**
 
> ¿Cuál es el efecto de ejecutar la instrucción ```ADD R0,[0x2000]```?