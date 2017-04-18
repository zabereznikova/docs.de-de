---
title: Erweitern des Visual Basic-Anwendungsmodells | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9752cdfa79d3db4c8b07daa95aea2c842e06cc36
ms.lasthandoff: 03/13/2017

---
# <a name="extending-the-visual-basic-application-model"></a>Erweitern des Visual Basic-Anwendungsmodells
Sie können das Anwendungsmodell Funktionen hinzugefügt, durch Überschreiben der `Overridable` Member der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>Klasse.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Dieses Verfahren können Sie das Verhalten des Anwendungsmodells anpassen und Aufrufe eigener Methoden hinzufügen, wie die Anwendung gestartet und beendet wird.  
  
## <a name="visual-overview-of-the-application-model"></a>Visuelle Übersicht über das Anwendungsmodell  
 In diesem Abschnitt werden die Sequenz von Funktionsaufrufen visuell im Visual Basic-Anwendungsmodell. Im nächste Abschnitt wird den Zweck der einzelnen Funktionen im Detail beschrieben.  
  
 Die folgende Grafik zeigt die Aufrufsequenz des Anwendungsmodells in einer normalen Visual Basic-Windows Forms-Anwendung. Die Sequenz beginnt, wenn die `Sub Main` Prozeduraufrufe der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>-Methode.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>  
  
 ![Visual Basic-Anwendungsmodell - Ausführen](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelrun.gif "VB_ModelRun")  
  
 Die Visual Basic-Anwendungsmodell enthält außerdem die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>und <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>Ereignisse.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> Der folgenden Grafik wird den Mechanismus zum Auslösen dieser Ereignisse.  
  
 ![Visual Basic-Anwendungsmodell - Neben Instanz](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelnext.gif "VB_ModelNext")  
  
 ![Visual Basic-Anwendungsmodell-nicht behandelte Ausnahme](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_unhandex.gif "VB_UnhandEx")  
  
## <a name="overriding-the-base-methods"></a>Überschreiben von Basismethoden  
 Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>Methode definiert die Reihenfolge, in denen die `Application` Methoden ausführen.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> Standardmäßig die `Sub Main` -Prozedur für eine Windows Forms-Anwendung ruft die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>-Methode.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>  
  
 Wenn die Anwendung eine normale Anwendung (mehrere Instanzen) oder die erste Instanz einer Anwendung eine Instanz der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>Methode führt die `Overridable` Methoden in der folgenden Reihenfolge:</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>  
  
1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> Standardmäßig diese Methode legt fest, die visuelle Stile, Formatvorlagen für Text und aktuellen Prinzipal für den Hauptthread der Anwendung (wenn die Anwendung Windows-Authentifizierung verwendet wird), und ruft `ShowSplashScreen` Wenn weder `/nosplash` noch `-nosplash` als Befehlszeilenargument verwendet wird.  
  
     Starten der Anwendung wird abgebrochen, wenn diese Funktion gibt `False`. Dies kann nützlich sein, wenn es gibt Situationen, in denen die Anwendung nicht ausgeführt werden soll.  
  
     Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>-Methode ruft die folgenden Methoden:</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Bestimmt, ob die Anwendung einen Begrüßungsbildschirm definiert wurde und wenn dies der Fall ist, zeigt den Begrüßungsbildschirm in einem separaten Thread an.  
  
         Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>-Methode enthält den Code, den Begrüßungsbildschirm anzeigt, Bildschirm mindestens für die angegebene Anzahl von Millisekunden von der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>-Eigenschaft.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Zur Verwendung dieser Funktionen müssen Sie den Begrüßungsbildschirm hinzufügen, um die Anwendung mithilfe der **Projekt-Designer** (welche die `My.Application.MinimumSplashScreenDisplayTime` auf zwei Sekunden), oder legen Sie die `My.Application.MinimumSplashScreenDisplayTime` -Eigenschaft in einer Methode, die überschreibt, die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>oder <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>Methode.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> Ermöglicht es einem Designer, Code auszugeben, die den Begrüßungsbildschirm initialisiert.  
  
         Standardmäßig bewirkt diese Methode nichts. Wenn Sie einen Begrüßungsbildschirm für die Anwendung auswählen die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **Projekt-Designer**, überschreibt der Designer die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>Methode mit einer Methode, die festlegt die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>Eigenschaft, um eine neue Instanz des Formulars Begrüßungsbildschirm.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>  
  
2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A> Stellt einen Erweiterungspunkt für das Auslösen der `Startup` Ereignis. Starten der Anwendung wird beendet, wenn diese Funktion gibt `False`.  
  
     Standardmäßig löst diese Methode das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>Ereignis.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> Wenn der Ereignishandler setzt der @System.ComponentModel.CancelEventArgs.Cancel -Eigenschaft des Ereignisarguments auf `True`, gibt die Methode zurück `False` zum Abbrechen der Start der Anwendung.  
  
