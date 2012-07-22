---
title: "Paradigmas de programación"
isChild: true
---
## Paradigmas de programación

PHP es un lenguaje flexible y dinámico que soporta una variedad de técnicas de programación. En los
últimos años ha evolucionado de forma dramática, en especial al añadir un modelo sólido orientado a
objetos en PHP 5.0 (2004), funciones anónimas y espacios de nombres en PHP 5.3 (2009), y “traits” en
PHP 5.4 (2012).

### Programación orientada a objetos

PHP tiene una gama completa de características de programación orientada a objetos, incluyendo soporte
para clases, clases abstractas, interfaces, herencia, constructores, clonación, excepciones y mucho más.

* [Lee acerca de PHP orientado a objetos][oop].
* [Lee acerca de Traits][traits].

### Programación funcional

PHP soporta funciones de primera clase, lo que significa que una función puede ser asignada a una variable.
Tanto las funciones propias del lenguaje como las definidas por el usuario pueden ser referenciadas por
una variable e invocadas dinámicamente. Las funciones pueden ser pasadas como argumentos a otras funciones
(propiedad llamada Funciones de alto orden) y las funciones pueden retornar otras funciones.

El lenguaje soporta la recursión, una característica que permite a una función llamarse a sí misma, pero
la mayoría del código PHP se enfoca en la iteración.

Las nuevas funciones anónimas (con soporte para clausuras) están presentes desde PHP 5.3 (2009).

PHP 5.4 agregó la habilidad de atar clausuras al ámbito de un objeto, y también mejoró el soporte para
llamadas de retorno, tal que puedan ser usadas de forma intercambiable con funciones anónimas en casi
todos los casos.

* Continúa leyendo en [Programación funcional en PHP](/pages/Functional-Programming.html).
* [Lee acerca de Funciones anónimas][anonymous-functions].
* [Lee acerca de la clase Closure][closure-class].
* [Más detalles en los RFC de Closures][closures-rfc].
* [Lee acerca de las Llamadas de retorno][callables].
* [Lee sobre la incovación dinámica de funciones con `call_user_func_array`][call-user-func-array].

### Metaprogramación

PHP soporta varias formas de metaprogramación a través de mecanismos como el API de Reflexión y los
Métodos mágicos. Hay muchos Métodos mágicos disponibles como `__get()`, `__set()`, `__clone()`,
`__toString()`, `__invoke()`, entre otros, que permiten a desarrolladores engancharze al comportamiento
de una clase. Los desarroladores en Ruby suelen decir que a PHP le falta `method_missing`, pero está
disponible como `__call()` y `__callStatic()`.

* [Lee acerca de Métodos mágicos][magic-methods].
* [Lee acerca de Reflexión][reflection].

[oop]: http://www.php.net/manual/es/language.oop5.php
[traits]: http://www.php.net/manual/es/language.oop5.traits.php
[anonymous-functions]: http://www.php.net/manual/es/functions.anonymous.php
[closure-class]: http://www.php.net/manual/es/class.closure.php
[closures-rfc]: https://wiki.php.net/rfc/closures
[callables]: http://www.php.net/manual/es/language.types.callable.php
[magic-methods]: http://www.php.net/manual/es/language.oop5.magic.php
[reflection]: http://www.php.net/manual/es/intro.reflection.php
[call-user-func-array]: http://www.php.net/manual/es/function.call-user-func-array.php