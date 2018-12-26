---
layout: post
title: C# y Devexpress!
---
![Acordeon](..\\images\\Blog\\banner.png)

> Este artículo hace parte de una iniciativa genial: el primer calendario de adviento de C# español. Cada día, durante 9 días, dos artículos nuevos sobre C# serán compartidos por la comunidad. Esta es mi contribución.

Hace un poco mas de cinco años que conoci **C#** y junto a el **Devexpress**, era mi primer trabajo sin experiencia alguna y frente a un mundo lleno de nuevos retos, había realizado pequeños proyectos de clases con visual basic pero esto era totalmente diferente y más aún cuando mire el poder que tenía y lo que se podia hacer al ver los controles que ofrecía Devexpress y su integración con C#, creo que es por esto que le tengo tanto apreció a este lenguaje pues fue quien me dio la oportunidad de hoy poder trabajar como programador, es por eso que hoy les quiero contar un poco sobre este fremework y su integración con C#.

Devexpress desde mi punto de vista esta enfocado en la experiencia de usuario, es por ello que en este artículo estaremos abordando el tema de **Fluent Design Form and Acrylic effects** una de las nuevas capacidades diseñadas para replicar la metáfora de la próxima generación de IU de Microsoft

# WinForms - Forma de diseño fluido y efectos (WinForms Fluent Design and Acrylic Effects)

La idea de elementos de ventana parcialmente transparentes se remonta al efecto Aero en Windows 7. En las últimas versiones de Windows 10, Microsoft está introduciendo Acrylic, que se explica [en este artículo relacionado con UWP](https://docs.microsoft.com/en-us/windows/uwp/design/style/acrylic). Para ilustrar, esta imagen muestra un formulario con un control de acordeón parcialmente transparente:

![WinForms Fluent Design and Acrylic Effects](..\\images\\Blog\\winforms-fluent-form.png)
Como consecuencia de la iniciativa Fluent Design de Microsoft , muchos desarrolladores de aplicaciones modernas como la de la imagen hacen tres elecciones importantes para sus implementaciones de UI:

* Implementan un diseño adaptable, por lo que las ventanas de la aplicación se ven bien en diferentes tamaños de pantalla
* Muestran una barra de navegación que utiliza Acrílico y el efecto Revelar resaltado
* Utilizan un menú de hamburguesas, que desempeña un papel importante para los escenarios de diseño adapta

# Diseño fluido para WinForms

Para crear aplicaciones similares para Windows Forms, primero creamos un nuevo control de formulario llamado FluentDesignForm. Como reemplazo del estándar Form, esto es similar XtraForm, RibbonFormy, TabbedForm, pero también es muy diferente porque combina varios elementos conectados:

* Un control de acordeón para la navegación, con un nuevo estilo de menú de hamburguesa aplicado.
  
![Menu Hamburguesa](..\\images\\Blog\\menu.png)

* Fluent Design Form Control toma el control del área de encabezado del formulario y le permite agregar botones, editores y etiquetas en su superficie.

![Diseño fluido](..\\images\\Blog\\elements.png)

* El contenedor de formularios de diseño fluido contiene el contenido del formulario.

# Transparencia parcial

Establézcalo FluentDesignForm.EnableAcrylicAccenten true para habilitar el efecto Acrílico para el Control de Acordeón. Al mismo tiempo, el efecto Revelar resaltado también se activa, imitando una fuente de luz suave que se mueve junto con el puntero del mouse.

![Transparencia parcial](..\\images\\Blog\\transparencia.gif)
   > Notas: Tenga en cuenta que ambos efectos están habilitados en Windows 10 versión 1803 (compilación de SO 17134), que se requiere para ver estos efectos en acción. El formulario de diseño fluido detecta su compilación de Windows y utiliza automáticamente la representación de DirectX para pintar estos efectos, si es posible.

# Diseño adaptativo

Como mencioné anteriormente, el diseño adaptativo es el componente final importante de Fluent Design, y nuestro nuevo Formulario implementa esto utilizando dos valores de umbral para su ancho. Cuando un usuario cambia el tamaño del formulario, el Control de acordeón cambia automáticamente su DisplayModedependiendo del ancho.

![Diseño adaptativo](..\\images\\Blog\\resize.gif)

# Integración de acordeón

El Control de Acordeón puede integrarse con la Forma de Diseño Fluido en dos modos: un modo "tradicional" donde el encabezado del formulario es el elemento más alto, y un modo de "tamaño completo" donde el Acordeón se extiende hasta la parte superior del Formulario.

![Acordeon](..\\images\\Blog\\acordeon.png)
   > Notas: Tenga en cuenta que el modo de tamaño completo funciona mejor con las máscaras planas modernas, por lo que actualmente requiere The Bezier o una de las máscaras DevExpress de Office 2016.

# Conclución

C# es un lenguaje muy excepcional con muchísimas funcionalidades y desde mi propia experiencia Devexpress lo complementa si deseas una ofrecer una expericia de usuario amigable.

Tambien cabe mencionar que Devexpress tiene controles que se integran perfectamente con Xamarin, Visual Studio (C#, ASP.NET y ASP.NET MVC), Delphi, HTML5 / JavaScript.

Y tú, ¿Considerarías usarlos en tu próxima aplicación?

![Acordeon](..\\images\\Blog\\images.jpg)

# Agradecimimento

Un Agradecimiento especial a los organizadores del primer **#advientocsharp** en español, por darme la oportunidad de ser parte de esta evento ya que es mi primera publicación en un blog, esperando que este articulos sea de sua agrado me despido.  
