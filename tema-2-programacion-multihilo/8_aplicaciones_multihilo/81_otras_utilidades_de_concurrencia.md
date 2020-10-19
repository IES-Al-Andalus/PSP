# 8.1. Otras utilidades de concurrencia

 Además de las utilidades de sincronización que hemos visto en apartados anteriores, el paquete `java.util.concurrent` incluye estas otras **utilidades de concurrencia**:

* La interfaz `Executor`
* Colecciones.
* La clase `Locks`
* Variables atómicas

 El **programador de tareas** `Executor` es una interfaz que permite:

* Realizar la ejecución de tareas en un único hilo en segundo plano \(como eventos Swing\), en un hilo nuevo, o en un pool de hilos
* Diseñar políticas propias de ejecución y añadirlas a `Executor`.
* Ejecutar tareas mediante el método `execute()`. Estas tareas tienen que implementar la interfaz Runnable.
* Hacer uso de diferentes implementaciones de `Executor`, como `ExecutorService`.

 Entre las **colecciones** hay que destacar:

* La interfaz `Queque`. Es una colección diseñada para almacenar elementos antes de procesarlos, ofreciendo diferentes operaciones como inserción, extracción e inspección.
* La interfaz `BlockingQueque`, diseñada para colas de tipo productor/consumidor, y que son thread-safe \(aseguran un funcionamiento correcto de los accesos simultáneos multihilo a recursos compartidos\). Son capaces de esperar mientras no haya elementos almacenados en la cola.
* Implementaciones concurrentes de `Map` y `List`.

 La clase de **bloqueos**, `java.util.concurrent.locks`, proporciona diferentes implementaciones y diversos tipos de bloqueos y desbloqueos entre métodos. Su funcionalidad es equivalente a `Synchronized`, pero proporciona métodos que hacen más fácil el uso de bloqueos y condiciones. Entre ellos.

* El métdo `newCondition()`, que permite tener un mayor control sobre el bloqueo y genera un objeto del tipo `Condition` asociado al bloqueo. Así el método `await()` indica cuándo deseamos esperar, y el método `signal()` permite indicar si una condición del bloqueo se activa, para finalizar la espera.
* La implementación `ReentranLock`, permite realizar exclusión mutua utilizando monitores. El método lock\(\) indica que deseamos utilizar el recurso compartido, y el método `unlock()` indica que hemos terminado de utilizarlo.

 Las **variables atómicas** incluidas en las utilidades de concurrencia clase `java.util.concurrent.atomic`, permiten definir recursos compartidos, sin la necesidad de proteger dichos recursos de forma explícita, ya que ellas internamente realizan dichas labores de protección.

 Si desarrollamos aplicaciones multihilo más complejas, por ejemplo para plataformas multiprocesador y sistemas con multi-núcleo \(multi-core\) que requieren un alto nivel de concurrencia, será muy conveniente hacer uso de todas estas utilidades.

