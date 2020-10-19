# 7.5. El problema del interbloqueo \(deadlock\)

El **interbloqueo** o bloqueo mutuo \(deadlock\) consiste en que uno a más hilos, **se bloquean o esperan indefinidamente**.

¿Cómo se llega a una situación de interbloqueo? A dicha situación se llega

* Porque **cada hilo espera a que le llegue un aviso de otro hilo que nunca le llega**.
* Porque todos **los hilos, de forma circular, esperan para acceder a un recurso**.

El problema del bloqueo mutuo, en las aplicaciones concurrentes, se podrá dar fundamentalmente cuando un hilo entra en un bloque `synchronized`, y a su vez llama a otro bloque `synchronized`, o bien al utilizar clases de `java.util.concurrent` que llevan implícita la exclusión mutua.

En el siguiente enlace encontrarás un ejemplo que produce interbloqueo. Observa que no finaliza la ejecución del programa y que en la barra de estado del IDE NetBeans \(a la derecha\) aparece la indicación de programa bloqueado. Habrá que finalizar manualmente el programa.

Otro problema, menos frecuente, es la **inanición** \(starvation\), que consiste en que un hilo es desestimado para su ejecución. Se produce cuando un hilo no puede tener acceso regular a los recursos compartidos y no puede avanzar, quedando bloqueado. Esto puede ocurrir porque el hilo nunca es seleccionado para su procesamiento o bien porque otros hilos que compiten por el mismo recurso se lo impiden.

Está claro que los programas que desarrollemos deben estar exentos de estos problemas, por lo que habrá que ser cuidadosos en su diseño.

