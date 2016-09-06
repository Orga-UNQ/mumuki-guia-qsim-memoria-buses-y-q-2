### Líneas de control

Dado que los buses son *medios compartidos* a los que se conecta más de un dispositivo, la señal emitida por cualquiera de ellos está disponible para ser leída por cualquier otro. Si más de un dispositivo transmite al mismo tiempo pueden ocurrir colisiones, y entonces se necesita un mecanismo de control y sincronización para asegurar que solo uno transmita al mismo tiempo. 

Para resolver esto se utiliza el **bus de control**, que transmite señales de **temporización** y **comandos** hacia la memoria.

* La temporización indica la validez de las direcciones y datos en los demás buses. 
  * El bus está ocupado
  * Necesito usar el bus
  * Listo!
* Los comandos indican el tipo de operación que se debe llevar a cabo en la memoria (lectura o escritura)


### Lectura y escritura, revisadas

Ahora que entendemos un poco mas el detalle de la comunicación dentro de la computadora, revisemos las operaciones de lectura y escritura que definimos [acá]() con el siguiente ejemplo: 

* Se quiere leer el contenido de la celda ```011```
![Lectura con buses](https://raw.githubusercontent.com/Orga-UNQ/mumuki-guia-qsim-memoria-buses-y-q-2/master/images/lecturaconbuses.png)

* Se quiere escribir el valor 0000 en la celda ```011```
![Escritura con buses](https://raw.githubusercontent.com/Orga-UNQ/mumuki-guia-qsim-memoria-buses-y-q-2/master/images/escrituraconbuses.png)
