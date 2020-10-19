# 7.1. Arquitecturas y patrones de diseño

La [Arquitectura del Software](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Arquitectura%20del%20software%20%28DAM_PSP01%29), también denominada arquitectura lógica, es el **diseño de más alto nivel** de la estructura de un sistema. Consiste en un **conjunto de patrones y abstracciones coherentes** con base a las cuales se pueden resolver los problemas. A semejanza de los planos de un edificio o construcción, estas indican la **estructura, funcionamiento e interacción entre las partes del software**.

La arquitectura de software, tiene que ver con el diseño y la implementación de estructuras de software de alto nivel. Es el resultado de ensamblar un cierto número de elementos arquitectónicos de forma adecuada para **satisfacer la mayor funcionalidad y requerimientos de desempeño** de un sistema, así como requerimientos no funcionales, como la **confiabilidad, escalabilidad, portabilidad, y disponibilidad; mantenibilidad, auditabilidad, flexibilidad e interacción**.

Generalmente, no es necesario inventar una nueva arquitectura de software para cada sistema de información. Lo habitual es **adoptar una arquitectura conocida en función de sus ventajas e inconvenientes** para cada caso en concreto. Así, las arquitecturas **más universales** son:

* **Monolítica**. El software se estructura en grupos funcionales muy acoplados.
* **Cliente-servidor**. El software reparte su carga de cómputo en dos partes independientes: consumir un servicio y proporcionar un servicio.
* **Arquitectura de tres niveles**. Especialización de la arquitectura cliente-servidor donde la carga se divide en capas con un reparto claro de funciones: una capa para la presentación \(interfaz de usuario\), otra para el cálculo \(donde se encuentra modelado el negocio\) y otra para el almacenamiento \(persistencia\). Una capa solamente tiene relación con la siguiente.

Otras arquitecturas menos conocidas son:

* En **pipeline**. Consiste en modelar un proceso comprendido por varias fases secuenciales, siendo la entrada de cada una la salida de la anterior.
* **Entre pares**. Similar a la arquitectura cliente-servidor, salvo porque podemos decir que cada elemento es igual a otro \(actúa simultáneamente como cliente y como servidor\).
* En **pizarra**. Consta de múltiples elementos funcionales \(llamados agentes\) y un instrumento de control o pizarra. Los agentes estarán especializados en una tarea concreta o elemental. El comportamiento básico de cualquier agente, es: examinar la pizarra, realizar su tarea y escribir sus conclusiones en la misma pizarra. De esta manera, otro agente puede trabajar sobre los resultados generados por otro.
* **Orientada a servicios** \(Service Oriented Architecture - SOA\) Se diseñan servicios de aplicación basados en una definición formal independiente de la plataforma subyacente y del lenguaje de programación, con una interfaz estándar; así, un servicio C\# podrá ser usado por una aplicación Java.
* **Dirigida por eventos**. Centrada en la producción, detección, consumo de, y reacción a eventos.

Los [patrones de diseño](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Patrones%20de%20dise%C3%B1o%20%28DAM_PSP01%29), se definen como soluciones de diseño que son válidas en distintos contextos y que han sido aplicadas con éxito en otras ocasiones:

* Ayudan a "arrancar" en el diseño de un programa complejo.
  * Dan una descomposición de objetos inicial "bien pensada".
  * Pensados para que el programa sea escalable y fácil de mantener.
  * Otra gente los ha usado y les ha ido bien.
* Ayudan a reutilizar técnicas.
  * Mucha gente los conoce y ya sabe como aplicarlos.
  * Están en un alto nivel de abstracción.
  * El diseño se puede aplicar a diferentes situaciones.

Existen dos **modelo básicos de programas concurrentes**:

* Un programa resulta de la actividad de objetos activos que interaccionan entre si directamente o a través de recursos y servicios pasivos.
* Un programa resulta de la ejecución concurrente de tareas. Cada tarea es una unidad de trabajo abstracta y discreta que idealmente puede realizarse con independencia de las otras tareas.

**No es obligatorio** utilizar patrones, solo es aconsejable en el caso de tener el mismo problema o similar que soluciona el patrón, siempre teniendo en cuenta que en un caso particular puede no ser aplicable.

Como podemos ver en la siguiente web, lo normal es que encontremos la definición de los patrones de diseño en UML \(`Unified Modeling Language` – Lenguaje Unificado de Modelado\).

[Enlace a la web SourceMaking \(en inglés\), con ejemplos de patrones de diseño, implementados.](http://sourcemaking.com/design_patterns)

Aunque un diagrama UML es muy fácil de entender, en el siguiente enlace, encontrarás un tutorial sencillito.

[Enlace a la web DocIRS, a su tutorial sobre UML.](http://www.docirs.cl/uml.htm)

