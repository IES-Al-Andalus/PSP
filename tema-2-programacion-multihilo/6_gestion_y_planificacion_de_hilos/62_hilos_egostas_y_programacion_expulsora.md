# 6.2. Hilos egoístas y programación expulsora

¿De verdad existen los hilos egoístas? En un Sistema Operativo que no implemente time-slicing puede ocurrir que un hilo que entra en "ejecución" no salga de ella hasta su muerte, de manera que no dará ninguna posibilidad a que otros hilos "preparados" entren en "ejecución" hasta que él muera. Este hilo se habrá convertido en un **hilo egoísta**.

Por ejemplo, supongamos la siguiente situación en un Sistema Operativo sin time-slicing:

* La tarea asociada al método `run()` de un hilo consiste en imprimir 100 veces la palabra que se le pasa al constructor más el número de orden.
* Se inician dos hilos en `main()`, uno imprimiendo "Azul" y otro "Rojo".
* El hilo que sea seleccionado en primer lugar por el planificador se ejecutará íntegramente, por ejemplo el que imprime "Rojo" 100 veces. Después se ejecutará el otro hilo, tal y como muestra la imagen parcial de la derecha.
* Este hilo tiene un **comportamiento egoísta**.

En un Sistema Operativo que si implemente time-slicing la ejecución de esos hilos se entremezcla, tal y como muestra la imagen parcial de la izquierda, lo cual indica que no hay comportamiento egoísta de ningún hilo, esto es, el Sistema operativo combate los hilos egoístas.

El proyecto completo lo puedes descargar desde el siguiente enlace.

Según lo anterior, un mismo programa Java se puede ejecutar de diferente manera según el Sistema Operativo donde corra. Entonces, ¿que pasa con la [portabilidad_Portabilidad_Característica que posee un software para ejecutarse en diferentes plataformas, el código fuente del software es capaz de reutilizarse en vez de crearse un nuevo código cuando el software pasa de una plataforma a otra. A mayor portabilidad menor la dependencia con respecto a la plataforma.]() de Java? Java da solución a este problema mediante lo que se conoce como **programación expulsora** a través del método `yield()` de la clase `java.lang.thread`:

* `yield()` hace que un hilo que está "ejecutándose" pase a "preparado" **para permitir que otros hilos de la misma prioridad puedan ejecutarse**.

Sobre el **método** `yield()` y el egoísmo de los threads debes tener en cuenta que:

* El funcionamiento de `yield()` no está garantizado, puede que después de que un hilo invoque a `yield()` y pase a "preparado", éste vuelva a ser elegido para ejecutarse.
* No debes asumir que la ejecución de una aplicación se realizará en un Sistema Operativo que implementa time-slicing.
* En la aplicación debes incluir adecuadamente llamadas al método `yield()`, incluso a `sleep()` o `wait()`, si el hilo no se bloquea por una Entrada/Salida.

El siguiente código muestra la forma de invocar a `yield()` dentro del método `run()` de un hilo. Ten en cuenta que si la invocación se hace desde un hilo Runnable tendrás que poner `thread.yield();`

