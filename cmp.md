# Qué es la programacion funcional 

La [programación funcional](https://es.wikipedia.org/wiki/Programaci%C3%B3n_funcional) puede ayudarnos a crear software más robusto, mantenible y fácil de testear. Lenguajes de programación funcional como [Scala](http://www.scala-lang.org/),[Haskell](https://www.haskell.org/) o [Lisp](https://es.wikipedia.org/wiki/Lisp),  [Java](https://www.java.com/) en su versión 8 permite usar la potencia de la programación funcional sin abandonar su [orientación a objetos](https://es.wikipedia.org/wiki/Programaci%C3%B3n_orientada_a_objetos).

_“Hay dos formas de diseñar software: una forma es hacerlo tan simple que obviamente no haya deficiencias, y la otra es hacerlo tan complicado que no haya deficiencias obvias. El primer método es mucho más difícil”__._

Desde que empiezas a programar con Java enseñan qué es un lenguaje de programación orientado a objetos y que Java es uno de ellos. Te enseñan a programar de manera [imperativa](https://es.wikipedia.org/wiki/Programaci%C3%B3n_imperativa) y es como se ha programado desde entonces. Con estas herramientas se tiene  que crear la mejor solución posible y hasta hoy no ha ido mal. Pero, ¿Hay una forma mejor de llegar a esas soluciones?

En la [programación declarativa](https://es.wikipedia.org/wiki/Programaci%C3%B3n_declarativa) no definimos cómo queremos resolver un problema, sino que definimos cuál es el problema. Un ejemplo sencillo para comparar estas dos formas de programar es encontrar en una lista de colores si tenemos el color _“red”__:_

 
 `boolean hasRed = false;`
 `for (String color : colors) {`
   `if (color.equals("red")) {`
      `hasRed = true;`
     `break;`
   `}`
`}`
`System.out.println("Has color red? " + hasRed);`

Aquí vemos cómo estamos definiendo la manera de resolver el problema. Esta forma de hacerlo es muy verbosa y nos hace tener que definir una variable *hasRed* para marcar si se ha encontrado o no, lo que hace que este código sea un poco _“feo”_
¿La forma declarativa?

 `System.out.println(“Has color red?:” + colors.contains(“red”));`
 
Esta solución es más concisa, más clara y más fácil de entender por cualquier persona. No sabemos la implementación que estamos usando ya que eso es cosa del código que hay por debajo. Lo que sí sabemos es exactamente lo que hace ese código: nos dice si _colors_ contiene_“red”_. Por suerte, para este ejemplo el API de Java nos provee del método _contains__,_ que nos ayuda a hacer nuestro código más legible, pero no siempre tendremos esa suerte.

En los casos en los que tengamos que crear nuestros propios métodos podemos usar la programación funcional, que es declarativa y por tanto nos puede ayudar a hacer nuestro código más limpio. Veamos un ejemplo de cómo podemos mejorar nuestro código usando programación funcional.

Dada una lista de números decimales queremos descontar un 20% a todos los que sean mayores de 25 y sumarlos: 

`BigDecimal sum = BigDecimal.ZERO;`
`for(BigDecimal number : numbers) {`
`if (number.compareTo(BigDecimal.valueOf(25)) >0) {`
`sum = sum.add(number.multiply(BigDecimal.valueOf(0.8)));`
`   }`
`   }`
`System.out.println("Total: " + sum);`

Seguro que ese código es muy familiar para todos. Como vemos, estamos creando una variable  sum donde vamos cambiando su valor en función de las condiciones que hemos definido en el enunciado.

Veamos ahora cómo escribir ese código de una manera mucho más clara de forma funcional primero en Java 8:
###### Y el mismo código usando Scala:
`val sum = numbers.filter(_ > 25)`
`.map(_ * .8)`
`.sum`
`  println(sum)`

Este código se puede “leer”. Cualquier persona que se ponga delante de él puede leerlo de la siguiente forma:

-   Filtrar los números mayores de 25.
-   Asignar a cada número un número igual a su 80%.
-   Usar el método _add_ para reducir esa lista.


#### Lenguaje De Programación Funcional 
![](http://codigolinea.com/wp-content/uploads/2015/03/logo_scala-300x133.png)

Scala es un lenguaje de programación multi-paradigma que une lo programación orientado a objetos y la programación funcional, que promueven la escalabilidad desde lo más pequeño.

El nombre de Scala significa “Scalable Languaje”, se llama así ya que fue diseñado para poder crecer según la demanda de los usuarios, se puede usar Scala para crear pequeños scripts hasta para desarrollar grandes sistemas muy sofisticados.

Las principales características de Scala son:

-   #### Tipado estático
    
    Scala es un lenguaje de tipado estático, lo que quiere decir que une el tipo a una variable durante toda la vida de esa variable. En contraste con los lenguajes de tipado dinámicos que unen el tipo al valor real referenciado por una variable, lo que significa que el tipo de una variable puede cambiar junto con el valor que hace referencia.
    
-   #### Orientado a Objetos – (OOP)
    
    Scala es un lenguaje orientado a objetos puro en el sentido de que cada valor es un objeto y cada operación es una llamada de método. El lenguaje soporta arquitecturas de componentes avanzados a través de clases y traits.
    
-   #### Funcional (FP)
    
    A pesar de que su sintaxis es bastante convencional, Scala es también un lenguaje funcional (FP) en toda regla. Tiene todo lo que se puede esperar, incluyendo funciones de primera clase, funciones anónimas, funciones de orden superior, funciones anidadas, una biblioteca con estructuras de datos inmutables eficientes, y una preferencia general de inmutabilidad sobre la mutabilidad.
    
    La Programación funcional (FP) es un paradigma de programación que es más antigua que la OOP, que se había refugiado en las torres de marfil de la academia hasta hace poco. El interés por la FP está aumentando debido a la manera que simplifica ciertos problemas de diseño, especialmente la concurrencia.
    
    Podría parecer que la programación orientada a objetos y FP son incompatibles. De hecho, la filosofía de diseño de Scala es que la OOP y FP sean más de sinergia y no oposición. Las características de uno de los enfoques puede mejorar a la otra.
    
-   #### JVM (Java Virtual Machine)
    
    Scala se ejecuta en todas las máquinas virtuales de Java y también en Android. las clases de Java y Scala pueden combinarse libremente, sin importar si residen en diferentes proyectos o en el mismo. Incluso pueden referirse mutuamente entre sí.
    
-   #### Una sintaxis concisa, elegante y flexibles
    
    Scala utiliza una serie de técnicas para minimizar la sintaxis innecesarios, haciendo el código de Scala tan sucinto como código en lenguajes dinámicos. La inferencia de tipos minimiza la necesidad de información de tipo explícito en muchos contextos. Las declaraciones de tipos y funciones son muy concisas. Scala permite incluir caracteres no alfanuméricos en el nombres de las funciones. Combinado con un poco de azúcar sintáctica, esta característica permite al usuario definir métodos que se parezcan y se comporten como operadores.
    
-   #### Arquitecturas Escalables
    
    Scala está diseñado para escalar desde pequeños scripts interpretado hasta grandes aplicaciones. Scala ofrece cuatro mecanismos del lenguaje que promueven sistemas escalables de composición:
    
    1.  Tipos explícitos;
    2.  Miembros de tipo abstracto y genéricos;
    3.  Clases anidadas;
    4.  Mixin utilizando traits
-   #### Rendimiento
    
    Como el código de Scala corre sobre el JVM, se beneficia de todas las optimizaciones de rendimiento realizadas sobre las bibliotecas y el core del JVM.
    
    Si confía en el rendimiento de Java, puede confiar en el rendimiento de Scala. Por supuesto, algunas construcciones particulares del lenguaje y algunas partes de la biblioteca pueden funcionar considerablemente mejor o peor que otras opciones en otros lenguajes de programación. Siempre deberías perfilar y optimizar tu código cuando sea necesario.
    
-   #### Preparado para el Futuro
    
    Scala brilla especialmente cuando se trata de software de servidor escalable que hace uso de procesamiento concurrente y síncrona, utilización paralela de varios núcleos y procesamiento distribuido en la nube.
    
    Su naturaleza funcional facilita una escritura segura y una programación multi-hilo de alto rendimiento. Hay menos dependencia del estado mutable y los actores de Scala proporcionan herramientas poderosas para la organización de sistemas concurrentes en un alto nivel de abstracción.
    

Scala es un lenguaje es un poco difícil dominar porque requiere de competencias en la programación orientado a objetos (OOP), la programación funcional (FP) y el tipado estático, para usarlo más eficazmente.

