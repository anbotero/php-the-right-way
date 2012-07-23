---
title: "Configuración en Windows"
isChild: true
---
## Configuración en Windows

En Windows, PHP está disponible de muchas maneras. Puedes [descargar los binarios][php-downloads]
y hasta hace poco podías utilizar un instalador '.msi'. El instalador ya no es soportado y desaparece
desde PHP 5.3.0.

Para aprender y para desarrollo local, puedes utilizar el servidor web embebido con PHP 5.4, de forma que
no tengas que preocuparte por configurarlo. Si prefieres un “todo en uno” que incluya un completo
servidor web y también MySQL, entonces herramientas como [Web Platform Installer][wpi], [XAMPP][xampp]
y [WAMP][wamp] te ayudarán a tener andando un entorno rápido de desarrollo en Windows. Con eso dicho,
estas herramientas son un poco diferentes a las de producción, así que ten cuidado de las diferencias
de entorno si estás trabajando en Windows y desplegando a Linux.

Si necesitas poner a andar tu sistema de producción sobre Windows, entonces IIS7 te dará la mejor
estabilidad y rendimiendo. Puedes utilizar [phpmanager][phpmanager] (una interfaz para IIS7) para hacer
simple la tarea de configurar y administrar PHP. IIS7 viene con FastCGI incorporado y listo para andar,
tan solo tienes que conigurarle el módulo de PHP. Para soporte y recursos adicionales, hay un
[área dedicada en iis.net][php-iis] para PHP.

Generalmente ejecutar tu aplicación en un entorno diferente en desarrollo y en producción puede llevar
a anomalías apareciendo cuando publicas tus cambios en producción. Si estás desarrollando en Windows y
desplegando en Linux (o cualquier sistema diferente de Windows), entonces deberías considerar una
máquina virtual. Esto suena engorroso, pero usando [Vagrant][vagrant] puedes configurar paquetes simples,
para que luego utilizando [Puppet][puppet] o [Chef][chef] puedas gestionar estos paquetes y compartirlos
con tus colegas para asegurarte de que todos están trabajando sobre una misma base. Más sobre esto pronto.

[php-downloads]: http://windows.php.net/download/
[wpi]: http://www.microsoft.com/web/downloads/platform.aspx
[xampp]: http://www.apachefriends.org/es/xampp.html
[wamp]: http://www.wampserver.com/
[phpmanager]: http://phpmanager.codeplex.com/
[php-iis]: http://php.iis.net/
[vagrant]: http://vagrantup.com/
[puppet]: http://www.puppetlabs.com/
[chef]: http://www.opscode.com/