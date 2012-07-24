---
title: "Composer y Packagist"
isChild: true
---
## Composer y Packagist

Composer es un **excelente** manejador de dependencias para PHP. Haz una lista de las dependencias
de tu proyecto en un archivo `composer.json`, y con unos pocos comandos Composer automáticamente
descarga las dependencias de tu proyecto y configura su autocarga por ti.

Ya existe una gran cantidad de bibliotecas de PHP que son compatibles con Composer, y que están
listas para ser utilizadas en tu proyecto. Estos “paquetes” están listados en [Packagist][1],
el repositorio oficial para bibliotecas de PHP compatibles con Composer.

### Cómo instalar Composer

Puedes instalar Composer localmente (en tu directorio de trabajo actual, aunque esto ya no se
recomienda) o globalmente (por ejemplo: /usr/local/bin). Asumamos que quieres instalar Composer
localmente. Desde el directorio raíz de tu proyecto:

    curl -s http://getcomposer.org/installer | php

Esto va a descargar `composer.phar` (un archivo binario de PHP). Puedes ejecutarlo con `php`
para que administre tus dependencias. **Atención, por favor:** Si unificas (con el símbolo `|`)
el código descargado directamente en un interpretador, por favor lee primero el código en línea
para confirmar que sea seguro.

### Cómo instalar Composer (manualmente)

Instalar Composer manualmente es una técnica avanzada. Sin embargo, existen varios motivos por
los que un desarrollador podría preferir este método frente a la rutina de instalación interactiva.
La instalación interactiva revisa tu instalación de PHP para asegurar que:

- se está utilizando una versión suficiente.
- los archivos `.phar` se pueden ejecutar correctamente.
- los permisos de determinados directorios son suficientes.
- determinadas extensiones problemáticas no estén cargadas.
- determinadas opciones de `php.ini` están activas.

Dado que la instalación manual no realiza ninguna de estas comprobaciones, tienes que decidir
si vale la pena. Y bien, abajo está cómo obtener Composer manualmente:

    curl -s http://getcomposer.org/composer.phar -o $HOME/local/bin/composer
    chmod +x $HOME/local/bin/composer

La ruta `$HOME/local/bin` (o un directorio de tu elección) debe estar en tu variable de entorno
`$PATH`. Esto hará que se habilite el comando `composer`.

Cuando te cruces con documentación que diga que ejecutes Composer de la forma `php composer.phar install`,
puedes sustituir eso con:

    composer install

### Cómo definir e instalar dependencias

Primero, crea un archivo `composer.json` en el mismo directorio que `composer.phar`. He aquí un ejemplo
que lista [Twig][2] como una dependencia del proyecto:

	{
	    "require": {
	        "twig/twig": "1.8.*"
	    }
	}

Luego, ejecutamos este comando desde el directorio raíz del proyecto:

    php composer.phar install

Esto va a descargar y a instalar las dependencias del proyecto en el directorio `vendors/`. Luego, añade
la siguiente línea al principal archivo PHP de tu proyecto; esto le dirá a PHP cómo utilizar el
autocargador de Composer para manejar las dependencias de tu proyecto:

{% highlight php %}
<?php
require 'vendor/autoload.php';
{% endhighlight %}

Ahora puedes utilizar las dependencias de tu proyecto, y se autocargarán por demanda.

* [Lee acerca de Composer][3].

[1]: http://packagist.org/
[2]: http://twig.sensiolabs.org
[3]: http://getcomposer.org/doc/00-intro.md