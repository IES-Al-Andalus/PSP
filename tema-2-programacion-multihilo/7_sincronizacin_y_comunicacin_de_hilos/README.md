# 7. Sincronización y comunicación de hilos

Los ejemplos realizados hasta ahora utilizan hilos independientes; una vez iniciados los hilos, éstos no se relacionan con los demás y no acceden a los mismos datos u objetos, por lo que no hay conflictos entre ellos. Sin embargo, hay ocasiones en las que distintos hilos de un programa necesitan establecer alguna relación entre sí y **compartir recursos o información**. Se pueden presentar las siguientes situaciones:

* Dos o más hilos **compiten por obtener un mismo recurso**, por ejemplo dos hilos que quieren escribir en un mismo fichero o acceder a la misma variable para modificarla.
* Dos o más hilos **colaboran para obtener un fin común** y para ello, necesitan comunicarse a través de algún recurso. Por ejemplo un hilo produce información que utilizará otro hilo.

En cualquiera de estas situaciones, es necesario que los hilos se ejecuten de manera controlada y coordinada, para evitar posibles interferencias que pueden desembocar en programas que se bloquean con facilidad y que intercambian datos de manera equivocada.

¿Cómo conseguimos que los hilos se ejecuten de manera coordinada? Utilizando sincronización y comunicación de hilos:

* **Sincronización**. Es la capacidad de informar de la situación de un hilo a otro. El objetivo es establecer la secuencialidad correcta del programa.
* **Comunicación**. Es la capacidad de transmitir información desde un hilo a otro. El objetivo es el intercambio de información entre hilos para operar de forma coordinada.

En Java la sincronización y comunicación de hilos se consigue mediante:

* **Monitores**. Se crean al marcar bloques de código con la palabra `synchronized`.
* **Semáforos**. Podemos implementar nuestros propios [semáforos_Semáforo_Una variable especial \(o tipo abstracto de datos\) que constituye el método clásico para restringir o permitir el acceso a recursos compartidos en un entorno de multiprocesamiento \(en el que se ejecutarán varios procesos cocurrentemente\).](), o bien utilizar la clase Semaphore incluida en el paquete `java.util.concurrent`. Un semáforo binario es un indicador de condición que registra si un recurso está disponible o no.
* **Notificaciones**. Permiten comunicar hilos mediante los métodos `wait()`, `notify()` y `notifyAll()` de la clase `java.lang.Object`.

Por otra parte, Java proporciona en el paquete `java.util.concurrent` varias **clases de sincronización** que permiten la sincronización y comunicación entre diferentes hilos de una aplicación multithreadring, como son: `Semaphore`, `CountDownLatch`, `CyclicBarrier` y `Exchanger`.

En los siguientes apartados veremos ejemplos de todo esto.

