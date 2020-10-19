# 6.1.1. Categoría de proceso cliente-suministrador

 En este caso, vamos a hacer una introducción a los procesos que podremos clasificar dentro de la categoría **cliente-suministrador**.

* [Cliente](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Cliente%20%28DAM_PSP01%29). Es un proceso que **requiere o solicita información o servicios** que proporciona otro proceso.
* [Suministrador](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Suministrador%20%28DAM_PSP01%29). Probablemente, te suene más el término [servidor](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Servidor%20%28DAM_PSP01%29); pero, no queremos confundirnos con el concepto de servidor en el que profundizaremos en próximas unidades. Suministrador, hace referencia a un concepto de proceso más amplio; un suministrador, suministra información o servicios; ya sea a través memoria compartida, un fichero, red, o cualquier otro recurso.
* **Información o servicio es perecedero**. La información desaparece cuando es consumida por el cliente; y, el servicio es prestado en el momento en el que cliente y suministrador están sincronizados.

 Entre **un cliente y un suministrador** \(ojo, empecemos con un proceso de cada\), **se establece sincronismo** entre ellos, por medio de **intercambio de mensajes o a través de un recurso compartido**. Entre **un cliente y un servidor**, la comunicación se establece de acuerdo a un conjunto mensajes a intercambiar con sus correspondientes reglas de uso; llamado [protocolo](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Protocolo%20%28DAM_PSP01%29). Podremos implementar nuestros propios protocolos, o, protocolos existentes \(ftp, http, telnet, smtp, pop3, …\); pero aún tenemos que ver algunos conceptos más antes de implementar protocolos.

 Cliente y suministrador, son, los procesos que vimos en nuestros ejemplos de uso básico de sockets y comunicación a través de tuberías \(apartado 4.1. Mecanismos básicos de comunicación\); y, por supuesto, se puede extender a los casos en los que tengamos un proceso que lee y otro que escribe en un recurso compartido.

 Entre procesos cliente y suministrador debemos disponer de mecanismos de sincronización que permitan que:

* Un **cliente no debe poder leer un dato hasta que no haya sido completamente suministrado**. Así nos aseguraremos de que el dato leído es correcto y consistente.
* Un **suministrador** irá produciendo **su información**, que en cada instante, **no podrá superar un volumen de tamaño máximo establecido**; por lo que el suministrador, no debe poder escribir un dato si se ha alcanzado ese máximo. Esto es así, para no desbordar al cliente.

 Lo más sencillo, es pensar que el suministrador sólo produce un dato que el cliente tiene que consumir. ¿Qué sincronismo hace falta en esta situación?

1. El cliente tiene que esperar a que el suministrador haya generado el dato.
2. El suministrador genera el dato y de alguna forma avisa al cliente de que puede consumirlo.

 Podemos pensar en dar una **solución** a esta situación con **programación secuencial**. Incluyendo un bucle en el cliente en el que esté testeando el valor de una variable que indica que el dato ha sido producido.

 Como podemos ver en este gráfico el pseudocódigo del cliente incluye el bucle del que habíamos mencionado. Ese bucle hace que esta solución sea poco eficiente, ya que el proceso cliente estaría consumiendo tiempo de CPU sin realizar una tarea productiva; lo que conocemos como [espera activa](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Espera%20activa%20%28DAM_PSP01%29). Además, si el proceso suministrador quedara bloqueado por alguna razón, ello también bloquearía al proceso cliente.

 En los próximos apartados, vamos a centrarnos en los mecanismos de programación concurrente que nos permiten **resolver** estos **problemas de sincronización entre procesos de forma eficiente**, llamados **primitivas de programación concurrente:** [semáforos](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Sem%C3%A1foro%20%28DAM_PSP01%29) y [monitores](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Monitor%20%28DAM_PSP01%29); y son estas primitivas las que utilizaremos para **proteger las secciones críticas** de nuestros procesos.

