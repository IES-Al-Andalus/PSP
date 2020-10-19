# 6. Sincronización entre procesos

 Ya tenemos mucho más claro, que las situaciones en las que dos o más procesos tengan que comunicarse, cooperar o utilizar un mismo recurso; implicará que deba haber cierto **sincronismo** entre ellos. O bien, unos tienen que esperar que otros finalicen alguna acción; o, tienen que realizar alguna tarea al mismo tiempo.

 En este capítulo, veremos distintas **problemáticas, primitivas y soluciones de sincronización** necesarias para resolverlas. También es cierto, que en **el sincronismo entre procesos lo hace posible el SO, y lo que hacen los lenguajes de programación de alto nivel es encapsular los mecanismos de sincronismo que proporciona cada SO en objetos, métodos y funciones.** Los lenguajes de programación, proporcionan primitivas de sincronismo entre los distintos hilos que tenga un proceso; estas primitivas del lenguaje, las veremos en la siguiente unidad.

 Comencemos viendo un ejemplo muy sencillo de un problema que se nos plantea de forma más o menos común: inconsistencias en la actualización de un valor compartido por varios

 procesos; así, nos daremos cuenta de la importancia del uso de mecanismos de sincronización.

 En programación concurrente, siempre que accedamos a algún **recurso compartido** \(eso incluye a los **ficheros**\), deberemos tener en cuenta las **condiciones** en las que **nuestro proceso debe hacer uso de ese recurso**: ¿será de forma exclusiva o no? Lo que ya definimos anteriormente como **condiciones de competencia**.

 En el caso de lecturas y escrituras en un fichero, debemos determinar si queremos acceder al fichero como sólo lectura; escritura; o lectura-escritura; y utilizar los objetos que nos permitan establecer los mecanismos de sincronización necesarios para que un proceso pueda bloquear el uso del fichero por otros procesos cuando él lo esté utilizando.

 Esto se conoce como el **problema de los procesos lectores-escritores**. El **sistema operativo, nos ayudará** a resolver los problemas que se plantean; ya que:

* Si el acceso es de **sólo lectura**. Permitirá que todos los procesos lectores, que sólo quieren leer información del fichero, **puedan acceder simultáneamente** a él.
* En el caso de **escritura**, o lectura-escritura. El SO nos permitirá pedir un tipo de **acceso** de **forma exclusiva** al fichero. Esto significará que el proceso deberá esperar a que otros procesos lectores terminen sus accesos. Y otros procesos \(lectores o escritores\), esperarán a que ese proceso escritor haya finalizado su escritura.

 Debemos tener en cuenta que, nosotros, **nos comunicamos con el SO a través de los objetos y métodos proporcionados por un lenguaje de programación**; y, por lo tanto, tendremos que **consultar cuidadosamente la documentación de las clases** que estamos utilizando para **conocer** todas las **peculiaridades** de su comportamiento.

 En la siguiente presentación, podemos ver cómo implementamos dos aplicaciones. Una de ellas, lee un valor de un fichero y lo escribe en el mismo fichero después de incrementarlo en uno. Otra aplicación crea un grupo de procesos de la primera aplicación; todos esos procesos accederán al mismo fichero para realizar la misma acción. Al final de la ejecución, al abrir el fichero que han estado utilizando, el valor que encontremos, ¿será el que esperamos que debe ser?  


