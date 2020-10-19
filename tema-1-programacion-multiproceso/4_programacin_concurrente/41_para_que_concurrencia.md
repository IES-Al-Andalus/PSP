# 4.1. ¿Para qué concurrencia?

 Por supuesto, la ejecución de una aplicación de forma secuencial y aislada en una máquina es lo más eficiente para esa aplicación. Entonces, ¿para qué la concurrencia?

 Las **principales razones** por las que se utiliza una estructura concurrente son:

* **Optimizar la utilización de los recursos.** Podremos simultanear las operaciones de E/S en los procesos. La CPU estará menos tiempo ociosa. Un equipo informático es como una cadena de producción, obtenemos más productividad realizando las tareas concurrentemente.
* **Proporcionar interactividad a los usuarios \(y animación gráfica\).** Todos nos hemos desesperado esperando que nuestro equipo finalizara una tarea. Esto se agravaría sino existiera el multiprocesamiento, sólo podríamos ejecutar procesos por lotes.
* **Mejorar la disponibilidad.** Servidor que no realice tareas de forma concurrente, no podrá atender peticiones de clientes simultáneamente.
* **Conseguir un diseño conceptualmente más comprensible y mantenible.** El diseño concurrente de un programa nos llevará a una mayor modularidad y claridad. Se diseña una solución para cada tarea que tenga que realizar la aplicación \(no todo mezclado en el mismo algoritmo\). Cada proceso se activará cuando sea necesario realizar cada tarea.
* **Aumentar la protección.** Tener cada tarea aislada en un proceso permitirá depurar la seguridad de cada proceso y, poder finalizarlo en caso de mal funcionamiento sin que suponga la caída del sistema.

 Los anteriores pueden parecer los motivos para utilizar concurrencia en sistemas con un solo procesador. Los actuales avances tecnológicos hacen necesario **tener en cuenta** la concurrencia en el diseño de las aplicaciones para aprovechar su potencial. Los nuevos entornos hardware son:

* **Microprocesadores con múltiples** núcleos que comparten la memoria principal del sistema.
* **Entornos multiprocesador con memoria compartida.** Todos los procesadores utilizan un mismo espacio de direcciones a memoria, sin tener conciencia de dónde están instalados físicamente los módulos de memoria.
* **Entornos distribuidos.** Conjunto de equipos heterogéneos o no, conectados por red y/o Internet.

 Los **beneficios** que obtendremos al adoptar un modelo de programa concurrente son:

* Estructurar un programa como conjunto de procesos concurrentes que interactúan, **aporta gran claridad** sobre lo que cada proceso debe hacer y cuando debe hacerlo.
* **Puede conducir a una reducción del tiempo de ejecución.** Cuando se trata de un entorno monoprocesador, permite solapar los tiempos de E/S o de acceso al disco de unos procesos con los tiempos de ejecución de CPU de otros procesos. Cuando el entorno es multiprocesador, la ejecución de los procesos es realmente simultánea en el tiempo \(paralela\), y esto reduce el tiempo de ejecución del programa.
* **Permite una mayor flexibilidad de planificación.** Procesos de alta prioridad pueden ser ejecutados antes de otros procesos menos urgentes.
* La concepción concurrente del software **permite un mejor modelado** previo **del comportamiento del programa**, y en consecuencia un **análisis más fiable** de las diferentes opciones que requiera su diseño.

## Pregunta

**La concurrencia permite que la productividad de los equipos informáticos...**

> Construir una aplicación software es una tarea mucho más compleja de lo que parece al iniciarla. El espíritu de la crisis del software.

