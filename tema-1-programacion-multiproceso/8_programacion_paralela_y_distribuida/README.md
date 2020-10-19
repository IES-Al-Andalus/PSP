# 8. Programación paralela y distribuida

 **Ana** y **Antonio**, ya han quedado varias tardes para repasar. La mayoría de las veces, además de repasar, aprovechan para investigar juntos sobre los conceptos que les parecen más interesantes y con proyección de futuro. **Ana**, esta tarde, está muy interesada en un concepto que **Juan** le ha comentado mientras que estaba en la empresa: los "**clústers**". **Juan** le ha explicado por encima en qué consisten: "un conjunto de equipos completos que se comportan como un único sistema y que se utilizan para resolver problemas complejos". A ella le ha parecido muy interesante, aunque no le ha quedado muy claro, qué relación tienen con la programación concurrente y cómo ha terminado hablando de ellos con **Juan**. Por la tarde se lo comenta a **Antonio** y deciden investigar.

 Dos **procesos se ejecutan de forma paralela**, si las **instrucciones** de ambos se están **ejecutando** realmente de **forma simultánea**. Esto sucede en la actualidad en sistemas que poseen más de un núcleo de procesamiento.

 La **programación paralela y distribuida** consideran los **aspectos conceptuales y físicos** de la computación paralela; siempre con el objetivo de **mejorar las prestaciones aprovechado la ejecución simultánea de tareas**.

 Tanto en la programación paralela como distribuida, existe **ejecución simultánea de tareas que resuelven un problema común**. La **diferencia** entre ambas es:

* La **programación paralela** se centra en **microprocesadores multinúcleo** \(en nuestros PC y servidores\); o ,sobre los llamados **supercomputadores**, fabricados con arquitecturas específicas, compuestos por gran cantidad de equipos **idénticos** interconectados entre sí, y que cuentan son sistemas operativos propios.
* La **programación para distribuida**, en sistemas formados por un conjunto de ordenadores **heterogéneos interconectados** entre sí, por **redes de comunicaciones de propósito general**: redes de área local, metropolitana; incluso, a través de Internet. Su **gestión** se realiza utilizando **componentes, protocolos estándar y sistemas operativos de red**.

 En la **computación paralela y distribuida**:

* **Cada procesador** tiene asignada la tarea de resolver una **porción del problema**.
* En programación paralela, los **procesos** pueden **intercambiar datos**, a través de direcciones de **memoria compartidas o** mediante una **red de interconexión propia**.
* En programación distribuida, el **intercambio de datos y la sincronización** se realizará mediante **intercambio de mensajes**.
* El **sistema** se presenta como una unidad **ocultando la realidad de las partes que lo forman**.

Cada 6 meses se publica un ranking con 500 supercomputadores más potentes del mundo. En noviembre de 2011 el supercomputador más ponente se encuentra en Japón y posee más de 700.000 núcleos de procesamiento. Curiosamente, en junio de 2005, el computador MareNostrum que se encuentra en Barcelona ocupó el puesto 5 del Top500, con sus nada despreciables 4800 núcleos.

[Listas de rankings del Top500.](http://www.top500.org/lists)

## Pregunta

**Marca, de entre las siguientes, la característica que diferencia la programación paralela de la distribuida.**

### Respuestas

 [Opción 1]()

 La programación paralela trabaja sobre computadores homogéneos y la distribuida sobre heterogéneos.

 [Opción 2]()

 La programación paralela trabaja sobre computadores heterogéneos y la distribuida sobre homogéneos.

