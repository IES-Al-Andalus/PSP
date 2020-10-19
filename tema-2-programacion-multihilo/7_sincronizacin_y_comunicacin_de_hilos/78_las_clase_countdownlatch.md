# 7.8. Las clase CountDownLatch

 La clase `CountDownLatch` del paquete `java.util.concurrent` es una utilidad de sincronización que permite que **uno o más** `threads` **esperen hasta que otros** `threads` **finalicen su trabajo**.

 El **funcionamiento esquemático** de `CountDownLatch` o "cuenta atrás de cierre" es el siguiente:

* Implementa un punto de espera que denominaremos "puerta de cierre", donde uno o más hilos esperan a que otros finalicen su trabajo.
* Los hilos que deben finalizar su trabajo se controlan mediante un contador que llamaremos "cuenta atrás".
* Cuando la "cuenta atrás" llega a cero se reanudará el trabajo del hilo o hilos interrumpidos y puestos en espera.
* No será posible volver a utilizar la "cuenta atrás", es decir, **no se puede reiniciar**. Si fuera necesario reiniciar la "cuenta atrás" habrá que pensar en utilizar la clase `CyclicBarrier`.

 Los **aspectos más importantes al usar la clase** `CountDownLatch` son los siguientes:

* Al constructor `countDownLatch(int cuenta)` se le indica, mediante el parámetro "cuenta", el total de hilos que deben completar su trabajo, que será el valor de la "cuenta atrás".
* El hilo en curso desde el que se invoca al método `await()` esperará en la "puerta de cierre" hasta que la "cuenta atrás" tome el valor cero. También se puede utilizar el método `await(long tiempoespera, TimeUnit unit)`, para indicar que la espera será hasta que la cuenta atrás llegue a cero o bien se sobrepase el tiempo de espera especificado mediante el parámetro `tiempoespera`.
* La "cuenta atrás" se irá decrementando mediante la invocación del método `countDown()`, y cuando ésta llega al valor cero se libera el hilo o hilos que estaban en espera, continuando su ejecución.
* No se puede reinicar o volver a utilizar la "cuenta atrás" una vez que ésta toma el valor cero. Si esto fuera necesario, entonces debemos pensar en utilizar la clase `CyclicBarrier`.
* El método `getCount()` obtiene el valor actual de la "cuenta atrás" y generalmente se utiliza durante las pruebas y depuración del programa.

 En el siguiente enlace puedes ver un ejemplo de cómo utilizar `CountDownLatch` para sumar todos los elementos de una matriz. Cada fila de la matriz es sumada por un hilo. Cuando todos los hilos han finalizado su trabajo, se ejecuta el procedimiento que realiza la suma global.

