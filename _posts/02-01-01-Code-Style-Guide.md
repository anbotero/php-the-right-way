---
title: "Guía de estilo de codificación"
---
# Guía de estilo de codificación

La comunidad PHP es numerosa y diversa, compuesta por innumerables bibliotecas, armazones y componentes.
Es común para desarrolladores en PHP escoger varias de éstas, y combinarlas en un mismo proyecto.
Es importante que el código PHP se adhiera (tanto como sea posible) a un estilo común de codificación,
para facilitarle a los desarrolladores mezclar y barajar varias bibliotecas en sus proyectos.

El [Grupo de interoperabilidad entre armazones][fig] (antiguamente conocido como el 'Grupo de Estándares
PHP') ha propuesto y aproboado una serie de recomendaciones de estilo, conocidas como [PSR-0][psr0],
[PSR-1][psr1] y [PSR-2][psr2]. No dejes que los nombres graciosos te confundan, estas recomendaciones son
tan solo un conjunto de reglas que algunos proyectos como Drupal, Zend, CakePHP, Symfony, phpBB, AWS SDK,
FuelPHP, Lithium, y otros, están comenzando a adoptar. Puedes utilizarlas en tus propios proyectos, o
continuar utilizado tu estilo personal.

Lo ideal es que se escriba código PHP que se adhiera a uno o más de estos estándares, de forma que otros
desarrolladores puedan entender y trabajar con facilidad tu código. Cada una se basa en la recomendación
anterior, por lo que usar PSR-1 requiere PSR-0, pero no PSR-2.

* [Lee acerca de PSR-0][psr0].
* [Lee acerca de PSR-1][psr1].
* [Lee acerca de PSR-2][psr2].

Puedes utilizar las reglas [phpcs-psr][phpcs-psr] para [PHP_CodeSniffer][phpcs] y cotejar tu código
con estas recomendaciones.

Utiliza el [PHP Coding Standards Fixer][phpcsfixer] de Fabien Potencier para modificar automáticamente
tu sintaxis de acuerdo a estos estándares, ahorrándote tener que modificar cada problema a mano.

[fig]: http://www.php-fig.org/
[psr0]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md
[psr1]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md
[psr2]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md
[phpcs-psr]: https://github.com/klaussilveira/phpcs-psr
[phpcs]: http://pear.php.net/package/PHP_CodeSniffer/
[phpcsfixer]: http://cs.sensiolabs.org/