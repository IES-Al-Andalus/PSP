# 3.2. Estados de un Proceso

 Si el sistema tiene que repartir el uso del microprocesador entre los distintos procesos, ¿qué le sucede a un proceso cuando no se está ejecutando? Y, si un proceso está esperando datos, ¿por qué el equipo hace otras cosas mientras que un proceso queda a la espera de datos?

 Veamos con detenimiento, cómo es que el SO controla la ejecución de los procesos. Ya comentamos en el apartado anterior, que el SO es el encargado de la gestión de procesos. En el siguiente gráfico, podemos ver un esquema muy simple de cómo podemos planificar la ejecución de varios procesos en una CPU.

 En este esquema, podemos ver:

1. Los procesos nuevos, entran en la cola de procesos activos en el sistema.
2. Los procesos van avanzando posiciones en la cola de procesos activos, hasta que les toca el turno para que el SO les conceda el uso de la CPU.
3. El SO concede el uso de la CPU, a cada proceso durante un tiempo determinado y equitativo, que llamaremos quantum. Un proceso que consume su quantum, es pausado y enviado al final de la cola.
4. Si un proceso finaliza, sale del sistema de gestión de procesos.

 Esta planificación que hemos descrito, resulta equitativa para todos los procesos \(todos van a ir teniendo su quamtum de ejecución\). Pero se nos olvidan algunas situaciones y características de nuestros los procesos:

* Cuando un proceso, necesita datos de un archivo o una entrada de datos que deba suministrar el usuario; o, tiene que imprimir o grabar datos; cosa que llamamos 'el proceso está en una **operación de entrada/salida'** \(E/S para abreviar\). El proceso, queda **bloqueado hasta que haya finalizado** esa E/S. El proceso es bloqueado, porque, los dispositivos son mucho más lentos que la CPU, por lo que, mientras que uno de ellos está esperando una E/S, **otros procesos pueden** pasar a la CPU y **ejecutar sus instrucciones**. Cuando termina la E/S que tenga un proceso bloqueado, el SO, volverá a pasar al proceso a la cola de procesos activos, para que recoja los datos y continúe con su tarea \(dentro de sus correspondientes turnos\).
* Sólo mencionar \(o recordar\), que cuando la memoria RAM del equipo está llena, algunos procesos deben pasar a disco \(o [almacenamiento secundario](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Almacenamiento%20secundario%20%28DAM_PSP01%29)\) para dejar espacio en RAM que permita la ejecución de otros procesos.
* Hay procesos en el equipo cuya ejecución es crítica para el sistema, por lo que, no siempre pueden estar esperando a que les llegue su turno de ejecución, haciendo cola. Por ejemplo, el propio SO es un programa, y por lo tanto un proceso o un conjunto de procesos en ejecución. Se le da prioridad, evidentemente, a los procesos del SO, frente a los procesos de usuario.

 Con todo lo anterior, podemos quedarnos con los siguientes **estados en el ciclo de vida de un proceso**:

1. **Nuevo.** Proceso nuevo, creado.
2. **Listo.** Proceso que está esperando la CPU para ejecutar sus instrucciones.
3. **En ejecución.** Proceso que actualmente, está en turno de ejecución en la CPU.
4. **Bloqueado.** Proceso que está a la espera de que finalice una E/S.
5. **Suspendido.** Proceso que se ha llevado a la [memoria virtual](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Memoria%20virtual%20%28DAM_PSP01%29) para liberar, un poco, la RAM del sistema.
6. **Terminado.** Proceso que ha finalizado y ya no necesitará más la CPU.

 El siguiente gráfico, nos muestra las distintas transiciones que se producen entre uno u otro estado:  


