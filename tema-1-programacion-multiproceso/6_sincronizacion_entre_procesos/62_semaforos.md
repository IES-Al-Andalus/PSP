# 6.2. Semáforos

 Veamos una primera solución eficiente a los problemas de sincronismo, entre procesos que acceden a un mismo recurso compartido.

 Podemos ver varios procesos que quieren acceder al mismo recurso, como coches que necesitan pasar por un cruce de calles. En nuestros cruces, los semáforos nos indican cuándo podemos pasar y cuándo no. Nosotros, antes de intentar entrar en el cruce, primero miramos el color en el que se encuentra el semáforo, y si está en verde \(abierto\), pasamos. Si el color es rojo \(cerrado\), quedamos a la espera de que ese mismo semáforo nos indique que podemos pasar. Este mismo funcionamiento es el que van a seguir nuestros semáforos en programación concurrente. Y, son una solución eficiente, porque los procesos quedarán bloqueados \(y no en espera activa\) cuando no puedan acceder al recurso, y será el semáforo el que vaya desbloqueándolos cuando puedan pasar.

 Al **utilizar** un semáforo, lo veremos como un **tipo dato**, que podremos instanciar. Ese objeto semáforo podrá tomar un determinado **conjunto de valores y** se podrá realizar con él un **conjunto** determinado **de operaciones**. Un semáforo, **tendrá también asociada una lista de procesos que suspendidos que se encuentran a la espera de entrar en el mismo**.

 Dependiendo del conjunto de datos que pueda tomar un semáforo, tendremos:

* Semáforos **binarios**. Aquellos que pueden tomar sólo valores 0 ó 1. Como nuestras luces verde y roja.
* Semáforos **generales**. Pueden tomar cualquier valor Natural \(entero no negativo\).

 En cualquier caso, los valores que toma un semáforo representan:

* Valor igual a 0. Indica que el semáforo está cerrado.
* Valor mayor de 0. El semáforo está abierto.

 Cualquier **semáforo** permite **dos operaciones seguras** \(la implementación del semáforo garantiza que la operación de chequeo del valor del semáforo, y posterior actualización según proceda, es siempre segura respecto a otros accesos concurrentes \):

* `objSemaforo.wait()`: Si el semáforo no es nulo \(está abierto\) decrementa en uno el valor del semáforo. Si el valor del semáforo es nulo \(está cerrado\), el proceso que lo ejecuta se suspende y se encola en la lista de procesos en espera del semáforo.
* `objSemaforo.signal()`: Si hay algún proceso en la lista de procesos del semáforo, activa uno de ellos para que ejecute la sentencia que sigue al wait que lo suspendió. Si no hay procesos en espera en la lista incrementa en 1 el valor del semáforo.

 Además de la operación segura anterior, con un semáforo, también podremos realizar una operación no segura, que es la **inicialización del valor del semáforo**. Ese valor indicará cuántos procesos pueden entrar concurrentemente en él. Esta inicialización la realizaremos al crear el semáforo.

 La ventaja de utilizar semáforos es que son fáciles de comprender, proporcionan una **gran capacidad funcional \(podemos utilizarlos para resolver cualquier problema de concurrencia\)**. Pero, su nivel bajo de abstracción, los hace **peligrosos de manejar** y, a menudo, son la **causa de muchos errores**, como es el interbloqueo. Un simple olvido o cambio de orden conduce a bloqueos; y requieren que la gestión de un semáforo se distribuya por todo el código lo que hace la depuración de los errores en su gestión es muy difícil.

 En **java**, encontramos la clase `Semaphore` dentro del paquete `java.util.concurrent`; y su uso real **se aplica** a los **hilos** de un mismo proceso, para arbitrar el acceso de esos hilos de forma concurrente a una misma región de la memoria del proceso. Por ello, veremos ejemplos de su uso en siguiente unidades de este módulo.

