# 7.6. La clase Semaphore

La clase `Semaphore` del paquete `java.util.concurrent`, **permite definir un semáforo** para controlar el acceso a un recurso compartido.

Para **crear y usar un objeto** `Semaphore` haremos lo siguiente:

* Indicar al constructor `Semaphore` \(`int permisos`\) el total de permisos que se pueden dar para acceder al mismo tiempo al recurso compartido. Este valor coincide con el número de hilos que pueden acceder a la vez al recurso.
* Indicar al semáforo mediante el método `acquire()`, que queremos acceder al recurso, o bien mediante `acquire(int permisosAdquirir)` cuántos permisos se quieren consumir al mismo tiempo.
* Indicar al semáforo mediante el método `release()`, que libere el permiso, o bien mediante `release(int permisosLiberar)`, cuantos permisos se quieren liberar al mismo tiempo.
* Hay otro constructor `Semaphore (int permisos, boolean justo)` que mediante el parámetro `justo` permite garantizar que el primer hilo en invocar `adquire()` será el primero en adquirir un permiso cuando sea liberado. Esto es, garantiza el orden de adquisición de permisos, según el orden en que se solicitan.

¿Desde dónde se deben invocar estos métodos? Esto dependerá del **uso de** `Semaphore`.

* Si se usa **para proteger secciones críticas**, la llamada a los métodos `acquire()` y `release()` se hará desde el recurso compartido o sección crítica, y el número de permisos pasado al constructor será 1.
* Si se usa **para comunicar hilos**, en este caso un hilo invocará al método `acquire()` y otro hilo invocará al método `release()` para así trabajar de manera coordinada. El número de permisos pasado al constructor coincidirá con el número máximo de hilos bloqueados en la cola o lista de espera para adquirir un permiso.

En el siguiente enlace tienes un ejemplo del uso de `Semaphore` para proteger secciones críticas o recursos compartidos. Es el ejemplo que vimos del acceso simultáneo de 4 terminales a un Servidor, pero resuelto ahora con la clase `Semaphore` en vez de con `synchronized`.

En el siguiente enlace tienes un ejemplo del uso de `Semaphore` para comunicar hilos. Es el ejemplo de los Lectores-Escritores. Se inician 5 hilos lectores y 2 escritores, como en el ejemplo que resolvimos con `wait()` y `notify()`.

En el siguiente enlace, puedes ver otro ejemplo con la clase `Semaphore`. En este ejemplo se usa `Semaphore` para controlar que en primer lugar se ejecuten siempre dos hilos concretos y en en segundo lugar otros.

[Ejemplo que sincroniza hilos mediante la clase Semaphore.](http://blogricardo.wordpress.com/2010/07/19/sincronizacion-pura-en-java/)

