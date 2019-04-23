---
title: Erweitern des Visual Basic-Anwendungsmodells
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: 6ba3f29ad0ceef7f1ea9d102743df568a32c26c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59320144"
---
# <a name="extending-the-visual-basic-application-model"></a>Erweitern des Visual Basic-Anwendungsmodells
Sie können das Anwendungsmodell Funktionen hinzugefügt, durch das Überschreiben der `Overridable` Mitglied der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Klasse. Dieses Verfahren ermöglicht Ihnen das Anpassen des Verhaltens des Anwendungsmodells und Ihren eigenen Methoden zu aufrufen hinzufügen, wie die Anwendung startet und beendet wird.  
  
## <a name="visual-overview-of-the-application-model"></a>Übersicht über das Anwendungsmodell  
 In diesem Abschnitt werden die Sequenz von Funktionsaufrufen visuell im Visual Basic-Anwendungsmodell. Im nächste Abschnitt werden den Zweck der einzelnen Funktionen im Detail beschrieben.  
  
 Die folgende Grafik zeigt die Aufruffolge für Anwendung-Modell in einer normalen Visual Basic Windows Forms-Anwendung. Die Sequenz beginnt, wenn die `Sub Main` Prozeduraufrufe der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> Methode.  
  
 ![Das Diagramm zeigt die Aufruffolge-Anwendungsmodell.](./media/extending-the-visual-basic-application-model/application-model-call-sequence.gif)  
  
 Das Visual Basic-Anwendungsmodell bietet außerdem die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> und <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> Ereignisse. Die folgende Abbildung zeigt den Mechanismus zum Auslösen von diesen Ereignissen.  
  
 ![Das Diagramm zeigt die OnStartupNextInstance-Methode, die das StartupNextInstance-Ereignis auslöst.](./media/extending-the-visual-basic-application-model/raise-startupnextinstance-event.gif)  
  
 ![Das Diagramm zeigt die OnUnhandledException-Methode, die das UnhandledException-Ereignis auslöst.](./media/extending-the-visual-basic-application-model/raise-unhandledexception-event.gif)  
  
## <a name="overriding-the-base-methods"></a>Überschreiben von Basismethoden  
 Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> Methode definiert die Reihenfolge, in dem die `Application` Methoden ausführen. In der Standardeinstellung die `Sub Main` Prozedur für eine Windows Forms-Anwendung ruft die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> Methode.  
  
 Wenn die Anwendung eine normale Anwendung (Mehrfachinstanz-Anwendung) oder die erste Instanz des eine einzelinstanzanwendung ist die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A> Methode führt die `Overridable` Methoden in der folgenden Reihenfolge:  
  
1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>. Standardmäßig diese Methode legt fest, die visuelle Stile, die Textanzeigestile und die aktuelle Prinzipal für den Hauptthread der Anwendung (sofern die Anwendung Windows-Authentifizierung verwendet wird), und ruft `ShowSplashScreen` Wenn weder `/nosplash` noch `-nosplash` dient als ein Befehlszeilenargument.  
  
     Starten der Anwendung wird abgebrochen, wenn diese Funktion gibt `False`. Dies kann nützlich sein, wenn es gibt Situationen, in denen die Anwendung nicht ausgeführt werden soll.  
  
     Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> Methode ruft die folgenden Methoden:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>. Bestimmt, ob die Anwendung einen Begrüßungsbildschirm definiert wurde, und wenn dies der Fall ist, zeigt den Begrüßungsbildschirm in einem separaten Thread an.  
  
         Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Methode enthält den Code, dem der Begrüßungsbildschirm anzeigt, Bildschirm mindestens für die Anzahl der Millisekunden, die gemäß der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A> Eigenschaft. Um diese Funktion verwenden zu können, müssen Sie den Begrüßungsbildschirm hinzufügen, auf Ihre Anwendung mit der **Projekt-Designer** (welche legt die `My.Application.MinimumSplashScreenDisplayTime` auf zwei Sekunden), oder legen Sie die `My.Application.MinimumSplashScreenDisplayTime` Eigenschaft in einer Methode, die die überschreibt<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> oder <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> Methode. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>. Ermöglicht einem Designer, Code auszugeben, die den Begrüßungsbildschirm initialisiert.  
  
         Standardmäßig führt diese Methode keine Aktion. Bei Auswahl ein Begrüßungsbildschirms für Ihre Anwendung in Visual Basic **Projekt-Designer**, überschreibt der Designer die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> Methode mit einer Methode, die festlegt der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A> Eigenschaft, um eine neue Instanz des Formulars Splash-Bildschirm .  
  
2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A>. Stellt einen Erweiterungspunkt zum Auslösen der `Startup` Ereignis. Starten der Anwendung wird beendet, wenn diese Funktion gibt `False`.  
  
     Standardmäßig löst diese Methode die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> Ereignis. Wenn der Ereignishandler setzt der <xref:System.ComponentModel.CancelEventArgs.Cancel> Eigenschaft des Ereignisarguments auf `True`, gibt die Methode zurück `False` zum Start der Anwendung abbrechen.  
  
3. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A>. Stellt einen Ausgangspunkt für den Fall kann die hauptanwendung damit beginnen, ausgeführt, nachdem die Initialisierung abgeschlossen ist.  
  
     Standardmäßig, bevor in der Windows Forms-Nachrichtenschleife, wird diese Methode ruft die `OnCreateMainForm` (zum Hauptformular der Anwendung zu erstellen) und `HideSplashScreen` (zum Schließen des Begrüßungsbildschirms) Methoden:  
  
    1.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>. Bietet eine Möglichkeit für einen Designer zum Ausgeben von Code, der das Hauptformular initialisiert.  
  
         Standardmäßig führt diese Methode keine Aktion. Allerdings bei der Auswahl einer Hauptformular für Ihre Anwendung in Visual Basic **Projekt-Designer**, überschreibt der Designer die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> Methode mit einer Methode, die festlegt der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> Eigenschaft, um eine neue Instanz des Hauptformulars.  
  
    2.  <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A>. Wenn die Anwendung einen Begrüßungsbildschirm definiert und es geöffnet ist, schließt diese Methode den Begrüßungsbildschirm.  
  
         Standardmäßig schließt diese Methode den Begrüßungsbildschirm.  
  
4. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>. Bietet eine Möglichkeit zum Anpassen, wie eine einzelinstanzanwendung verhält, wenn eine andere Instanz der Anwendung gestartet wird.  
  
     Standardmäßig löst diese Methode die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> Ereignis.  
  
5. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A>. Stellt einen Erweiterungspunkt zum Auslösen der `Shutdown` Ereignis. Diese Methode wird nicht ausgeführt werden, wenn eine nicht behandelte Ausnahme in die Hauptassembly der Anwendung auftritt.  
  
     Standardmäßig löst diese Methode die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> Ereignis.  
  
6. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A>. Ausgeführt, wenn eine unbehandelte Ausnahme in einem der oben aufgeführten Methoden auftritt.  
  
     Standardmäßig löst diese Methode die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> Ereignis solange kein Debugger angefügt ist und die Anwendung ist der Umgang mit den `UnhandledException` Ereignis.  
  
 Wenn die Anwendung ein Einzelinstanz-Anwendung ist und die Anwendung bereits ausgeführt wird, ruft der nachfolgenden Anwendungsinstanz die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> Methode in der ursprünglichen Instanz von der Anwendung und wird dann beendet.  
 
 Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)> Konstruktor ruft die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> Eigenschaft, um zu bestimmen, welche Textwiedergabe-Engine, die für die Formulare der Anwendung verwendet. In der Standardeinstellung die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> -Eigenschaft gibt `False`, gibt an, dass die GDI-Rendering-Engine verwendet werden, dies ist die Standardeinstellung in [!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)]. Sie können außer Kraft setzen der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A> zurückzugebende Eigenschaft `True`, was bedeutet, dass die GDI +-Textwiedergabe-Engine verwendet werden, dies ist die Standardeinstellung in Visual Basic .NET 2002 und Visual Basic .NET 2003.  
  
## <a name="configuring-the-application"></a>Konfigurieren der Anwendung  
 Als Teil der Visual Basic-Anwendungsmodell den <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering> Klasse enthält geschützte Eigenschaften, die die Anwendung zu konfigurieren. Diese Eigenschaften sollten im Konstruktor der implementierenden Klasse festgelegt werden.  
  
 In einem standardmäßigen Windows Forms-Projekt die **Projekt-Designer** Code zum Festlegen der Eigenschaften mit den Einstellungen des Designers erstellt. Die Eigenschaften werden verwendet, nur, wenn die Anwendung gestartet wird. nach dem Starten der Anwendung festlegen, hat keine Auswirkungen.  
  
|Eigenschaft|Bestimmt|Im Bereich "Anwendung" des Projekt-Designers festlegen|  
|---|---|---|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Gibt an, ob die Anwendung als einzelne Instanz oder Mehrfachinstanz-Anwendung ausgeführt wird.|**Einzelinstanzanwendung erstellen** Kontrollkästchen|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|Wenn der Anwendung visuelle Stile, die mit Windows XP übereinstimmen verwendet werden.|**Visuelle XP-Stile aktivieren** Kontrollkästchen|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|Wenn die Anwendung beim Beenden der Anwendung automatisch Benutzer – Änderungen der Anwendung speichert.|**My.Settings beim Herunterfahren speichern** Kontrollkästchen|  
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|Was bewirkt, dass die Anwendung beendet wurde z. B. wenn das Startformular schließt oder wenn das letzte Formular geschlossen wird.|**Modus für das Herunterfahren** Liste|  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- [Übersicht über das Visual Basic-Anwendungsmodell](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
- [Seite „Anwendung“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
