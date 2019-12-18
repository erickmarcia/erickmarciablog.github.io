---
layout: post
title: C# - Marca de Agua en un TextEdit - CueProvider!
---
![Acordeon](..\\images\\Blog\\cshar.png)

> Este artículo hace parte de una iniciativa genial: del segundo calendario de adviento de C# español. Cada día, dos artículos nuevos sobre C# serán compartidos por la comunidad. Esta es mi contribución.

La programación es sin duda un mundo lleno de aventuras, en donde el programador es quien define los limites de su inmaginación, y durante todo este tiempo me he topado con retos tras retos y en este articulo quiero contarte de sobre una clase que he ocupado en mis proyectos.

# Marca de Agua en un TextEdit - CueProvider

La idea conciste mostrar un texto en un cuadro de texto antes de poder editarlo como forma de marca de agua o parcialmente transparentes, suelen usarse en los form de Login, para indicar el ingreso de un tipo de dato.

![WinForms Marca de agua](..\\images\\Blog\\ma1.png)

Como desarrolladores de aplicaciones modernas esto nos ayudara en nuestras implementaciones de WindosForm, para lo cual utilizaremos CueProvideres una clase pequeña que le permite establecer un banner como una marca de agua (el texto de aviso gris que desaparece automáticamente cuando comienza a escribir) en un TextBoxcontrol.

### Cómo usar CueProvider

* CueProvideres fácil de usar y tiene solo dos métodos: uno para establecer TextBox el texto de referencia de una, el otro para borrarlo. Para configurar el texto de referencia, llame **SetCue();** para limpiarlo, llame **ClearCue()**. Estas llamadas se colocan mejor en el **OnLoadcontrolador** de su formulario .

> Example:
> CueProvider.SetCue(TxtEmail.MaskBox, " Example@example.gob.ni");

### Cómo Funciona

**CueProvider** funciona enviando TextBox el **EM_SETCUEBANNER** mensaje. El mensaje se envía usando la **SendMessage()** API Win32. **EM_SETCUEBANNER** Puede encontrar más información sobre el mensaje en esta página de MSDN.

#### Clase CueProvider

* Referencias

>using DevExpress.XtraEditors;
using System;
using System.Runtime.InteropServices;
using System.Windows.Forms;

* Codigo

    Clase para poner texto en forma de Marca de Agua a un Texbox.
    Proporciona indicaciones textuales a un cuadro de texto.
    
   > public static class CueProvider
    {
        private const int EM_SETCUEBANNER = 0x1501;

        [DllImport("user32.dll", CharSet = CharSet.Auto)]
        private static extern Int32 SendMessage
          (IntPtr hWnd, int msg, int wParam, [MarshalAs(UnmanagedType.LPWStr)] string lParam);

        /// <summary>
        /// Establece el texto del cue de un cuadro de texto.
        /// Este evento permite que se le pueda mandar un mensaje al textbox en forma de marca de agua
        /// </summary>
        /// <param name="textBox">The text box.</param>
        /// <param name="cue">The cue text.</param>
        public static void SetCue (TextBox textBox, string cue)
        {
            SendMessage(textBox.Handle, EM_SETCUEBANNER, 0, cue);
            textBox.ForeColor = System.Drawing.Color.White;
        }

        /// <summary>
        /// Borra el texto de la señal de un cuadro de texto.
        /// </summary>
        /// <param name="textBox">The text box</param>
        public static void ClearCue
          (TextBox textBox)
        {
            SendMessage (textBox.Handle, EM_SETCUEBANNER, 0, string.Empty);
        }

      
    }





# Conclución

Como puede ver, no hay nada demasiado complicado en esta clase. Lo CueBanner reuní en unos minutos y quería compartirlo con la comunidad en el calendario de Aviento de C# con la esperanza de que pudiera ayudar a nuestras aplicaciones de escritorio y pulir un pocco nuestra interfaz de usuario.


C# es un lenguaje muy excepcional con muchísimas funcionalidades por descubrir.

Y tú, ¿Considerarías usar esta clase en tu próxima aplicación?

# Agradecimimento

Un Agradecimiento especial a los organizadores del segundo **#advientocsharp** en español, por darme la oportunidad de ser parte de esta evento, esperando que este articulos sea de sua agrado me despido.

# Fuentes externas.
He tomado parte de la información mostrada en esta publicación del siguiente enlace [CueProvider](https://www.codeproject.com/Articles/27853/CueProvider)
