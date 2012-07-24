---
title: "Interfaz de línea de comandos"
isChild: true
---
## Interfaz de línea de comandos

PHP fue creado inicialmente para escribir aplicaciones web, pero también es útil para configurar
programas de línea de comandos (CLI). Los programas de línea de comandos en PHP pueden ayudarte a
automatizar tareas como las pruebas, el despliegue, y administración de aplicaciones.

Los programas CLI en PHP son poderosos porque te permiten utilizar el código de tu programa
directamente sin tener que crear y asegurar una interfaz gráfica para él. ¡Tan solo asegúrate
de no poner tus scripts CLI en PHP en las raíz web pública!

Intenta ejecutar PHP desde tu línea de comandos:

{% highlight bash %}
> php -i
{% endhighlight %}

La opción `-i` imprime tu configuración PHP tal como la función [`phpinfo`][phpinfo].

La opción `-a` suministra una consola interactiva, similar al IRB de Ruby o a la consola interactiva
de Python. Hay además una buena cantidad de otras [opciones de línea de comandos][cli-options].

Escribcamos un sencillo programa CLI “Hola, $nombre”. Para comenzar, crea un archivo llamado `hola.php`,
como en el ejemplo:

{% highlight php %}
<?php
if($argc != 2) {
    echo "Modo de empleo: php hola.php [nombre].\n";
    exit(1);
}
$nombre = $argv[1];
echo "Hola, $nombre\n";
{% endhighlight %}

PHP configura dos variables especiales basadas en los argumentos con los que se ejecuta tu script.
[`$argc`][argc] es una variable entera que contiene el *cantidad* de argumentos y [`$argv`][argv]
es una variable de tipo matriz, que contiene el *valor* de cada argumento. El primer argumento
siempre es el nombre del archivo de tu script PHP, en nuestro caso `hola.php`.

La expresión `exit()` es utilizada con un valor diferente de cero para hacerle saber a la consola
que el comando falló. Normalmente los códigos de salida se pueden encontrar [aquí][exit-codes].

Para ejecutar nuestro script de ejemplo, escribimos desde la línea de comandos:

{% highlight bash %}
> php hola.php
Modo de empleo: php hola.php [nombre]
> php hola.php mundo
Hola, mundo
{% endhighlight %}


 * [Aprende un poco más cómo usar PHP desde la línea de comando][php-cli].
 * [Aprende cómo configurar Windows para que ejecute PHP desde la línea de comandos][php-cli-windows].

[phpinfo]: http://www.php.net/manual/es/function.phpinfo.php
[cli-options]: http://www.php.net/manual/es/features.commandline.options.php
[argc]: http://www.php.net/manual/es/reserved.variables.argc.php
[argv]: http://www.php.net/manual/es/reserved.variables.argv.php
[exit-codes]: http://www.gsp.com/cgi-bin/man.cgi?section=3&topic=sysexits
[php-cli]: http://www.php.net/manual/es/features.commandline.php
[php-cli-windows]: http://www.php.net/manual/es/install.windows.commandline.php