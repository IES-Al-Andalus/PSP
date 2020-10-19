# 8.3. Modelos de infraestructura para programación distribuida

 Las aplicaciones distribuidas requieren que componentes que se ejecutan en diferentes procesadores se comuniquen entre sí. Los **modelos** de infraestructura que permiten la **implementación** de esos **componentes**, son:

* **Uso de Sockets**: Facilitan la generación dinámica de canales de comunicación. Es actualmente la base de la comunicación. Pero al ser de muy bajo nivel de abstracción, no son adecuados a nivel de aplicación.
* **Remote Procedure Call \(RPC\)**: Abstrae la comunicación a nivel de invocación de procedimientos. Es adecuada para programación estructurada basada en librerías.
*  Invocación remota de objetos: Abstrae la comunicación a la invocación de métodos de objetos que se encuentran distribuidos por el sistema distribuido. Los objetos se localizan por su identidad. Es adecuada para aplicaciones basadas en el paradigma OO.

   **RMI \(Remote Method Invocation\)** es la solución Java para la comunicación de objetos Java distribuidos. Presenta un inconveniente, y es el paso de parámetros por valor implica tiempo para hacer la serialización, enviar los objetos serializados a través de la red y luego volver a recomponer los objetos en el destino.

* **CORBA** \(Common Object Request Brocker Architecture\) . Para facilitar el diseño de aplicaciones basadas en el paradigma Cliente/Servidor. Define servidores estandarizados a través de un modelo de referencia, los patrones de interacción entre clientes y servidores y las especificaciones de las APIs.
* **MPI** \("Message Passing Interface", Interfaz de Paso de Mensajes\) es un estándar que define la sintaxis y la semántica de las funciones contenidas en una biblioteca de paso de mensajes diseñada para ser usada en programas que exploten la existencia de múltiples procesadores.
* La Interfaz de Paso de Mensajes es un protocolo de comunicación entre computadoras. Es el estándar para la comunicación entre los nodos que ejecutan un programa en un sistema de memoria distribuida. Las llamadas de MPI se dividen en cuatro clases:
  * Llamadas utilizadas para inicializar, administrar y finalizar comunicaciones.
  * Llamadas utilizadas para transferir datos entre un par de procesos.
  * Llamadas para transferir datos entre varios procesos.
  * Llamadas utilizadas para crear tipos de datos definidos por el usuario.
* **Máquina paralela virtual**. Paquetes software que permite ver el conjunto de nodos disponibles como una máquina virtual paralela ; ofreciendo una opción práctica, económica y popular hoy en día para aproximarse al cómputo paralelo .

Existen gran cantidad de **proyectos computación distribuida**. En el siguiente enlace, puedes ver un listado de ellos. Por curiosidad, dos se están desarrollando en la Univerdidad Complutense de Madrid. Uno de ellos es una **red neuronal** que simula el comportamiento de la gran y compleja red de células neuronales autómatas; otro proyecto, utiliza modelos matemáticos de una red social, para **estudiar la evolución ideológica** de un grupo de personas a través del tiempo.

[Lista de proyectos de computación distribuida.](http://en.wikipedia.org/wiki/List_of_distributed_computing_projects)

