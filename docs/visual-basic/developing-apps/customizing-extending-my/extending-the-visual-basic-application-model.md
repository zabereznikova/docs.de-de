---
title: Erweitern des Visual Basic-Anwendungsmodells
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: 64c175216cf21b7947462cf79e4b88ab6fcd6d86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591871"
---
# <a name="extending-the-visual-basic-application-model"></a>Erweitern des Visual Basic-Anwendungsmodells
Sie können das Anwendungsmodell Funktionalität hinzufügen, durch Überschreiben der `Overridable` Mitglied der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Klasse. Bei dieser Technik können Sie das Verhalten des Anwendungsmodells anpassen und Ihre eigenen Methoden zu aufrufen hinzufügen, wie die Anwendung gestartet und heruntergefahren.  
  
## <a name="visual-overview-of-the-application-model"></a>Visuelle Übersicht über das Anwendungsmodell  
 In diesem Abschnitt werden die Sequenz von Funktionsaufrufen visuell in Visual Basic-Anwendungsmodell. Im nächste Abschnitt beschreibt den Zweck der einzelnen Funktionen im Detail.  
  
 Die folgende Abbildung zeigt die Aufrufsequenz des Anwendungsmodells in einer normalen Visual Basic-Windows Forms-Anwendung. Die Sequenz beginnt, wenn die `Sub Main` Prozeduraufrufe der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> Methode.  
  
 ![Visual Basic-Anwendungsmodell &#45; &#45; ausführen](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelrun.gif "VB_ModelRun")  
  
 Das Visual Basic-Anwendungsmodell bietet außerdem die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> und <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> Ereignisse. Der folgenden Grafik wird den Mechanismus zum Auslösen von diesen Ereignissen.  
  
 ![Visual Basic-Anwendungsmodell &#45; &#45; neben Instanz](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_modelnext.gif "VB_ModelNext")  
  
 ![Visual Basic-Anwendungsmodell-nicht behandelte Ausnahme](../../../visual-basic/developing-apps/customizing-extending-my/media/vb_unhandex.gif "VB_UnhandEx")  
  
## <a name="overriding-the-base-methods"></a>Überschreiben von Basismethoden  
 Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> Methode definiert die Reihenfolge, in dem die `Application` Methoden ausführen. Wird standardmäßig die `Sub Main` Prozedur für eine Windows Forms-Anwendung ruft die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> Methode.  
  
 Wenn die Anwendung eine normale Anwendung (multiinstanzbericht) oder der ersten Instanz einer einzelinstanzanwendung ist die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> Methode führt die `Overridable` Methoden in der folgenden Reihenfolge:  
  
1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> Standardmäßig legt diese Methode die visuelle Stile, die Anzeigestile für Text und die aktuellen Prinzipal für den Hauptthread der Anwendung (sofern die Anwendung Windows-Authentifizierung verwendet wird), und ruft `ShowSplashScreen` Wenn weder `/nosplash` noch `-nosplash` dient als ein Befehlszeilenargument.  
  
     Starten der Anwendung wird abgebrochen, wenn diese Funktion gibt `False`. Dies kann nützlich sein, wenn es gibt Situationen, in denen die Anwendung nicht ausgeführt werden soll.  
  
     Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> Methode ruft die folgenden Methoden:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Bestimmt, ob die Anwendung einen Begrüßungsbildschirm definiert wurde, und wenn dies der Fall ist, zeigt den Begrüßungsbildschirm in einem separaten Thread an.  
  
         Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> -Methode enthält den Code, der den Begrüßungsbildschirm anzeigt Bildschirm mindestens für die Anzahl der Millisekunden, die gemäß der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> Eigenschaft. Zur Verwendung dieser Funktionen müssen Sie den Begrüßungsbildschirm hinzufügen, um die Anwendung mit der **Projekt-Designer** (welche die `My.Application.MinimumSplashScreenDisplayTime` auf zwei Sekunden), oder legen Sie die `My.Application.MinimumSplashScreenDisplayTime` Eigenschaft in einer Methode, die die überschreibt<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> oder <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> Methode. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> Ermöglicht einem Designer zum Ausgeben von Code, der den Begrüßungsbildschirm initialisiert.  
  
         Standardmäßig wird diese Methode keine Aktion ausgeführt. Wenn Sie einen Begrüßungsbildschirm für Ihre Anwendung in Visual Basic auswählen **Projekt-Designer**, überschreibt der Designer die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> Methode mit einer Methode, die festlegt der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> Eigenschaft, um eine neue Instanz des Formulars Splash-Bildschirm .  
  
2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A> Stellt einen Erweiterbarkeitspunkt zum Auslösen der `Startup` Ereignis. Starten der Anwendung beendet wird, wenn diese Funktion gibt `False`.  
  
     Standardmäßig löst diese Methode die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> Ereignis. Wenn bei der Ereignishandler die <xref:System.ComponentModel.CancelEventArgs.Cancel> Eigenschaft das Ereignisargument für `True`, gibt die Methode zurück `False` auf den Start der Anwendung "Abbrechen".  
  
3.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A> Stellt den Startpunkt für den Fall kann die Hauptassembly der Anwendung beginnen, ausgeführt, nachdem die Initialisierung erfolgt.  
  
     Standardmäßig, bevor er in der Windows Forms-Nachrichtenschleife wird diese Methode ruft die `OnCreateMainForm` (zum Hauptformular der Anwendung zu erstellen) und `HideSplashScreen` (zum Schließen des Begrüßungsbildschirms) Methoden:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> Bietet eine Möglichkeit für einen Designer zum Ausgeben von Code, der das Hauptformular initialisiert.  
  
         Standardmäßig wird diese Methode keine Aktion ausgeführt. Allerdings bei Auswahl einer Hauptformular für Ihre Anwendung in Visual Basic **Projekt-Designer**, überschreibt der Designer die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> Methode mit einer Methode, die festlegt der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> Eigenschaft, um eine neue Instanz des Hauptformulars.  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A> Wenn die Anwendung hat einen Begrüßungsbildschirm definiert, und er geöffnet ist, schließt diese Methode den Begrüßungsbildschirm.  
  
         Standardmäßig schließt diese Methode den Begrüßungsbildschirm.  
  
4.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> Bietet eine Möglichkeit zum Anpassen, wie eine einzelinstanzanwendung verhält, wenn eine andere Instanz der Anwendung gestartet wird.  
  
     Standardmäßig löst diese Methode die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> Ereignis.  
  
5.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A> Stellt einen Erweiterbarkeitspunkt zum Auslösen der `Shutdown` Ereignis. Diese Methode wird nicht ausgeführt, wenn eine nicht behandelte Ausnahme in die Hauptassembly der Anwendung auftritt.  
  
     Standardmäßig löst diese Methode die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> Ereignis.  
  
6.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A> Ausgeführt, wenn eine nicht behandelte Ausnahme in einer der oben aufgeführten Methoden auftritt.  
  
     Standardmäßig löst diese Methode die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> Ereignis solange kein Debugger angefügt ist und die Anwendung behandelt wird die `UnhandledException` Ereignis.  
  
 Wenn die Anwendung ein Einzelinstanz-Anwendung ist und die Anwendung bereits ausgeführt wird, ruft die nachfolgende Instanz der Anwendung die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> Methode in der ursprünglichen Instanz von der Anwendung, und wird dann beendet.  
 
 Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> Konstruktoraufrufe der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> Eigenschaft, um zu bestimmen, welche Text-Renderingmodul für Formulare der Anwendung verwendet. Wird standardmäßig die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> -Eigenschaft gibt `False`, gibt an, dass das GDI-Text-Renderingmodul verwendet werden, dies ist die Standardeinstellung in [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)]. Sie können außer Kraft setzen die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> -Eigenschaft zum Zurückgeben von `True`, gibt an, dass das GDI +-Text-Renderingmodul verwendet werden, dies ist die Standardeinstellung in Visual Basic .NET 2002 und Visual Basic .NET 2003.  
  
## <a name="configuring-the-application"></a>Konfigurieren der Anwendung  
 Als Teil der Visual Basic-Anwendungsmodell den <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering> Klasse enthält geschützte Eigenschaften, die die Anwendung zu konfigurieren. Diese Eigenschaften sollten im Konstruktor der implementierenden Klasse festgelegt werden.  
  
 In einem Standard-Windows Forms-Projekt die **Projekt-Designer** Code zum Festlegen der Eigenschaften mit den Designer Einstellungen erstellt. Die Eigenschaften werden verwendet, nur, wenn die Anwendung gestartet wird. Sie festlegen, nachdem die Anwendung gestartet hat keine Auswirkungen.  
  
|Eigenschaft|Bestimmt|Einstellung im Anwendungsbereich des Projekt-Designer|  
|---|---|---|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Gibt an, ob die Anwendung als eine Einzelinstanz- oder multiinstanzbericht-Anwendung ausgeführt wird.|**Stellen Sie die Einzelinstanz-Anwendung** Kontrollkästchen|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Wenn die Anwendung visuelle Stile, die mit Windows XP übereinstimmen verwenden.|**Aktivieren Sie visuelle XP-Stile** Kontrollkästchen|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Wenn die Anwendung automatisch Anwendung benutzereinstellungen Änderungen speichert, wenn die Anwendung beendet wird.|**My.Settings beim Herunterfahren speichern** Kontrollkästchen|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|Was bewirkt, dass die Anwendung beendet werden, z. B. wenn die Startformular geschlossen wird oder wenn das letzte Formular geschlossen wird.|**Modus für das Herunterfahren** Liste|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 [Übersicht über das Visual Basic-Anwendungsmodell](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 [Seite „Anwendung“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
