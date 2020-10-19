# 7.9. La clase CyclicBarrier

 La clase `CyclicBarrier` del paquete `java.util.concurrent` es una utilidad de sincronización que permite que uno o más `threads` se esperen hasta que todos ellos finalicen su trabajo.

 El **funcionamiento esquemático** de `CyclicBarrier` o "barrera cíclica" es el siguiente:

* Implementa un punto de espera que llamaremos "barrera", donde cierto número de hilos esperan a que todos ellos finalicen su trabajo.
* Finalizado el trabajo de estos hilos, se dispara la ejecución de una determinada acción o bien el hilo interrumpido continúa su trabajo.
* La barrera se llama cíclica, porque se puede **volver a utilizar** después de que los hilos en espera han sido liberados tras finalizar todos su trabajo, y también **se puede reiniciar**.

 Los **aspectos más importantes al usar la clase** `CyclicBarrier` son los siguientes:

* Indicar al constructor `CyclicBarrier(int hilosAcceden)` el total de hilos que van a usar la barrera mediante el parámetro `hilosAcceden`. Este número sirve para disparar la barrera.
* La barrera se dispara cuando llega el último hilo.
* Cuando se dispara la barrera, dependiendo del constructor, `CyclicBarrier(int hilosAcceden`\) o `CyclicBarrier(int hilosAcceden, Runnable acciónBarrera)` se lanzará o no una acción, y entonces se liberan los hilos de la barrera. Esa acción puede ser realizada mediante cualquier objeto que implemente `Runnable`.
* El método principal de esta clase es `await()` que se utiliza para indicar que el hilo en curso ha concluido su trabajo y queda a la espera de que lo hagan los demás.

 **Otros métodos** de esta clase que puedes utilizar son:

* El método `await(long tiempoespera, TimeUnit unit)` funciona como el anterior, pero en este caso el hilo espera en la barrera hasta que los demás finalicen su trabajo o se supere el `tiempoespera`.
* El método `reset()` permite reiniciar la barrera a su estado inicial.
* El método `getNumber Waiting()` devuelve el número de hilos que están en espera en la barrera.
* El método `getParties()` devuelve el número de hilos requeridos para esa barrera

 En el siguiente enlace puedes ver un ejemplo parecido al anterior, pero ahora resuelto con `CyclicBarrier`. Cada fila de la matriz ahora representa los valores recaudados por un cobrador. Cada fila es sumada por un hilo. Cuando 5 de estos hilos finalizan su trabajo, se dispara un objeto que implementa `Runnable` para obtener la suma recaudada hasta el momento. Como la matriz del ejemplo tiene 10 filas, la suma de sus elementos se hará mediante una barrera de 5 hilos y que se utilizará por tanto de forma cíclica dos veces.

