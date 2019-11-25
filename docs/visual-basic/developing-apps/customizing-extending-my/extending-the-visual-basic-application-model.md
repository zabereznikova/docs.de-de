---
title: Erweitern des Visual Basic-Anwendungsmodells
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: 46c18ab540c90c4147514685c2acc824755b435f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976865"
---
# <a name="extending-the-visual-basic-application-model"></a>Erweitern des Visual Basic-Anwendungsmodells

Sie können dem Anwendungsmodell Funktionalität hinzufügen, indem Sie die `Overridable` Member der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>-Klasse überschreiben. Mit dieser Technik können Sie das Verhalten des Anwendungs Modells anpassen und Aufrufe ihrer eigenen Methoden hinzufügen, während die Anwendung gestartet und heruntergefahren wird.

## <a name="visual-overview-of-the-application-model"></a>Visuelle Übersicht über das Anwendungsmodell

In diesem Abschnitt wird die Abfolge von Funktionsaufrufen im Visual Basic Anwendungsmodell visuell dargestellt. Im nächsten Abschnitt wird der Zweck der einzelnen Funktionen ausführlich beschrieben.

Die folgende Abbildung zeigt die Aufruf Sequenz des Anwendungs Modells in einer normalen Visual Basic Windows Forms Anwendung. Die Sequenz wird gestartet, wenn die `Sub Main` Prozedur die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>-Methode aufruft.

![Diagramm, das die Anwendungsmodell-Rückruf Sequenz anzeigt.](./media/extending-the-visual-basic-application-model/application-model-call-sequence.gif)

Das Visual Basic-Anwendungsmodell stellt auch das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>-und <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>-Ereignis bereit. Die folgende Grafik zeigt den Mechanismus zum Erhöhen dieser Ereignisse.

![Diagramm, das die OnStartupNextInstance-Methode anzeigt, die das StartupNextInstance-Ereignis aufhebt.](./media/extending-the-visual-basic-application-model/raise-startupnextinstance-event.gif)

![Diagramm, das die onunshanddexception-Methode anzeigt, die das unlenker-Ereignis ausgelöst hat.](./media/extending-the-visual-basic-application-model/raise-unhandledexception-event.gif)

## <a name="overriding-the-base-methods"></a>Überschreiben der Basis Methoden

Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>-Methode definiert die Reihenfolge, in der die `Application` Methoden ausgeführt werden. Standardmäßig ruft die `Sub Main` Prozedur für eine Windows Forms Anwendung die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>-Methode auf.

Wenn es sich bei der Anwendung um eine normale Anwendung (multiinstanzanwendung) oder die erste Instanz einer Einzelinstanzanwendung handelt, führt die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>-Methode die `Overridable` Methoden in der folgenden Reihenfolge aus:

1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> Standardmäßig legt diese Methode die visuellen Stile, Textanzeige Stile und den aktuellen Prinzipal für den Haupt Anwendungs Thread fest (wenn die Anwendung die Windows-Authentifizierung verwendet) und ruft `ShowSplashScreen` auf, wenn weder `/nosplash` noch `-nosplash` als Befehlszeilenargument verwendet wird.

     Die Startsequenz der Anwendung wird abgebrochen, wenn diese Funktion `False` zurückgibt. Dies kann hilfreich sein, wenn es Situationen gibt, in denen die Anwendung nicht ausgeführt werden soll.

     Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>-Methode ruft die folgenden Methoden auf:

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Bestimmt, ob für die Anwendung ein Begrüßungsbildschirm definiert ist. wenn dies der Fall ist, wird der Begrüßungsbildschirm in einem separaten Thread angezeigt.

         Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>-Methode enthält den Code, der den Begrüßungsbildschirm für mindestens die in der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>-Eigenschaft angegebene Anzahl von Millisekunden anzeigt. Um diese Funktion verwenden zu können, müssen Sie der Anwendung den Begrüßungsbildschirm mit dem **Projekt-Designer** hinzufügen (der die `My.Application.MinimumSplashScreenDisplayTime`-Eigenschaft auf zwei Sekunden festlegt), oder Sie können die `My.Application.MinimumSplashScreenDisplayTime`-Eigenschaft in einer Methode festlegen, die die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> oder <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>-Methode überschreibt. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> Ermöglicht es einem Designer, Code auszugeben, der den Begrüßungsbildschirm initialisiert.

         Standardmäßig führt diese Methode keine Aktion aus. Wenn Sie im Visual Basic **Projekt-Designer**einen Begrüßungsbildschirm für die Anwendung auswählen, überschreibt der Designer die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>-Methode mit einer Methode, die die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>-Eigenschaft auf eine neue Instanz des Begrüßungsbildschirm Formulars festlegt.

2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A> Stellt einen Erweiterbarkeits Punkt zum Erhöhen des `Startup` Ereignisses bereit. Die Startsequenz der Anwendung wird beendet, wenn diese Funktion `False` zurückgibt.

     Standardmäßig löst diese Methode das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>-Ereignis aus. Wenn der Ereignishandler die <xref:System.ComponentModel.CancelEventArgs.Cancel>-Eigenschaft des Ereignis Arguments auf `True` festlegt, gibt die Methode `False` zurück, um den Start der Anwendung abzubrechen.

3. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A> Stellt den Ausgangspunkt für den Start der Hauptanwendung bereit, um die Ausführung zu starten, nachdem die Initialisierung abgeschlossen wurde.

     Standardmäßig ruft diese Methode vor dem Eintritt in die Windows Forms Message-Schleife die `OnCreateMainForm` auf (um das Hauptformular der Anwendung zu erstellen), und `HideSplashScreen` (um den Begrüßungsbildschirm zu schließen):

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> Bietet einem Designer die Möglichkeit, Code auszugeben, der das Hauptformular initialisiert.

         Standardmäßig führt diese Methode keine Aktion aus. Wenn Sie jedoch im Visual Basic **Projekt-Designer**ein Hauptformular für die Anwendung auswählen, überschreibt der Designer die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>-Methode mit einer Methode, die die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>-Eigenschaft auf eine neue Instanz des Haupt Formulars festlegt.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A> Wenn für die Anwendung ein Begrüßungsbildschirm definiert und geöffnet ist, schließt diese Methode den Begrüßungsbildschirm.

         Standardmäßig schließt diese Methode den Begrüßungsbildschirm.

4. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> Bietet eine Möglichkeit, die Art und Weise anzupassen, wie sich eine Einzelinstanzanwendung verhält, wenn eine andere Instanz der Anwendung gestartet wird.

     Standardmäßig löst diese Methode das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>-Ereignis aus.

5. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A> Stellt einen Erweiterbarkeits Punkt zum Erhöhen des `Shutdown` Ereignisses bereit. Diese Methode wird nicht ausgeführt, wenn eine nicht behandelte Ausnahme in der Hauptanwendung auftritt.

     Standardmäßig löst diese Methode das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>-Ereignis aus.

6. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A> Wird ausgeführt, wenn in einer der oben aufgeführten Methoden eine nicht behandelte Ausnahme auftritt.

     Standardmäßig löst diese Methode das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>-Ereignis aus, solange kein Debugger angefügt ist und die Anwendung das `UnhandledException`-Ereignis verarbeitet.

 Wenn die Anwendung eine Einzelinstanzanwendung ist und die Anwendung bereits ausgeführt wird, ruft die nachfolgende Instanz der Anwendung die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>-Methode für die ursprüngliche Instanz der Anwendung auf und wird dann beendet.

 Der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)>-Konstruktor ruft die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>-Eigenschaft auf, um zu bestimmen, welche textrenderingengine für die Anwendungs Formulare verwendet werden soll. Standardmäßig gibt die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>-Eigenschaft `False`zurück, die angibt, dass das GDI-textrenderingmodul verwendet werden soll. Dies ist die Standardeinstellung in Visual Basic 2005 und höheren Versionen. Sie können die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>-Eigenschaft überschreiben, um `True`zurückzugeben. Dies bedeutet, dass das GDI+-textrenderingmodul verwendet wird. Dies ist die Standardeinstellung in Visual Basic .NET 2002 und Visual Basic .NET 2003.

## <a name="configuring-the-application"></a>Konfigurieren der Anwendung

 Im Rahmen des Visual Basic Anwendungs Modells stellt die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>-Klasse geschützte Eigenschaften bereit, die die Anwendung konfigurieren. Diese Eigenschaften sollten im Konstruktor der implementierenden Klasse festgelegt werden.

 In einem Standard Windows Forms Projekt erstellt der **Projekt-Designer** Code, um die Eigenschaften mit den Designer Einstellungen festzulegen. Die Eigenschaften werden nur verwendet, wenn die Anwendung gestartet wird. Wenn Sie diese nach dem Start der Anwendung festlegen, hat dies keine Auswirkungen.

|property|Bestimmt|Festlegen im Anwendungsbereich des Projekt-Designers|
|---|---|---|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|Gibt an, ob die Anwendung als Einzelinstanzanwendung oder als Anwendung mit mehreren Instanzen ausgeführt wird.|Kontrollkästchen zum **Erstellen einer einzelnen Instanz**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|, Wenn die Anwendung visuelle Stile verwendet, die mit Windows XP in Einklang stehen.|**Aktivieren von visuellen XP-Stilen** (Kontrollkästchen)|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|, Wenn die Anwendung die Benutzereinstellungen der Anwendung automatisch speichert, wenn die Anwendung beendet wird.|Aktivieren des Kontrollkästchens **meine Einstellungen beim Herunterfahren speichern**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|Was bewirkt, dass die Anwendung beendet wird, z. b. wenn das Start Formular geschlossen wird oder wenn das letzte Formular geschlossen wird.|Liste der **herunter Fahr Modus**|

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- [Übersicht über das Visual Basic-Anwendungsmodell](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
- [Seite „Anwendung“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
