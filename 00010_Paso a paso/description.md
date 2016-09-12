## Ejecución de los programas
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
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;border-top-width:1px;border-bottom-width:1px;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:0px;overflow:hidden;word-break:normal;border-top-width:1px;border-bottom-width:1px;}
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
    <td class="tg-yw4l"> </td>
    <td class="tg-yw4l">3030 </td>
  </tr>
</table>



