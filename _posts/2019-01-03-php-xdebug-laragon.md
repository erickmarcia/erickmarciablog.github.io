---
layout: post
title: Php + XDebug + Laragon + Visual Studio Code!
---
![Banner](..\\images\\Blog\\bannerPhpXdebug.png)

Como programador una de las opciones que menos me gusta pero que realmente es necesario es el debug, mas en los casos cuando el desarrollo falla y no tienes ni la minima idea de como resolverlo.

Recién estoy llevando los cursos de la Especialidad de **EDteam** sobre Php con la profesora **Yesi Days**, por lo cual en este artículo no pretendo enseñarte cuales son los fundamentos de la depuración en Php, más bien como preparar el entorno para poder realizar la depuraciones de nuestro código por que realmente puede hacernos la vida más fácil.

# Xdebug

[Xdebug](https://xdebug.org/) es una extensión de PHP que apunta a ayudar en el proceso de depuración de sus aplicaciones. Xdebug ofrece características como:

* Seguimiento automático de la pila en caso de error
* Función de registro de llamadas
* Mostrar características como la salida var_dump () mejorada y la información de cobertura de código.

Xdebug es altamente configurable y adaptable a una variedad de situaciones. Por ejemplo, los seguimientos de la pila (que son extremadamente útiles para monitorear qué está haciendo su aplicación y cuándo) se pueden configurar a cuatro niveles de detalle diferentes. Esto significa que puede ajustar la sensibilidad de la salida de Xdebug ayudándole a obtener información granular sobre la actividad de su aplicación.

Los seguimientos de pila le muestran dónde ocurren los errores, le permiten rastrear llamadas a funciones y detallar los números de línea de origen de estos eventos. Todo lo cual es información fantástica para depurar su código.

Puedes echar un vistazo link [a la guía de instalación de Xdebug](https://xdebug.org/docs/index.php?action=install) que se ofrece en la página oficial.

## Instalación Xdebug

Para ello, necesitaremos descargar la versión de Xdebug, adecuada a nuestra versión de PHP. Hay que tener en cuenta que necesitaremos tener PHP 7.0 o superior.

Empezaremos averiguando que versión de Xdebug nos corresponde para la instalación de PHP de nuestra máquina. En este post utilizaremos Laragon pero funciona igual si tienes instalado XAMPP el proceso es muy sencillo, tan solo tenemos que abrir el navegador y escribiremos en la barra de direcciones localhost, y en el menú de la página que aparecerá pulsaremos la opción de PHPInfo.

![LaragonXdebugPhpinfo](..\\images\\Blog\\01-xdebug.png)

## Cómo agregar Xdebug a Laragon

Si tienes problemas en cargar esta pantalla puedes realizar los siguientes pasos:

1) En la barra de tareas de windows dale click al icono de Laragon.
2) Selecciona PHP
3) En el menú desplegable selecciona Quick Setting.
4) Selecciona xdebug.

![LaragonXdebug1](..\\images\\Blog\\1-xdebug.png)

Aparecerá una advertencia indicando si necesitamos ayuda para agregar Xdebug a Laragon.

![LaragonXdebug2](..\\images\\Blog\\2-xdebug.png)

Nota: al aceptar la advertencia nos redireccionará al siguiente [Link](https://forum.laragon.org/topic/264/tutorial-how-to-add-xdebug-to-laragon), en el cual nos muestra el método para agregar Xdebug a Laragon usando phpinfo() y asistente de Xdebug.

## Usando de phpinfo () y asistente de Xdebug

![LaragonXdebug3](..\\images\\Blog\\3-xdebug.png)

1) Copie todo el contenido de phpinfo():  
   [http://localhost/?Q=info](http://localhost/?Q=info)
   ![LaragonXdebug4](..\\images\\Blog\\4-xdebug.png)
   > Tips: Puedes Seleccionar toda la información con solo presionar **Ctrl + A**.

2) Pegue los datos copiados al formulario en la página del Asistente de Xdebug:
   [http://localhost/?Q=info](http://localhost/?Q=info)
   ![LaragonXdebug5](..\\images\\Blog\\5-xdebug.png)
   > Tips: Asegúrese de que al momento de pegar la información de phpInfo() en el formulario de Xdebug borrar los espacios al inicio y final.

3) Haga clic en **"Analyse my phpinfo() output."**

   ![LaragonXdebug6](..\\images\\Blog\\6-xdebug.png)

4) Una vez concluido estos pasos se nos muestra las instrucciones que necesitaremos para usar la extensión Xdebug.

   ![LaragonXdebug7](..\\images\\Blog\\7-xdebug.png)

5) Tal y como nos sugiere debemos descargar la extensión de Xdebug (en mi caso seria la **php_xdebug-2.6.1-7.2-vc15-x86_64.dll**)

   ![LaragonXdebug8](..\\images\\Blog\\8-xdebug.png)

6) Mover o copiar la extensión descargada a la ruta que nos indica **Extensions directory** (en mi caso seria **C:\laragon\bin\php\php-7.2.11-Win32-VC15-x64\ext**)
    ![LaragonXdebug9](..\\images\\Blog\\9-xdebug.png)
   >Tips: Esta dirección puede variar según donde tengas instalado Laragon.

