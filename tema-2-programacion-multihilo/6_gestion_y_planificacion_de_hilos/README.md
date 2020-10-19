# 6. Gestión y planificación de hilos

 La ejecución de hilos se puede realizar mediante:

* **Paralelismo**. En un sistema con múltiples CPU, cada CPU puede ejecutar un hilo diferente.
* **Pseudoparalelismo**. Si no es posible el paralelismo, una CPU es responsable de ejecutar múltiples hilos.

 La ejecución de múltiples hilos en una sola CPU requiere la planificación de una secuencia de ejecución \(sheduling\).

 El **planificador de hilos de Java** \(Sheduler\) utiliza un algoritmo de secuenciación de hilos denominado fixed priority scheduling que está basado en un sistema de prioridades relativas, de manera que el algoritmo secuencia la ejecución de hilos en base a la prioridad de cada uno de ellos.

 El **funcionamiento** del algoritmo es el siguiente:

* El hilo elegido para ejecutarse, siempre es el hilo "Ejecutable" de prioridad más alta.
* Si hay más de un hilo con la misma prioridad, el orden de ejecución se maneja mediante un algoritmo por turnos \(round-rubin\) basado en una cola circular FIFO \(Primero en entrar, primero en salir\).
* Cuando el hilo que está "ejecutándose" pasa al estado de "No Ejecutable" o "Muerto", se selecciona otro hilo para su ejecución.
* La ejecución de un hilo se interrumpe, si otro hilo con prioridad más alta se vuelve "Ejecutable". El hecho de que un hilo con una prioridad más alta interrumpa a otro se denomina "**planificación apropiativa**" \('preemptive sheudling'\).

 Pero la responsabilidad de ejecución de los hilos es del Sistemas Operativos sobre el que corre la JVM, y **Sistemas Operativos distintos manejan los hilos de manera diferente**:

* En un **Sistema Operativo que implementa** time-slicing \(subdivisión de tiempo\), el hilo que entra en ejecución, se mantiene en ella sólo un micro-intervalo de tiempo fijo o cuanto \(quantum\) de procesamiento, de manera que el hilo que está "ejecutándose" no solo es interrumpido si otro hilo con prioridad más alta se vuelve "Ejecutable", sino también cuando su "cuanto" de ejecución se acaba. Es el patrón seguido por Linux, y por todos los Windows a partir de Windows 95 y NT.
* En un **Sistema Operativo que no implementa** time-slicing el hilo que entra en ejecución, es ejecutado hasta su muerte; salvo que regrese a "No ejecutable", u otro hilo de prioridad más alta alcance el estado de "Ejecutable" \(en cuyo caso, el primero regresa a "preparado" para que se ejecute el segundo\). Es el patrón seguido en el Sistema Operativo Solaris.

