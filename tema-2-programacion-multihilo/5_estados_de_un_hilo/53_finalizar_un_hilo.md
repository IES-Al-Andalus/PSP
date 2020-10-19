# 5.3. Finalizar un hilo

 La forma natural de que muera o finalice un hilo es cuando **termina de ejecutarse su método** `run()`, pasando al **estado 'Muerto'**.

 Una vez que el hilo ha muerto, no lo puedes iniciar otra vez con `start()`. Si en tu programa deseas **realizar otra vez el trabajo desempeñado por el hilo**, tendrás que:

* Crear un nuevo hilo con `new()`.
* Iniciar el hilo con `start()`.

 Y ¿hay alguna forma de **comprobar si un hilo no ha muerto**?

 No exactamente, pero puedes utilizar el método `isAlive()` de la clase `thread` para comprobar si un hilo está vivo o no. Un hilo se considera que está **vivo** \(`alive`\) desde la llamada a su método `start()` hasta su muerte. `isAlive()` devuelve verdadero \(true\) o falso \(false\), según que el hilo esté vivo o no.

 Cuando el método `isAlive()` devuelve:

* False: sabemos que estamos ante un nuevo hilo recién "creado" o ante un hilo "muerto".
* True: sabemos que el hilo se encuentra en estado "ejecutable" o "no ejecutable".

 El método `stop()` de la clase `thread` \(actualmente en desuso\) también finaliza un hilo, pero es poco seguro. No debes utilizarlo. Te lo indicamos aquí simplemente porque puede que encuentres programas utilizando este método.

 En el siguiente ejemplo, te proporcionamos un programa cuyo hilo principal lanza un hilo secundario que realiza una cuenta atrás desde 10 hasta 1. Desde el hilo principal se verificará la muerte del hilo secundario mediante la función `isAlive()`. Además mediante el método `getState()` de la clase `thread` vamos obteniendo el estado del hilo secundario. Se usa también el método `thread.join()` que espera hasta que el hilo muere .

