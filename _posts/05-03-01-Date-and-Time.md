---
title: "Fecha y hora"
isChild: true
---
## Fecha y hora

PHP tiene una clase de nombre DateTime para ayudar en la lectura, escritura, comparación o cálculo de
fechas y horas. Hay muchas funciones en PHP relacionadas con la fecha y la hora además de DateTime,
pero ésta provee una cómoda interfaz orientada a objetos de sus usos más comunes. Puede manejar
las zonas horarias, pero ese tema está por fuera de esta corta introducción.

Para comenzar a trabajar con DateTime, convierte en objeto una cadena de texto de fecha y hora con el
método de factoría `createFromFormat()` o escribe `new \DateTime` para obtener la fecha y hora actual.
Utiliza el método `format()` para convertir DateTime de vuelta a una cadena para su presentación.

{% highlight php %}
<?php
$fecha = '22. 11. 1968';
$inicio = \DateTime::createFromFormat('d. m. Y', $fecha);

echo "Fecha de inicio: " . $inicio->format('m/d/Y') . "\n";
{% endhighlight %}

Cálculo con DateTime es posible con la clase DateInterval. DateTime tiene métodos como `add()` y `sub()`
que toman un DateInterval como argumento. No escrias código que espere el mismo número de segundos cada
día, ya que el horario de verano y las alteraciones por la zona horaria van a romper con esa suposición.
En vez de eso, utiliza intervalos de fechas.
that take a DateInterval as an argument. Do not write code that expect same number of seconds in every day, both daylight
saving and timezone alterations will break that assumption. Use date intervals instead. To calculate date difference use
the `diff()` method. It will return new DateInterval, which is super easy to display.
{% highlight php %}
<?php
// crea una copia de $inicio y suma un mes y 6 días
$end = clone $start;
$end->add(new \DateInterval('P1M6D'));

$diff = $end->diff($start);
echo "Diferencia: " . $diff->format('%m mes, %d días (total: %a días)') . "\n";
// Diferencia: 1 mes, 6 días (total: 37 días)
{% endhighlight %}

On DateTime objects you can use standard comparison:
{% highlight php %}
<?php
if($start < $end) {
    echo "Start is before end!\n";
}
{% endhighlight %}
    
One last example to demonstrate the DatePeriod class. It is used to iterate over recurring events. It can take two
DateTime objects, start and end, and the interval for which it will return all events in between.
{% highlight php %}
<?php
// output all thursdays between $start and $end
$periodInterval = \DateInterval::createFromDateString('first thursday');
$periodIterator = new \DatePeriod($start, $periodInterval, $end, \DatePeriod::EXCLUDE_START_DATE);
foreach($periodIterator as $date)
{
    // output each date in the period
    echo $date->format('m/d/Y') . " ";
}
{% endhighlight %}

* [Lee acerca de DateTime][datetime].
* [Read about date formatting][dateformat] (accepted date format string options)

[datetime]: http://www.php.net/manual/es/book.datetime.php
[dateformat]: http://www.php.net/manual/es/function.date.php