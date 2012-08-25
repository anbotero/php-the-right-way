---
title: "Excepciones"
isChild: true
---
## Excepciones

Las excepciones son un apartado estándar en la mayoría de lenguajes de programación populares, pero
a menudo los programadores en PHP las pasan pasan por alto. Lenguajes como Ruby están fuertemente
ligados a las excepciones, de modo que si algo sale mal como por ejemplo una petición HTTP que falla,
o una consulta a la base de datos que no sirve, o incluso si no se pudo encontrar un recurso como una
imagen, Ruby (o las gemas que se utilicen) arrojarán una excepción a la pantalla lo que de inmediato
te hace saber que hay un error.

El mismo PHP es algo laxo en este sentido, y una llamada a `file_get_contents()` tan solo te va a
arrojar un `FALSE` y una advertencia. Muchos armazones veteranos como [CodeIgniter][code-igniter] tan
solo retornan un `false`, generan un mensaje en su sistema propietario de registro, y tal vez te dejen
utilizar un método como `$this->upload->get_error()` para ver qué salió mal. El problema aquí es que
se hace necesario buscar error por error y revisar la documentación para ver cuál es el método de error
para esta clase, en lugar de hacerlo lo más obvio posible.

Otro problema es cuando las clases automáticamente arrojan un error a la pantalla y terminan el proceso.
Cuando haces esto, evitas que otro desarrollador pueda manejar el error dinámicamente. Las excepciones
deben arrojarse para sensibilizar a un desarrollador sobre un error, para que puedan dedicir cómo
manejarlo. Por ejemplo:

{% highlight php %}
<?php
$email = new Fuel\Email;
$email->subject('Asunto');
$email->body('¿Qué te cuentas de nuevo?');
$email->to('alguien@ejemplo.com', 'Alguien');

try
{
    $email->send();
}
catch(Fuel\Email\ValidationFailedException $e)
{
    // La validación falló
}
catch(Fuel\Email\SendingFailedException $e)
{
    // El controlador no pudo enviar el correo
}
{% endhighlight %}

### Excepciones SPL

Una excepción inicialmente no tiene significado y lo más común para dárselo es estableciendo su nombre:

{% highlight php %}
<?php
class ValidacionExcepcion extends Exception {}
{% endhighlight %}

Esto quiere decir que puedes añadir varios bloques de captura (`catch`) y manejar Excepciones diferentes
de distinta forma. Esto puede llevar a la creación de _muchas_ Excepciones personalizadas, algunas de las
cuales puede evitarse usando las Excepciones SPL que vienen en la [extensión SPL][splext].

Si por ejemplo utilizas el Método mágico `__call()`, y se solicita un método inválido, entonces en lugar
de arrojar una Excepción estándar que no dice mucho, o de crear una Excepción personalizada solo para eso,
puedes simplemente usar `throw new BadFunctionCallException;`.

* [Lee acerca de las Excepciones][exceptions].
* [Lee acerca de las Excepciones SPL][splexe].
* [Anidando excepciones en PHP][nesting-exceptions-in-php].
* [Mejores prácticas de excepciones en PHP 5.3][exception-best-practices53].

[code-igniter]: http://codeigniter.com/
[exceptions]: http://www.php.net/manual/es/language.exceptions.php
[splexe]: http://www.php.net/manual/es/spl.exceptions.php
[splext]: /#biblioteca_estndar_de_php
[nesting-exceptions-in-php]: http://www.brandonsavage.net/exceptional-php-nesting-exceptions-in-php/
[exception-best-practices53]: http://ralphschindler.com/2010/09/15/exception-best-practices-in-php-5-3