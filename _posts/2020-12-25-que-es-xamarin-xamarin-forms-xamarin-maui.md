---
layout: post
title: Xamarin - Xamarin.Forms - Xamarin MAUI
---

![Post Xamarin](..\images\Blog\Xamarin-MAUI.png)

> Este artículo hace parte de una iniciativa genial: del segundo calendario de Xamarin en español. Cada día, dos artículos nuevos sobre C# serán compartidos por la comunidad. Esta es mi contribución.

Como un verdadero principiante en el tema de Xamarin, durante toda la evolución de Xamarin, me ha costado entender la difetencia entre Xamarin y Xamarin.Forms y por si fuera poco ahora se suma Xamarin MAUI, por lo cual este árticulo va de eso, entender de una manera simple las 3 siguientes interrogantes:

- ¿Qué es Xamarin?
- ¿Qué es Xamarin.Forms?
- ¿Qué es Xamarin MAUI?

# **¿Qué es Xamarin?**

**Xamarin Native** Es lo más parecido a programar en nativo que puede haber pero utilizando para la lógica el lenguaje C# en lugar de los equivalentes nativos de iOS (Objective-C, Swift), Android (Java, Kotlin) u otros.

La creación de vistas es similar a las nativas utilizando Storyboards y XML. Se aplica el patrón MVVM siendo muy extendido para ello el uso de la librería MvvmCross. se aplica XAML para las vistas lo cual consigue compilar de manera nativa para múltiples plataformas (iOS, Android, WP8, UWP, Mac…).

Por ejemplo si usas xamarin android, es muy similar a usar java con android studio; el comportamiento del editor, actividades, framents etc. Es casi lo mismo solo que con c#.

Si usa Xamarin IOS tendras algo parecido como se trabajaraa en entorno nativo para el Iphone pero usando c#.

La ventaja es que puedes compartir lógica (acceso a datos, consumo de api) así no la tendrás que hacer lo mismo para cada plataforma. Pero la parte visual si debe hacerlo 2 veces (Una para android y una para IOS).

Xamarin le permite crear aplicaciones nativas para Android, iOS y macOS mediante un código .NET y las interfaces de usuario específicas de plataforma.

![ArquitecturaXamarin](..\images\Blog\xamarin-architecture.png)

En este diagrama se muestra la arquitectura general de una aplicación Xamarin multiplataforma. Xamarin permite crear una interfaz de usuario nativa en cada plataforma y escribir lógica de negocios en C# que se comparte entre plataformas.

Una vez entendido este apartado, pasamos al siguiente punto:

# **¿Qué es Xamarin.Forms?**

Xamarin.Forms es la evolución de Xamarin Native la cual permite crear aplicaciones nativas, con código de interfaz de usuario compartido, escrito en C# o XAML.

Xamarin.Forms es un marco de interfaz de usuario de código abierto y permite a los desarrolladores compilar aplicaciones en Xamarin.Android, Xamarin.iOS y Windows desde un único código base compartido ademas le permite a los desarrolladores crear interfaces de usuario en XAML con código subyacente en C#. Estas interfaces se representan como controles nativos con mejor rendimiento en cada plataforma.

En pos de minimizar el tiempo del desarrollo surge esta herramienta que maximiza la cantidad de código compartido entre plataformas. Con ella el código común no es solo para tareas aisladas sino que es posible diseñar todas la funcionalidades y vistas de la aplicación. Sería similar a desarrollar aplicaciones híbridas pero con resultados nativos. Con lenguaje C# para la lógica y XAML para las vistas.

En este caso el patrón MVVM con two-way data binding está perfectamente integrado sin necesidad de usar librerías externas.

![ArquitecturaXamarin](..\images\Blog\xamarin-forms-architecture.png)

En este diagrama se muestra la arquitectura general de una aplicación Xamarin.Forms multiplataforma. Xamarin.Forms proporciona una API coherente para crear elementos de interfaz de usuario entre plataformas. Esta API se puede implementar en XAML o C#, y admite el enlace de datos para patrones como Model-View-ViewModel (MVVM).

![Post Xamarin](..\images\Blog\xamarin-compare.png)

> Comparativa entre Xamarin Native y Xamarin.Forms

# **¿Qué es Xamarin MAUI?**

