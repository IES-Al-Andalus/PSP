# 8.1. Conceptos básicos

 Comencemos revisando algunas clasificaciones de sistemas distribuidos y paralelos:

* En función de los **conjuntos de instrucciones y datos** \(conocida como la **taxonomía de Flynn**\):
  * La arquitectura secuencial la denominaríamos SISD \(single instruction single data\).
  * Las diferentes arquitecturas paralelas \(o distribuidas\) en diferentes grupos: SIMD \(single instruction multiple data\), MISD \(multiple instruction single data\) y MIMD \(multiple instruction multiple data\), con algunas variaciones como la SPMD \(single program multiple data\).
* Por **comunicación y control**:
  * **Sistemas de multiprocesamiento simétrico** \(SMP\). Son MIMD con memoria compartida . Los procesadores se comunican a través de esta memoria compartida; este es el caso de los microprocesadores de múltiples núcleos de nuestros PCs.
  * **Sistemas MIMD con memoria distribuida** . La memoria está distribuida entre los procesadores \(o nodos\) del sistema, cada uno con su propia memoria local, en la que poseen su propio programa y los datos asociados. Una red de interconexión conecta los procesadores \(y sus memorias locales\), mediante enlaces \(links\) de comunicación, usados para el intercambio de mensajes entre los procesadores. Los procesadores intercambian datos entre sus memorias cuando se pide el valor de variables remotas. Tipos específicos de estos sistemas son:
    * Clusters. Consisten en una colección de ordenadores \(no necesariamente homogéneos\) conectados por red para trabajar concurrentemente en tareas del mismo programa. Aunque la interconexión puede no ser dedicada.
    * Grid. Es un cluster cuya interconexión se realiza a través de internet.

 Veamos una introducción a algunos **conceptos básicos** que debemos conocer para **desarrollar en sistemas distribuidos**:

* **Distribución**: construcción de una aplicación por partes, a cada parte se le asigna un conjunto de responsabilidades dentro del sistema.
* **Nudo de la red**: uno o varios equipos que se comportan como una unidad de asignación integrada en el sistema distribuido.
* Un **objeto distribuido** es un **módulo de código con plena autonomía** que se puede instanciar en cualquier nudo de la red y a cuyos servicios pueden acceder clientes ubicados en cualquier otro nudo.
* **Componente: Elemento de software que encapsula una serie de funcionalidades.** Un componente, es una unidad independiente, que puede ser utilizado en conjunto con otros componentes para formar un sistema más complejo \(concebido por ser **reutilizable**\). Tiene especificado: los **servicios** que ofrece; los **requerimientos** que necesarios para poder ser instalado en un nudo; las **posibilidades de configuración** que ofrece; y, **no está ligado** a ninguna aplicación, que se puede instanciar en cualquier nudo y ser **gestionado por herramientas automáticas**. Sus **características**:
  * **Alta cohesión**: todos los elementos de un componente están estrechamente relacionados.
  * **Bajo acoplamiento**: nivel de independencia que un componente respecto a otros.
* **Transacciones: Conjunto de actividades que se ejecutan en diferentes nudos de una plataforma distribuida para ejecutar una tarea de negocio.** Una transacción finaliza cuando todas las parte implicadas clientes y múltiples servidores confirman que sus correspondientes actividades han concluido con éxito. **Propiedades ACID** de una transacción:
  * **Atomicidad**: Una transacción es una unidad indivisible de trabajo, Todas las actividades que comprende deben ser ejecutadas con éxito.
  * **Congruencia**: Después de que una transacción ha sido ejecutada, la transacción debe dejar el sistema en estado correcto. Si la transacción no puede realizarse con éxito, debe restaurar el sistema al estado original previo al inicio de la transacción.
  * **Aislamiento**: La transacciones que se ejecutan de forma concurrente no deben tener interferencias entre ellas. La transacción debe sincronizar el acceso a todos los recursos compartidos y garantizar que las actualizaciones concurrentes sean compatibles entre si.
  * **Durabilidad**: Los efectos de una transacción son permanentes una vez que la transacción ha finalizado con éxito.
* **Gestor de transacciones.** Controla y supervisa la ejecución de transacciones, asegurando sus propiedades ACID.

