# 8.2. Tipos de paralelismo

 Las **mejoras arquitectónicas** que han sufrido los computadores se han basado en la **obtención de rendimiento explotando los diferentes niveles de paralelismo**.

 En un sistema podemos encontrar los siguientes niveles de paralelismo:

* A nivel de **bit**. Conseguido incrementando el tamaño de la palabra del microprocesador. Realizar operaciones sobre mayor número de bits. Esto es, el paso de palabras de 8 bits, a 16, a 32 y en los microprocesadores actuales de 64 bits.
* A nivel de **instrucciones**. Conseguida introduciendo pipeline en la ejecución de instrucciones máquina en el diseño de los microprocesadores.
* A nivel de **bucle**. Consiste en dividir las interaciones de un bucle en partes que se pueden realizar de manera complementaria. Por ejemplo, un bucle de 0 a 100; puede ser equivalente a dos bucles, uno de 0 a 49 y otro de 50 a 100.
* A nivel de **procedimientos**. Identificando qué fragmentos de código dentro de un programa pueden ejecutarse de manera simultánea sin interferir la tarea de una en la otra.
* A nivel de **tareas dentro de un programa**. Tareas que cooperan para la solución del programa general \(utilizado en sistemas distribuidos y paralelos\).
* A nivel de **aplicación dentro de un ordenador**. Se refiere a los conceptos que vimos al principio de la unidad, propios de la gestión de procesos por parte del sistema operativo multitarea: planificador de procesos, Round-Robin, quamtum, etc.

 En sistemas distribuidos hablaremos del **tamaño de grano o granularidad**, que es una **medida de la cantidad de computación** de un proceso software. Y se considera como el **segmento de código escogido para su procesamiento paralelo**.

* Paralelismo de **Grano Fino**: No requiere tener mucho conocimiento del código, la paralelización se obtiene de forma casi automática. Permite obtener buenos resultados en eficiencia en poco tiempo. Por ejemplo: la descomposición de bucles.
* Paralelismo de **Grano Grueso**: Es una paralelización de alto nivel, que engloba al grano fino. Requiere mayor conocimiento del código, puesto que se paraleliza mayor cantidad de él. Consigue mejores rendimientos, que la paralelización fina, ya que intenta evitar los overhead \(exceso de recursos asignados y utilizados\) que se suelen producir cuando se divide el problema en secciones muy pequeñas. Un ejemplo de paralelismo grueso lo obtenemos descomponiendo el problema en dominios \(dividiendo conjunto de datos a procesar, acompañando a estos, las acciones que deban realizarse sobre ellos\).

En programación paralela, además de utilizar CPUs, se utilizan GPU \(las **unidades de procesamiento de las tarjetas gráficas**\). Las GPU poseen una mayor potencia de cómputo al ser procesadores específicamente diseñados para resolver tareas intensivas de cómputo en tiempo real de direccionamiento de gráficos en 3D de alta resolución. En general, tienen muy buen comportamiento en algoritmos de ordenación rápida de grandes listas de datos, y transformaciones bidimensionales.

El proyecto de arquitectura de computación paralela con GPUs **CUDA**, de NVidia, puede programarse en multitud de lenguajes de programación.

Por ejemplo, las simulaciones de dinámica molecular obtienen mejores resultados en sistemas `CUDA`.

[Proyecto CUDA de NVidia.](http://www.nvidia.com/object/cuda_home_new.html)

