# 3.2. Utilidades de concurrencia del paquete java.util.concurrent

 El paquete `java.util.concurrent` incluye una serie de clases que facilitan enormemente el desarrollo de aplicaciones multihilo y aplicaciones complejas, ya que están concebidas para utilizarse como bloques de diseño.

 Concretamente estas utilidades están dentro de los siguientes **paquetes**:

* `java.util.concurrent`. En este paquete están definidos los siguientes elementos:
  * **Clases de sincronización**. `Semaphore`, `CountDownLatch`, `CyclicBarrier` y `Exchanger`.
  * **Interfaces para separar la lógica de la ejecución**, como por ejemplo `Executor`, `ExecutorService`, `Callable` y `Future`.
  * **Interfaces para gestionar colas de hilos**. `BlockingQueque`, `LinkedBlokingQueque`, `ArrayBlockingQueque`, `SynchronousQueque`, `PriorityBlockingQueque` y `DelayQueque`.
* `java.util.concurrent.atomic`. Incluye un conjunto de clases para ser usadas como variables atómicas en aplicaciones multihilo y con diferentes tipos de dato, por ejemplo `AtomicInteger` y `AtomicLong`.
* `java.util.concurrent.locks`. Define una serie de clases como uso alternativo a la cláusula `sinchronized`. En este paquete se encuentran algunas interfaces como por ejemplo `Lock`, `ReadWriteLock`.

 A lo largo de esta unidad estudiaremos las clases e interfaces más importantes de este paquete.

> "Vale más saber alguna cosa de todo, que saberlo todo de una sola cosa". Blaise Pascal

