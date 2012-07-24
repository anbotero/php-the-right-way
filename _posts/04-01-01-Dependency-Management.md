---
title: "Gestión de dependiencias"
---
# Gestión de dependiencias

Hay una gran cantidad de bibliotecas, armazones, y componentes en PHP de donde escoger. Tu proyecto muy
seguramente va a utilizar varios de ellos: éstas son las dependencias del proyecto. Hasta hace poco,
PHP no tenía un buen modo de manejar estas dependencias del proyecto. Incluso si las administrabas
manualmente, todavía tenías que preocuparte por los autocargadores. ¡Pero no más!

Actualmente hay dos sistemas que sobresalen en la gestión de dependencias para PHP: Composer y PEAR.
¿Cuál de ellos te sirve? La respuesta es ambos.

 * Utiliza **Composer** cuando manejes dependencias para un solo proyecto.
 * Utiliza **PEAR** cuando manejes dependencias para PHP como conjunto en tu sistema.

En general, los paquetes de Composer estarán disponibles solo en proyectos que especifiques
explícitamente, mientras que el paquete de PEAR estará disponible para todos tus proyectos en PHP.
Aunque a primera vista PEAR puede parecer la opción más fácil, hay ventajas en utilizar un
sistema que sea de proyecto por proyecto para tus dependencias.