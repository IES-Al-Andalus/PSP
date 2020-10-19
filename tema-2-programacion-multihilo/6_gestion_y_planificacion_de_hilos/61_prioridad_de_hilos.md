# 6.1. Prioridad de hilos

 En Java, **cada hilo tiene una prioridad** representada por un valor de tipo entero **entre 1 y 10**. Cuanto mayor es el valor, mayor es la prioridad del hilo.

 Por defecto, el **hilo principal** de cualquier programa, o sea, el que ejecuta su método `main()` siempre es creado con prioridad 5.

 El resto de **hilos secundarios** \(creados desde el hilo principal, o desde cualquier otro hilo en funcionamiento\), **heredan la prioridad que tenga en ese momento su hilo padre**.

 En la clase `thread` se definen 3 constantes para manejar estas prioridades:

* `MAX_PRIORITY` \(= 10\). Es el valor que simboliza la máxima prioridad.
* `MIN_PRIORITY` \(=1\). Es el valor que simboliza la mínima prioridad.
* `NORM_PRIORITY` \(= 5\). Es el valor que simboliza la prioridad normal, la que tiene por defecto el hilo donde corre el método `main()`.

 Además en cualquier momento se puede **obtener** y **modificar la prioridad de un hilo**, mediante los siguientes métodos de la clase thread:

* `getPriority()`. Obtiene la prioridad de un hilo. Este método devuelve la prioridad del hilo.
* `setPriority()`. Modifica la prioridad de un hilo. Este método toma como argumento un entero entre 1 y 10, que indica la nueva prioridad del hilo.

 Java tiene 10 niveles de prioridad que no tienen por qué coincidir con los del sistema operativo sobre el que está corriendo. Por ello, lo mejor es que utilices en tu código sólo las constantes `MAX_PRIORITY`, `NORM_PRIORITY` y `MIN_PRIORITY`.

 Podemos conseguir **aumentar el rendimiento de una aplicación multihilo** gestionando adecuadamente las prioridades de los diferentes hilos, por ejemplo utilizando una prioridad alta para tareas de tiempo crítico y una prioridad baja para otras tareas menos importantes.

 En el siguiente enlace tienes un ejemplo en el que se declara un hilo cuya tarea es llenar un vector con 20000 caracteres. Se inician 15 hilos con prioridades diferentes, 5 con prioridad máxima, 5 con prioridad normal y 5 con prioridad mínima. Al ejecutar el programa comprobarás que los hilos con prioridad más alta tienden a finalizar antes. Observa que se usa también el método `yield()` del que hablaremos en el siguiente apartado.

