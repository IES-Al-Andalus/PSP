# 8. Aplicaciones multihilo

 Una aplicación multihilo debe reunir las siguientes **propiedades**:

* **Seguridad**. La aplicación no llegará a un estado inconsistente por un mal uso de los recursos compartidos. Esto implicará sincronizar hilos asegurando la exclusión mutua.
* **Viveza**. La aplicación no se bloqueará o provocará que un hilo no se pueda ejecutar. Esto implicará un comportamiento no egoísta de los hilos y ausencia de interbloqueos e inanición.

 La **corrección de la aplicación** se mide en función de las propiedades anteriores, pudiendo tener:

* **Corrección parcial**. Se cumple la propiedad de seguridad. El programa termina y el resultado es el deseado.
* **Corrección total**. Se cumplen las propiedades de seguridad y viveza. El programa termina y el resultado es el correcto.

 Por tanto, al desarrollar una aplicación multihilo habrá que **tener en cuenta los siguientes aspectos**:

* La situación de los hilos en la aplicación: hilos independientes o colaborando/compitiendo.
  * Independientes. No será necesario sincronizar y/o comunicar los hilos.
  * Colaborando y/o compitiendo. Será necesario sincronizar y/o comunicar los hilos, evitando interbloqueos y esperas indefinidas.
* Gestionar las prioridades, de manera que los hilos más importantes se ejecuten antes.
* No todos los Sistemas Operativos implementan time-slicing.
* La ejecución de hilos es no-determinística.

 Por lo general, las aplicaciones multihilo son más difíciles de desarrollar y complicadas de depurar que una aplicación secuencial o de un solo hilo; pero si utilizamos las librerías que aporta el lenguaje de programación, podemos obtener algunas ventajas:

* **Facilitar la programación**. Requiere menos esfuerzo usar una clase estándar que desarrollarla para realizar la misma tarea.
* **Mayor rendimiento**. Los algoritmos utilizados han sido desarrollados por expertos en concurrencia y rendimiento.
* **Mayor fiabilidad**. Usar librerías o bibliotecas estándar, que han sido diseñadas para evitar interbloqueos \(deadlocks\), cambios de contexto innecesarios o condiciones de carrera, nos permiten garantizar un mínimo de calidad en nuestro software.
* **Menor mantenimiento**. El código que generemos será más legible y fácil de actualizar.
* **Mayor productividad**. El uso de una API estándar permite mejor coordinación entre desarrolladores y reduce el tiempo de aprendizaje.

 Teniendo en cuenta esto último, cuando vayas a desarrollar una aplicación multihilo debes hacer uso de las utilidades que ofrece el propio lenguaje. Esto facilitará la puesta a punto del programa y su depuración.

