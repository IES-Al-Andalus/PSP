# 7.3. Monitores. Segmentos de código synchronized

 Hay casos en los que no se puede, o no interesa sincronizar un método. Por ejemplo, no podremos sincronizar un método que no hemos creado nosotros y que por tanto no podemos acceder a su código fuente para añadir `synchronized` en su definición. La forma de resolver esta situación es **poner las llamadas a los métodos que se quieren sincronizar dentro de segmentos sincronizados** de la siguiente forma: `synchronized (objeto){ // sentencias segmento; }`

 En este caso el **funcionamiento** es el siguiente:

* El objeto que se pasa al segmento, es el objeto donde está el método que se quiere sincronizar.
* Dentro del segmento se hará la llamada al método que se quiere sincronizar.
* El hilo que entra en el segmento declarado `synchronized` se hará con el monitor del objeto, si está libre, o se bloqueará en espera de que quede libre. El monitor se libera al salir el hilo del segmento de código `synchronized`.
* Sólo un hilo puede ejecutar el segmento synchronized a la vez.

 En el ejemplo del problema de los jardines, aplicando este procedimiento, habría que sincronizar el objeto que denominaremos `jardin` y que será desde donde se invoca al método `incrementaCuenta()`, método que manipula la variable `cuenta` que modifican diferentes hilos:

 Observa que:

* Ahora el método incrementaCuenta\(\) no será synchronized \(se haría igual para decrementaCuenta\(\)\),
* Se está consiguiendo un acceso con exclusión mutua sobre el objeto jardin, aún cuando su clase no contiene ningún segmento ni método synchronized.

 En el siguiente enlace dispones del ejemplo completo con los cambios que acabamos de indicar.

 Debes **tener en cuenta** que:

* Declarar un método o segmento de código como sincronizado ralentizará la ejecución del programa, ya que la **adquisición y liberación de monitores genera una sobrecarga**.
* Siempre que sea posible, por legibilidad del código, es **mejor sincronizar métodos completos**.
* Al declarar bloques `synchronized` puede aparecer un **nuevo problema, denominado interbloqueo** \(lo veremos más adelante\).

