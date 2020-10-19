# 5. Estados de un hilo

 Hasta el momento, **Juan** ha podido comprobar que **Ana** se desenvuelve muy bien con todos los aspectos repasados sobre hilos en Java, pero lo más complicado comienza ahora. Juan le pregunta a **Ana**, —¿Tienes claro los diferentes estados que puede tener un hilo a lo largo de su vida y cómo se pasa de uno a otro? A lo que **Ana** le responde, —Mas o menos...., pero me vendría bien dar un repaso, porque además quiero recordar que había unos cuantos métodos para pasar de un estado a otro cuyo uso es peligroso y además ya están considerados obsoletos debido a los problemas que ocasionan.

El **ciclo de vida de un hilo** comprende los diferentes estados en los que puede estar un hilo desde que se crea o nace hasta que finaliza o muere.

De manera general, los **diferentes estados** en los que se puede encontrar un hilo son los siguientes:

* **Nuevo** \(new\): se ha creado un nuevo hilo, pero aún no está disponible para su ejecución.
* **Ejecutable** \(runnable\): el hilo está preparado para ejecutarse. Puede estar **Ejecutándose**, siempre y cuando se le haya asignado tiempo de procesamiento, o bien que no esté ejecutándose en un instante determinado en beneficio de otro hilo, en cuyo caso estará **Preparado**.
* **No Ejecutable o Detenido** \(no runnable\): el hilo podría estar ejecutándose, pero hay alguna actividad interna al propio hilo que se lo impide, como por ejemplo una espera producida por una operación de [Entrada/Salida_Entrada/Salida_Operaciones que constituyen un flujo de información del programa con el exterior.]() \(E/S\). Si un hilo está en estado "No Ejecutable", no tiene oportunidad de que se le asigne tiempo de procesamiento.
* **Muerto o Finalizado** \(terminated\): el hilo ha finalizado. La forma natural de que muera un hilo es finalizando su método `run()`.

El método `getState()` de la clase `thread`, permite obtener en cualquier momento el estado en el que se encuentra un hilo. Devuelve por tanto: `NEW`, `RUNNABLE`, `NO RUNNABLE` o `TERMINATED`.

En la imagen anterior, puedes ver algunos de los métodos que permiten obtener cada uno de esos estados. Los veremos con más detalle en los siguientes apartados.

**Señala si la afirmación siguiente es verdadera o falsa:**

