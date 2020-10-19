# 5.2. Detener temporalmente un hilo

 ¿Qué significa que un hilo se ha detenido temporalmente? Significa que **el hilo ha pasado al estado "No Ejecutable"**.

 Y ¿cómo puede **pasar un hilo al estado "No Ejecutable"**? Un hilo pasará al estado "No Ejecutable" o "Detenido" por alguna de estas circunstancias:

* **El hilo se ha dormido**. Se ha invocado al método `sleep()` de la clase `thread`, indicando el tiempo que el hilo permanecerá deteniendo. Transcurrido ese tiempo, el hilo se vuelve "Ejecutable", en concreto pasa a "Preparado".
* **El hilo está esperando**. El hilo ha detenido su ejecución mediante la llamada al método `wait()`, y no se reanudará, pasará a "Ejecutable" \(en concreto "Preparado"\) hasta que se produzca una llamada al método `notify()` o `notifyAll()` por otro hilo. Estudiaremos detalladamente estos métodos de la clase `Object` cuando veamos la sincronización y comunicación de hilos.
* **El hilo se ha bloqueado**. El hilo está pendiente de que finalice una operación de E/S en algún dispositivo, o a la espera de algún otro tipo de recurso; ha sido bloqueado por el sistema operativo. Cuando finaliza el bloqueo, vuelve al estado "Ejecutable", en concreto "Preparado".

 En la siguiente imagen puedes ver un esquema con los diferentes métodos que hacen que un hilo pase al estado "No Ejecutable", así cómo los que permiten salir de ese estado y volver al estado "Ejecutable".

 El método `suspend()` \(actualmente en desuso o deprecated\) también permite detener temporalmente un hilo, y en ese caso se reanudaría mediante el método `resume()` \(también en desuso\). No debes utilizar estos métodos, de la clase `thread` ya que no son seguros y provocan muchos problemas. Te lo indicamos simplemente porque puede que encuentres programas que aún utilizan estos métodos.

