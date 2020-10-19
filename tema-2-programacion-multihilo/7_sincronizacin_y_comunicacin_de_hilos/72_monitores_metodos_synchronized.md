# 7.2. Monitores. Métodos synchronized

Un **monitor** es un objeto que implementa acceso bajo exclusión mutua a todos sus métodos, y provee sincronización. En Java, un monitor es una porción de código protegida por un [mutex_Mutex_Un elemento que protege recursos con exclusión mutua.]() o lock. Para **crear un monitor** en Java, hay que **marcar un bloque de código con la palabra** `synchronized`, pudiendo ser ese bloque:

* Un **método completo**.
* Cualquier **segmento de código**.

Un objeto con métodos `synchronized` proporciona un cerrojo único que permite implantar monitores con comodidad y exclusión mutua bajo control y Los métodos `wait(), notify(), notifyAll()` permiten sincronizar los accesos al monitor. Añadir `synchronized` a un método significará que:

* Hemos creado un monitor asociado al objeto.
* Sólo un hilo puede ejecutar el método `synchronized` de ese objeto a la vez.
* Los hilos que necesitan acceder a ese método `synchronized` permanecerán bloqueados y en espera.
* Cuando el hilo finaliza la ejecución del método `synchronized`, los hilos en espera de poder ejecutarlo se desbloquearán. El planificador Java seleccionará a uno de ellos.

En el siguiente documento encontrarás una explicación detallada sobre el funcionamiento de un monitor Java.

Y ¿**qué bloques interesa marcar** como `synchronized`? Precisamente los que se correspondan con secciones críticas y contengan el código o datos que comparten los hilos.

En el ejemplo anterior, "Problema de los jardines" se debería sincronizar tanto el método `incrementaCuenta()`, como el `decrementaCuenta()` tal y como ves en el siguiente código, ya que estos métodos contienen la variable cuenta, la cual es modificada por diferentes hilos. Así mientras un hilo ejecuta el método `incrementaCuenta()` del objeto `jardin, jardin.incrementaCuenta()`, ningún otro hilo podrá ejecutarlo.

En el siguiente enlace dispones del proyecto completo con los dos métodos sincronizados.

En el siguiente recurso didáctico dispones de otro sencillo ejemplo que simula el acceso simultáneo de 4 terminales a un servidor utilizando monitores Java.