7) Ahora editaremos el fichero **C:\laragon\bin\php\php-7.2.11-Win32-VC15-x64\php.ini**, y añadiremos al final las siguientes líneas.

       [XDebug]
       xdebug.remote_enable = 1
       xdebug.remote_autostart = 1
       zend_extension=xdebug-2.6.1-7.2-vc15-x86_64

  ![LaragonXdebug10](..\\images\\Blog\\10-xdebug.png)
   >Tips: el valor de zend_extension debe de ser el que nos indica la página de Xdebug en sus instrucciones.

    Si tienes miedo de trastear el archivo de configuración de php.ini puedes realizar los siguientes pasos explicados anterior mente el cual solo agregara la siguiente linea **zend_extension=xdebug-2.6.1-7.2-vc15-x86_64** al archivo php.ini:

      1) En la barra de tareas de windows dale click al icono de Laragon.
      2) Selecciona PHP
      3) En el menú desplegable selecciona Quick Setting.
      4) Selecciona Xdebug.

   ![LaragonXdebug1](..\\images\\Blog\\1-xdebug.png)

8) Para verificar que todo el proceso anterior ha tenido éxito, consultaremos otra vez la opción de PHPInfo, y comprobaremos que en el texto que sale al lado de la imagen de **zendengine**, aparece **“with Xdebug”** tal y como se muestra en la siguiente imagen (otra forma de comprobarlo es buscar el texto xdebug en esta página).

   ![LaragonXdebug11](..\\images\\Blog\\11-xdebug.png)

# Configurando Visual Studio Code para depurar código PHP

Una vez que hemos realizado la instalación de Xdebug ya podemos comenzar a depurar nuestros código php con Visual Studio Code. Para ello debemos asegurarnos de tener instalado en este editor la extensión de “PHP Debug”.

## Instalación de PhpDebug

Las extensiones las buscaremos usando el icono de **Extensiones** del menú de la izquierda con forma cuadrada pulsando en la caja de texto **Php Debug** y la instalaremos.
   ![Phpdebug1](..\\images\\Blog\\1-PhpDebug.png)
   > Tips: Una vez instalado, para asegurarnos de que funciona, pulsaremos el botón azul Recargar. Y si nos aparece, también pulsaremos el botón con el mensaje **“Volver a cargar Window”**.

## Configuración de PhpDebug en Visual Studio Code

1) En este momento, es cuando abriremos nuestro proyecto (Archivo > Abrir Carpeta).
2) Después, accederemos a la Vista de depuración:

   ![Phpdebug2](..\\images\\Blog\\2-PhpDebug.png)
   >Tips: Para abrir la vista de depuración, haga clic en el ícono de depuración en la barra de actividad en el lado de Código VS. También puede utilizar la combinación de teclas **Ctrl + Shift + D**.

3) Luego agregaremos una configuración para depurar PHP con Xdebug.
   ![Phpdebug3](..\\images\\Blog\\4-PhpDebug.png)
   > Tips: En la parte superior hay un selector (2), y a su lado, un engranaje. Al pulsar en el selector nos pedirá que indiquemos el lenguaje a depurar (3).

4) Seleccionaremos el lenguaje a configurar en este caso Php.
    ![Phpdebug4](..\\images\\Blog\\5-PhpDebug.png)

5) Se abrirá el archivo **launch.json** y mostrara unas líneas de código por defecto, que dejaremos tal cual
    ![Phpdebug5](..\\images\\Blog\\6-PhpDebug.png)
6) En nuestro código PHP, agregaremos puntos de interrupción haciendo click a la izquierda del número de línea. Veremos cómo aparecen puntitos rojos en cada línea esto son puntos de interrupción.
   ![Phpdebug6](..\\images\\Blog\\7-PhpDebug.png)

7) En el archivo setting.json agrega el siguiente código.

        // CONFIGURACIÓN PARA PHP
        //
        // PHP
        // Señala al ejecutable PHP.
        "php.validate.executablePath": "C:\\laragon\\bin\\php\\php-7.2.11-Win32-VC15-x64\\php.exe",
        //
        // Indica si linter se ejecuta al guardar o al escribir.
        "php.validate.run": "onType",
        //
        // PHP Intellisense
        // The path to a PHP 7+ executable.
        "php.executablePath":  "C:\\laragon\\bin\\php\\php-7.2.11-Win32-VC15-x64\\php.exe"

8) Pulsamos el botón de Iniciar depuración, y después abrimos el navegador con la dirección de nuestra página a depurar.

   ![Phpdebug7](..\\images\\Blog\\9-PhpDebug.png)

Cuando el navegador empiece a cargar la página, Visual Studio Code tomará el control y nos permitirá ir depurando paso a paso usando las típicas herramientas de depuración.

Al añadir la configuración para la depuración, Visual Studio Code habrá creado una carpeta .vscode dentro de la carpeta de nuestro proyecto con la configuración de para la depuración. A partir de entonces, cada vez que abramos nuestro proyecto, tan solo tendremos que ir a la opción de depuración, poner algún punto de interrupción y darle a la flecha verde. Si por error borramos esa carpeta, tendremos que volver a repetir los pasos para volver a añadir la configuración.

# Conclusión

¡Listos para depurar código PHP!