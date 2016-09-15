## Ejecución de los programas

Este [apunte](http://orga.blog.unq.edu.ar/wp-content/uploads/sites/5/2015/04/orga_apunte_registros_PC-IR.pdf) es una buena forma de repasar los temas de esta lección.

Nunca está de más recordar el objetivo de nuestras computadoras, que es el de **ejecutar programas**. Dichos programas son una **secuencia de instrucciones** y por lo tanto cada instrucción debe ejecutarse en orden, recibiendo el mismo tratamiento, que hemos definido como se grafica en la siguiente imagen:

<img width="100px" src="https://raw.githubusercontent.com/Orga-UNQ/mumuki-guia-qsim-memoria-buses-y-q-2/master/images/ciclo-simple.png"/>

1. **Busqueda de instrucción**: Lectura de la memoria principal para recuperar el **codigo máquina** de una instrucción 
2. **Decodificación de instrucción**: Interpretación de los modos de direccionamiento
3. **Ejecución de instrucción**: Traducción del **código de operación** en las acciones correspondientes.

### Ciclo de ejecución revisado

Este ciclo puede detallarse más teniendo en cuenta que la memoria **también puede almacenar operandos**, así que en función de los modos de direccionamiento (luego de la decodificación) se se puede determinar si el operando está en memoria (modo de direccionamiento directo).

Asimismo, en función de cómo es el modo del operando destino, puede ser necesario acceder a memoria para **escribir el resultado**. Revisemos entonces el ciclo de ejecución de instruccción


![Ciclo con busqueda y almacenamiento de operandos](https://raw.githubusercontent.com/Orga-UNQ/mumuki-guia-qsim-memoria-buses-y-q-2/master/images/ciclo-completo-con-accesos.png "Ciclo con busqueda y almacenamiento de operandos")


#### Accesos a memoria

Ahora es posible deducir cuántas veces y en qué momentos se necesitan accesos a memoria (ya sean lecturas o escrituras). Por ejemplo, la ejecución de ``` ADD R0,R1``` requiere acceder a memoria sólo en la búsqueda de instrucción, porque los operandos están en la CPU (son registros).

¿Se te ocurre un ejemplo donde la ejecución requiera acceder a memoria en **otra etapa del cilo**?

Por ejemplo, veamos un ejemplo de cuando los operandos son de modo **directo**. Supongamos que la instrucción ```ADD R1, [0x3030]``` está ensamblada a partir de la celda **0xBBBB**
En este ejemplo, se tienen los siguientes accesos:

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#aaa;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#aaa;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#aaa;color:#fff;background-color:#f38630;}
.tg .tg-j2zy{background-color:#FCFBE3;vertical-align:top}
.tg .tg-rmb8{background-color:#C2FFD6;vertical-align:top}
.tg .tg-yw4l{vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-yw4l">Etapa del ciclo <br></th>
    <th class="tg-yw4l">¿Lectura/Escritura?</th>
    <th class="tg-yw4l">Dirección</th>
  </tr>
  <tr>
    <td class="tg-yw4l">Búsqueda de instrucción</td>
    <td class="tg-yw4l">Lectura</td>
    <td class="tg-yw4l">BBBB</td>
  </tr>
  <tr>
    <td class="tg-yw4l">Búsqueda de instrucción</td>
    <td class="tg-yw4l">Lectura</td>
    <td class="tg-yw4l">BBBC</td>
  </tr>
  <tr>
    <td class="tg-yw4l">Búsqueda de Operandos</td>
    <td class="tg-yw4l">Lectura </td>
    <td class="tg-yw4l">3030 </td>
  </tr>
</table>

Veamos ahora otro ejemplo: ```ADD [0x3030],R1``` ¿Que diferencia encontramos? El operando destino está en memoria! En que cambian los accesos?

<table class="tg">
  <tr>
    <th class="tg-yw4l">Etapa del ciclo <br></th>
    <th class="tg-yw4l">¿Lectura/Escritura?</th>
    <th class="tg-yw4l">Dirección</th>
  </tr>
  <tr>
    <td class="tg-yw4l">Búsqueda de instrucción</td>
    <td class="tg-yw4l">Lectura</td>
    <td class="tg-yw4l">BBBB</td>
  </tr>
  <tr>
    <td class="tg-yw4l">Búsqueda de instrucción</td>
    <td class="tg-yw4l">Lectura</td>
    <td class="tg-yw4l">BBBC</td>
  </tr>
  <tr>
    <td class="tg-yw4l">Búsqueda de Operandos</td>
    <td class="tg-yw4l">Lectura </td>
    <td class="tg-yw4l">3030 </td>
  </tr> <tr>
    <td class="tg-rmb8">Almacenamiento de Operandos</td>
    <td class="tg-rmb8">Escritura </td>
    <td class="tg-rmb8">3030 </td>
  </tr>
</table>



#### A practicar

Suponga que la instrucción ```MOV [0x3456], 0x5555``` está ensamblada a partir de la celda 6789.
¿Que celda se accede en la etapa de **Almacenamiento de operandos**?
