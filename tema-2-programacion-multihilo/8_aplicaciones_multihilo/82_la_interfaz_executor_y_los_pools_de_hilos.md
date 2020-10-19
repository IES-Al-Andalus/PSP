# 8.2. La interfaz Executor y los pools de hilos

 Cuando trabajamos con **aplicaciones tipo servidor**, éstas tienen que atender un número masivo y concurrente de peticiones de usuario, en forma de tareas que deben ser procesadas lo antes posible. Al principio de la unidad ya te indicamos mediante un ejemplo la conveniencia de utilizar hilos en estas aplicaciones, pero si ejecutamos cada tarea en un hilo distinto, se pueden llegar a crear tantos hilos que el incremento de recursos utilizados puede comprometer la estabilidad del sistema. Los pools de hilos ofrecen una solución a este problema.

 Y ¿qué es un pool de hilos? Un **pool de hilos** `(thread pools`\) es básicamente un contenedor dentro del cual se crean y se inician un número limitado de hilos, para ejecutar todas las tareas de una lista.

 Para **declarar un pool**, lo más habitual es hacerlo **como un objeto del tipo** `ExecutorService` utilizando alguno de los siguientes **métodos de la clase estática** `Executors`:

* `newFixedThreadPool(int numeroHilos)`: crea un pool con el número de hilos indicado. Dichos hilos son reutilizados cíclicamente hasta terminar con las tareas de la cola o lista.
* `newCachedThreadPool()`: crea un pool que va creando hilos conforme se van necesitando, pero que puede reutilizar los ya concluidos para no tener que crear demasiados. Los hilos que llevan mucho tiempo inactivos son terminados automáticamente por el pool.
* `newSingleThreadExecutor()`: crea un pool de un solo hilo. La ventaja que ofrece este esquema es que si ocurre una excepción durante la ejecución de una tarea, no se detiene la ejecución de las siguientes.
* `newScheduledExecutor()` : crea un pool que va a ejecutar tareas programadas cada cierto tiempo, ya sea una sola vez o de manera repetitiva. Es parecido a un objeto Timer, pero con la diferencia de que puede tener varios threads que irán realizando las tareas programadas conforme se desocupen.

 Los objetos de tipo `ExecutorService` implementan la interfaz `Executor`. Esta interfaz define el método `execute(Runnable)`, al que hay que llamar una vez por cada tarea que deba ser ejecutada por el pool \(la tarea se pasa como argumento del método\).

 La interface `ExecutorService` proporciona una serie de métodos para el control de la ejecución de las tareas, entre ellos el método `shutdown()`, para indicarle al pool que los hilos no se van a reutilizar para nuevas tareas y deben morir cuando finalicen su trabajo.

 En el siguiente enlace dispones de un ejemplo en el que se define una clase que implementa `Runnable` cuya tarea es generar e imprimir 10 números aleatorios. Se creará un pool de 2 hilos capaz de realizar 30 de esas tareas.