MAUI podriamos decir que es el acronimo de **Multi-platform App UI** pero esencialmente es la próxima evolución de Xamarin.Forms evolución que aun esta en desarrollo y formara parte de .Net6, este se trata de un framework que nos permitirá crear interfaces de usuario nativas para escritorio y dispositivos móviles, y lo más sorprendente de esto es que cuenta con una sola base de código y un único proyecto. Es decir, ¡no más cabezales distintos para cada SO móvil (iOS y Android)! Junto a MVVM, Maui también admitirá el nuevo y emocionante patrón de diseño MVU (Model-View-Update), también conocido como The Elm Architecture, el cual obtendrá el soporte de Blazor.

MAUI es un renovado Xamarin.Forms con características similares, el cual tendrá mayor soporte, y Xamarin Nativo (iOS-Android) no cambiará su estructura, solo el nombre en la versión .NET 6, así mismo deberá adaptarse a una nueva gama de bibliotecas de clases de bindings principalmente.

Con la llegada de MAUI pasaremos a tener un único proyecto. Así mismo podremos elegir el despliegue entre diferentes dispositivos o emuladores aunque tengamos un único proyecto. Y ¿qué ocurre con los recursos de la aplicación como las imágenes? El tooling gestionará fuentes compartidas en cada plataforma así como la gestión y creación de imágenes adaptadas a cada plataforma.

![Post Xamarin](..\images\Blog\maui-01-overview.png)

# **¿Qué pasa con Xamarin? y ¿Dónde deja el desarrollo Xamarin.Native (Xamarin.iOS y Xamarin.Android)?**

Pues no pasa nada de momento. Seguirá siendo la plataforma oficial para crear aplicaciones móviles y podrás crear aplicaciones de escritorio también usando los proyectos de la comunidad. Sacarán nuevas versiones cada 6 semanas como hasta ahora.

Ambos se incorporarán a la plataforma .NET 6 y se renombrarán a .NET para iOS y .NET para Android, respectivamente. También obtendrán soporte de CLI: dotnet new ios y dotnet new android, haciendo que el desarrollo sea aún más rápido.

# **Conclución**

Como puede ver, no es demasiado complicado pero que si resulta un dolor de cabeza cuando estas iniciando, espero les ayude y compartan para que más personas conozcan el mundo de Xamarin.

Buenos eso ha sido todo ppara este post, nos vemos en el siguiente.

# **Agradecimimento**

Un Agradecimiento especial a los organizadores del segundo
**[#AdvientoXamarin](https://www.luisbeltran.mx/2020/11/16/segundo-calendario-de-adviento-de-xamarin-en-espanol/?fbclid=IwAR2u3F4mTPj_WffRTmK5U3IHVcSiSyPUbwbuTxvOk2lWmHyVZO5zvA67wFU)** en español en especial a **[@LuisBeltran](https://www.facebook.com/groups/1787797968167722/user/100001759697510/)** por alentarnos a publicar lo poco que sabemos y por darme la oportunidad de ser parte de esta evento esperando un día conocerlo en persona y tomarnos un café.

Esperando que este articulos sea de sua agrado me despido.

# **Más Información:**

Parte de la información mostrada en este blog es una recopilación de varias fuentes mostradas en los siguientes links, por si deseas profundizar un poco mas del tema

## Blog de [vicenteguzman.mx](https://vicenteguzman.mx/2020/05/21/adios-xamarin-forms-hola-maui/).

## Blog de [hiberus.com](https://www.hiberus.com/crecemos-contigo/xamarin-desarrollo-multiplataforma-nativo/#:~:text=Xamarin%20es%20un%20entorno%20de%20desarrollo%20de%20apps,para%20m%C3%BAltiples%20plataformas%20%28iOS%2C%20Android%2C%20WP8%2C%20UWP%2C%20Mac%E2%80%A6%29.).

## ¿Qué es Xamarin? [docs.microsoft.com](https://docs.microsoft.com/es-es/xamarin/get-started/what-is-xamarin).

## ¿Qué es Xamarin.Forms? [docs.microsoft.com](https://docs.microsoft.com/es-es/xamarin/get-started/what-is-xamarin-forms).

![Post Xamarin](..\images\Blog\Que-es-xamarin.png)
