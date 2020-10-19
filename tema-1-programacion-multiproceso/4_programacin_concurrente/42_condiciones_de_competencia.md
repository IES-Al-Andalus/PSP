# 4.2. Condiciones de competencia

 Acabamos de ver que tenemos que desechar la idea de que nuestra aplicación se ejecutará de forma aislada. Y que, de una forma u otra, va a interactuar con otros procesos. Distinguimos los siguientes **tipos básicos de interacción entre procesos concurrentes**:

* **Independientes**. Sólo interfieren en el uso de la CPU.
* **Cooperantes**. Un proceso genera la información o proporciona un servicio que otro necesita.
* **Competidores**. Procesos que necesitan usar los mismos recursos de forma exclusiva.

 En el segundo y tercer caso, **necesitamos componentes que nos permitan establecer acciones de sincronización y comunicación entre los procesos**.

 Un ejemplo sencillo de **procesos cooperantes**, es "un proceso recolector y un proceso productor". El proceso recolector necesita la información que el otro proceso produce. El proceso **recolector**, quedará bloqueado mientras que no haya información disponible.

 El proceso **productor**, puede escribir siempre que lo desee \(es el único que produce ese tipo de información\). Por supuesto, podemos complicar esto, con varios procesos recolectores para un sólo productor; y si ese productor puede dar información a todos los recolectores de forma simultánea o no; o a cuántos procesos recolectores puede dar servicio de forma concurrente. Para determinar si los recolectores tendrán que esperar su turno o no. Pero ya abordaremos las soluciones a estas situaciones más adelante.

 En el caso de procesos competidores, vamos a comenzar viendo unas **definiciones**:

* Cuando un proceso necesita un recurso de forma exclusiva, es porque mientras que lo esté utilizando él, ningún otro puede utilizarlo. Se llama [región de exclusión mutua o región crítica](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Regi%C3%B3n%20o%20secci%C3%B3n%20cr%C3%ADtica%20%28DAM_PSP01%29) al **conjunto de instrucciones en las que el proceso utiliza un recurso y que se deben ejecutar de forma exclusiva con respecto a otros procesos competidores por ese mismo recurso.**
* Cuando más de un proceso necesitan el mismo recurso, antes de utilizarlo tienen que pedir su uso, una vez que lo obtienen, el resto de procesos quedarán bloqueados al pedir ese mismo recurso. Se dice que un proceso hace **un lock \(bloqueo\) sobre un recurso cuando ha obtenido su uso en exclusión mutua.**
* Por ejemplo dos procesos, compiten por dos recursos distintos, y ambos necesitan ambos recursos para continuar. Se puede dar la situación en la que cada uno de los procesos bloquee uno de los recursos, lo que hará que el otro proceso no pueda obtener el recurso que le falta; quedando bloqueados un proceso por el otro sin poder finalizar. **Deadlock o** [interbloqueo](../../../../../mod/glossary/showentry.php?displayformat=dictionary&concept=Interbloqueo%20%28DAM_PSP01%29)**, se produce cuando los procesos no pueden obtener, nunca, los recursos necesarios para continuar su tarea.** El interbloqueo es una situación muy peligrosa, ya que puede llevar al sistema a su caída o cuelgue.

 ¿Crees que no es usual que pueda darse una situación de interbloqueo? Veamos un ejemplo sencillo: un cruce de caminos y cuatro coches.

 El coche azul necesita las regiones 1 y 3 para continuar, el amarillo: 2 y 1, el rojo: 4 y 2, y el verde: 3 y 4.

 Obviamente, no siempre quedarán bloqueados, pero se puede dar la situación en la que ninguno ceda. Entonces, quedarán interbloqueados.

