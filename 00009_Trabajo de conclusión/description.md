Supongamos el siguiente *mapa* de una parte de la memoria:

![Conclusión](https://raw.githubusercontent.com/Orga-UNQ/mumuki-guia-qsim-memoria-buses-y-q-2/master/images/memoria-conclusion.png 'Mapa de memoria')

y además supongamos que:

* R5 = 0x0001
* PC = 0x9999

Completar el siguiente cuadro que describe el contenido de los buses en cada operación de lectura o escritura a Memoria Principal al ejecutar el programa anterior (La primer línea se pone como ejemplo)

Nota: en el bus de control se debe indicar L=1 cuando es una lectura o E=1 cuando es una escritura. 




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
    <th class="tg-yw4l">Bus de control</th>
    <th class="tg-yw4l">Bus de direcciones</th>
    <th class="tg-yw4l">Bus de datos</th>
  </tr>
  <tr>
    <td class="tg-yw4l">Búsqueda de instrucción</td>
    <td class="tg-yw4l">Lectura</td>
    <td class="tg-yw4l">L=1</td>
    <td class="tg-yw4l">9999</td>
    <td class="tg-yw4l">SUB [?], R5</td>
  </tr>
  <tr>
    <td class="tg-yw4l"></td>
    <td class="tg-yw4l"></td>
    <td class="tg-yw4l"></td>
    <td class="tg-yw4l"></td>
    <td class="tg-yw4l"></td>
  </tr>
  <tr>
    <td class="tg-yw4l"></td>
    <td class="tg-yw4l"></td>
    <td class="tg-yw4l"></td>
    <td class="tg-yw4l"></td>
    <td class="tg-yw4l"></td>
  </tr>
</table>


















































