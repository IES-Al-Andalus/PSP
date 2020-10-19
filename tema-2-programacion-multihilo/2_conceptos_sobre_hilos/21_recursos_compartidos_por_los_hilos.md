# 2.1. Recursos compartidos por los hilos

 **Un hilo lleva asociados** los siguientes elementos:

* Un identificador único.
* Un contador de programa propio.
* Un conjunto de registros.
* Una pila \(variables locales\).

 Por otra parte, **un hilo puede compartir con otros hilos del mismo proceso los siguientes recursos**:

* Código.
* Datos \(como variables globales\).
* Otros recursos del sistema operativo, como los ficheros abiertos y las señales.

 Seguro que te estarás preguntando "si los hilos de un proceso comparten el mismo espacio de memoria, ¿qué pasa si uno de ellos la corrompe?" La respuesta es, que los otros hilos también sufrirán las consecuencias. Recuerda que en el caso de procesos, el sistema operativo normalmente protege a un proceso de otro y si un proceso corrompe su espacio de memoria los demás no se verán afectados

 El hecho de que los hilos compartan recursos \(por ejemplo, pudiendo acceder a las mismas variables\) implica que sea necesario **utilizar esquemas de bloqueo y sincronización**, lo que puede hacer más difícil el desarrollo de los programas y así como su depuración.

 Realmente, es en la sincronización de hilos, donde reside el arte de programar con hilos; ya que de no hacerlo bien, podemos crear una aplicación totalmente ineficiente o inútil, como por ejemplo, programas que tardan horas en procesar servicios, o que se bloquean con facilidad y que intercambian datos de manera equivocada.

 Profundizaremos más adelante en la sincronización, comunicación y compartición de recursos entre hilos dentro del contexto de Java.

 Pero ¿qué ventajas aportan los hilos y cuando deben utilizarse? Eso es lo que vamos a ver precisamente en el siguiente apartado.

