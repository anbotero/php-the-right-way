---
title: "Espacios de nombres"
isChild: true
---
## Espacios de nombres

Como se mencionó anteriormente, la comunidad PHP tiene muchos desarrolladores creando bastante código.
Esto significa que el código de una librería PHP puede utilizar el mismo nombre de clase que otra
librería. Cuando ambas son utilizadas en el mismo espacio de nombres, colisionan y ocasionan problemas.

Los _Espacios de nombres_ solucionan este problema. Como se describe en el manual de referencia de PHP,
los espacios de nombres pueden ser comparados a directorios del sistema operativo que _cataloga_
archivos; dos archivos con el mismo nombre pueden coexistir en directorios separados. De igual forma,
dos clases en PHP con el mismo nombre pueden coexistir en espacios de nombres de PHP separados. Es tan
sencillo como eso

Es importante que se catalogue tu código de forma que pueda ser utilizado por otros desarrolladores
sin miedo de que choque con otras librerías.

Una forma recomendada de utilizar los espacios de nombres está planteada en [PSR-0][psr0], que busca
proveer una convención estándar para que archivos, clases, y espacios de nombres, posean código que se
pueda enchufar y usar.

* [Lee acerca de Espacios de nombres][namespaces].
* [Lee acerca de PSR-0][psr0].

[namespaces]: http://www.php.net/manual/es/language.namespaces.php
[psr0]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md