3.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A> Bildet die Grundlage für bei der Anwendung bereit ist ausgeführt, nachdem die Initialisierung abgeschlossen ist.  
  
     Standardmäßig, bevor er in der Windows Forms-Nachrichtenschleife wird diese Methode ruft die `OnCreateMainForm` (zum Hauptformular der Anwendung zu erstellen) und `HideSplashScreen` (zum Schließen des Begrüßungsbildschirms) Methoden:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> Bietet eine Möglichkeit für einen Designer, Code auszugeben, die das Hauptformular initialisiert.  
  
         Standardmäßig bewirkt diese Methode nichts. Jedoch bei der Auswahl ein Hauptformular für die Anwendung in der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **Projekt-Designer**, überschreibt der Designer die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>Methode mit einer Methode, die festlegt die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>Eigenschaft, um eine neue Instanz des Hauptformulars.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A> Wenn die Anwendung einen Begrüßungsbildschirm definiert und diese geöffnet ist, schließt diese Methode den Begrüßungsbildschirm.  
  
         Standardmäßig schließt diese Methode den Begrüßungsbildschirm.  
  
4.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> Bietet eine Möglichkeit zum Anpassen, wie eine Einzelinstanz-Anwendung verhält, wenn eine andere Instanz der Anwendung gestartet wird.  
  
     Standardmäßig löst diese Methode das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>Ereignis.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
  
5.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A> Stellt einen Erweiterungspunkt für das Auslösen der `Shutdown` Ereignis. Diese Methode wird nicht ausgeführt, wenn in der Anwendung eine nicht behandelte Ausnahme auftritt.  
  
     Standardmäßig löst diese Methode das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>Ereignis.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
  
6.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A> Ausgeführt, wenn eine nicht behandelte Ausnahme in einer der oben aufgeführten Methoden auftritt.  
  
     Standardmäßig löst diese Methode das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>Ereignis, solange kein Debugger angefügt ist und die Anwendung wird die `UnhandledException` Ereignis.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
  
 Wenn die Anwendung eine Einzelinstanz-Anwendung ist und die Anwendung bereits ausgeführt wird, ruft die nachfolgende Instanz der Anwendung die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>Methode auf der ursprünglichen Instanz von der Anwendung und wird dann beendet.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>  
  
 Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>Konstruktor ruft die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>-Eigenschaft bestimmt die Text-Rendering-Engine für die Formulare der Anwendung verwendet.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> </xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> In der Standardeinstellung die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>-Eigenschaft gibt `False`, gibt an, dass das GDI-Text-Renderingmodul verwendet werden, dies ist die Standardeinstellung in [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)].</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> Sie können außer Kraft setzen der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>-Eigenschaft zum Zurückgeben von `True`, gibt an, dass das GDI +-Text-Renderingmodul verwendet werden, dies ist die Standardeinstellung in Visual Basic .NET 2002 und Visual Basic .NET 2003.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>  
  
## <a name="configuring-the-application"></a>Konfigurieren der Anwendung  
 Als Teil der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Anwendungsmodell, die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>Klasse bietet geschützte Eigenschaften für die Konfiguration der Anwendung.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Diese Eigenschaften sollten im Konstruktor der implementierenden Klasse festgelegt werden.  
  
 In einem Windows Forms-Projekt standardmäßig die **Projekt-Designer** Code zum Festlegen der Eigenschaften mit den Einstellungen des Designers erstellt. Die Eigenschaften werden verwendet, nur, wenn die Anwendung gestartet wird. Sie festlegen, nachdem die Anwendung gestartet hat keine Auswirkung.  
  
|Eigenschaft|Bestimmt|Im Bereich "Anwendung" des Projekt-Designers festlegen|  
|---|---|---|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Gibt an, ob die Anwendung als einzelne Instanz oder Mehrfachinstanz-Anwendung ausgeführt wird.|**Einzelinstanz-Anwendung machen** das Kontrollkästchen|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Wenn die Anwendung visuelle Stile, die mit Windows XP übereinstimmen verwendet werden.|**Visuelle XP-Stile aktivieren** das Kontrollkästchen|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Wenn Anwendung beim Beenden der Anwendung automatisch Anwendung Benutzer Einstellungen Änderungen gespeichert.|**My.Settings beim Herunterfahren speichern** das Kontrollkästchen|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|Was bewirkt, dass die Anwendung beendet werden, z. B. wenn das Startformular geschlossen wird, oder wenn das letzte Formular geschlossen.|**Modus für das Herunterfahren** Liste|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Übersicht über das Visual Basic-Anwendungsmodell](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)   
 [Seite „Anwendung“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)
