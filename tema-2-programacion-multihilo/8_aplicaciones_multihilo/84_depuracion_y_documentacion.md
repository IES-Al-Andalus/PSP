# 8.4. Depuración y documentación

 Dos tareas muy importantes cuando desarrollamos software de calidad son la depuración y documentación de nuestras aplicaciones.

* Mediante la **depuración** trataremos de corregir fallos y errores de funcionamiento del programa.
* Mediante la **documentación interna** aportaremos legibilidad a nuestros programas.

La **depuración de aplicaciones multihilo** es una tarea difícil debido a que:

* La ejecución de los hilos tiene un comportamiento no determinístico.
* Hay que controlar varios flujos de ejecución.
* Aparecen nuevos errores potenciales debidos a la compartición de recursos entre varios hilos:
* Errores porque no se cumple la exclusión mutua.
* Errores porque se produce interbloqueo.

Podemos realizar seguimientos de la pila de Java tanto estáticos como dinámicos, utilizando los siguientes métodos de la clase `thread`:

* `dumpStack()`. Muestra una traza de la pila del hilo \(`thread`\) en curso.
* `getAllStackTraces()`. Devuelve un Map de todos los hilos vivos en la aplicación. \(`Map` es la interfaz hacia objetos `StackTraceElement`, que contiene el nombre del fichero, el número de línea, y el nombre de la clase y el método de la línea de código que se está ejecutando\).
* `getStackTrace()`. Devuelve el seguimiento de la pila de un hilo en una aplicación.

 Tanto `getAllStackTraces()` como `getStackTrace()` permiten grabar los datos del seguimiento de pila en un log.

En el siguiente enlace encontrarás un ejemplo de cómo depurar aplicaciones multihilo desde el IDE de NetBeans. Te puedes descargar además las aplicaciones de ejemplo para practicar.

[Depurando aplicaciones mutihilo con NetBeans.](http://netbeans.org/kb/docs/java/debug-multithreaded.html)

A la hora de **documentar una aplicación multihilo** no debemos escatimar en comentarios. Si son importantes en cualquier aplicación, con más motivo en una aplicación multihilo, debido a su mayor complejidad.

Para documentar nuestra aplicación Java, utilizaremos el generador **JavaDoc**, que de forma automática genera la documentación de la aplicación a partir del código fuente. Como ya debes de saber si has estudiado el módulo de "Programación", este sistema consiste en incluir comentarios en el código, utilizando las etiquetas /\*\* y \*/, que después pueden procesarse y generar un conjunto de páginas navegables HTML.

Te recordamos mediante el vídeo \(debes tener instalado JavaDoc en tu equipo, cómo obtener la documentación de tu programa con JavaDoc y Netbeans a partir de tu código fuente.

