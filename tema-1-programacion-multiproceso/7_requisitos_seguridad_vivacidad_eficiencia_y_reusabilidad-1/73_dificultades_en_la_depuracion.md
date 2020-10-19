# 7.3. Dificultades en la depuración

 Cuando estamos programando aplicaciones que incluyen mecanismos de sincronización y acceden a recursos de forma concurrente junto con otras aplicaciones. A la hora de depurarlas, nos enfrentaremos a:

* **Los mismos problemas de depuración de una aplicación secuencial.**
* **Además de nuevos errores de temporización y sincronización propios de la programación concurrente.**

 Los **programas secuenciales** presentan una línea simple de control de flujo. Las operaciones de este tipo de programas están estrictamente ordenados como una secuencia temporal lineal.

* El comportamiento del programa es solo función de la naturaleza de las operaciones individuales que constituye el programa y del orden en que se ejecutan.
* En los programas secuenciales, el tiempo que tarda cada operación en ejecutarse no tiene consecuencias sobre el resultado.
* Para validar un programa secuencial se necesitaremos comprobar:
  * La correcta respuesta a cada sentencia.
  * El correcto orden de ejecución de las sentencias.

 Para validar un **programa concurrente** se requiere comprobar los mismos aspectos que en los programas secuenciales, además de los siguientes nuevos aspectos:

* Las sentencias se pueden **validar individualmente solo si no están involucradas en el uso de recursos compartidos.**
* Cuando existen recursos compartidos, los **efectos de interferencia entre las sentencias concurrentes pueden ser muy variados y la validación es muy difícil.** Comprobaremos la **corrección en la definición de las regiones críticas** y que **se cumple la exclusión mutua.**
* Al comprobar la correcta implementación del **sincronismo entre aplicaciones**; que es forzar **la ejecución secuencial de tareas de distintos procesos**, introduciendo sentencias explícitas de sincronización. Tendremos en cuenta que el **tiempo no influye sobre el resultado**.

 El problema es que las herramientas de depuración no nos proporcionan toda la funcionalidad que quisiéramos para poder depurar nuestros programas concurrentes.

 ¿Con qué herramientas contamos para depurar programas concurrentes?

* El **depurador** del `IDE` NetBeans. En la Unidad 2, veremos que el depurador de NetBeans, sí está preparado para la depuración concurrente de hilos dentro de un mismo proceso. En esta unidad estamos tratando procesos independientes.
* Hacer volcados de actividad en un **fichero de log** o en pantalla de salida \(nos permitirá hacernos una idea de lo que ha estado pasando durante las pruebas de depuración\).
* Herramientas de depuración específicas: `TotalView` \(`SW` comercial\), `StreamIt Debugger Tool` \(`plugin` para `eclipse`\), ...

 Una de las nuevas situaciones a las que nos enfrentamos es que a veces, los **errores** que parecen estar sucediendo, **pueden desaparecer cuando introducimos código para tratar de identificar** el problema.

 Nos damos cuenta de la complejidad que entraña depurar el comportamiento de aplicaciones concurrentes, es por ello, que al diseñarlas, tendremos en cuenta los **patrones de diseño**, que ya están **diseñados resolviendo errores comunes** de la concurrencia. Podemos verlos como 'recetas', que nos permiten **resolver los problemas 'tipo' que se presentan en determinadas condiciones de sincronismo y/o en los accesos concurrentes a un recurso.**

