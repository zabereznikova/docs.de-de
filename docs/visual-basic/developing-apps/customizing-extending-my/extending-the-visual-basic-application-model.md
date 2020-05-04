---
title: Erweitern des Visual Basic-Anwendungsmodells
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic Application Model, extending
ms.assetid: e91d3bed-4c27-40e3-871d-2be17467c72c
ms.openlocfilehash: 46c18ab540c90c4147514685c2acc824755b435f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976865"
---
# <a name="extending-the-visual-basic-application-model"></a>Erweitern des Visual Basic-Anwendungsmodells

Sie können dem Anwendungsmodell Funktionen hinzufügen, indem Sie die `Overridable`-Member der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>-Klasse überschreiben. Diese Technik ermöglicht es Ihnen, das Verhalten des Anwendungsmodells anzupassen und Aufrufe für Ihre eigenen Methoden hinzuzufügen, wenn die Anwendung gestartet und beendet wird.

## <a name="visual-overview-of-the-application-model"></a>Visuelle Übersicht über das Anwendungsmodell

In diesem Abschnitt wird die Sequenz von Funktionsaufrufen im Visual Basic-Anwendungsmodell visuell dargestellt. Im nächsten Abschnitt werden die Zwecke der einzelnen Funktionen im Detail erläutert.

Auf der folgenden Abbildung sehen Sie die Aufrufsequenz des Anwendungsmodells in einer normalen Windows Forms-Anwendung in Visual Basic. Die Sequenz beginnt, wenn die `Sub Main`-Prozedur die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>-Methode aufruft.

![Diagramm, das die Aufrufsequenz des Anwendungsmodells zeigt](./media/extending-the-visual-basic-application-model/application-model-call-sequence.gif)

Das Anwendungsmodell in Visual Basic stellt auch <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>- und <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>-Ereignisse bereit. In der folgenden Abbildung sehen Sie die Mechanismen, die für das Auslösen dieser Ereignisse verantwortlich sind.

![Abbildung der OnStartupNextInstance-Methode, die das StartupNextInstance-Ereignis auslöst](./media/extending-the-visual-basic-application-model/raise-startupnextinstance-event.gif)

![Abbildung derOnUnhandledException-Methode, die das UnhandledException-Ereignis auslöst](./media/extending-the-visual-basic-application-model/raise-unhandledexception-event.gif)

## <a name="overriding-the-base-methods"></a>Überschreiben der Basismethoden

Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>-Methode definiert die Reihenfolge, in der die `Application`-Methoden ausgeführt werden. Standardmäßig ruft die `Sub Main`-Prozedur für eine Windows Forms-Anwendung die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>-Methode auf.

Wenn es sich bei der Anwendung um eine normale Anwendung (Anwendung mit mehreren Instanzen) handelt oder um die erste Instanz einer Einzelinstanzanwendung, führt die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Run%2A>-Methode die `Overridable`-Methoden in der folgenden Reihenfolge aus:

1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A> Standardmäßig legt diese Methode die visuellen Stile, die Textanzeigestile und den aktuellen Prinzipal für den Hauptanwendungsthread fest (wenn die Anwendung die Windows-Authentifizierung verwendet) und ruft `ShowSplashScreen` auf, wenn weder `/nosplash` noch `-nosplash` als Befehlszeilenargument verwendet werden.

     Die Anwendungsstartsequenz wird abgebrochen, wenn diese Funktion `False` zurückgibt. Dies kann hilfreich sein, wenn es Umstände gibt, in denen die Anwendung nicht ausgeführt werden sollte.

     Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>-Methode ruft die folgenden Methoden auf:

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A> Bestimmt, ob für die Anwendung ein Begrüßungsbildschirm definiert ist. Ist dies der Fall, wird der Begrüßungsbildschirm auf einem separaten Thread angezeigt.

         Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShowSplashScreen%2A>-Methode enthält den Code, der den Begrüßungsbildschirm mindestens für die Dauer an Millisekunden anzeigt, die von der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>-Eigenschaft angegeben werden. Zur Verwendung dieser Funktion müssen Sie den Begrüßungsbildschirm Ihrer Anwendung mithilfe des **Projekt-Designers** hinzufügen (wodurch die `My.Application.MinimumSplashScreenDisplayTime`-Eigenschaft auf zwei Sekunden festgelegt wird) oder die `My.Application.MinimumSplashScreenDisplayTime`-Eigenschaft in einer Methode festlegen, die die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnInitialize%2A>- oder <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>-Methode überschreibt. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MinimumSplashScreenDisplayTime%2A>.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A> Ermöglicht einem Designer, Code auszugeben, der den Begrüßungsbildschirm initialisiert.

         Standardmäßig hat diese Methode keine Auswirkungen. Wenn Sie einen Begrüßungsbildschirm für Ihre Anwendung im **Projekt-Designer** in Visual Basic auswählen, überschreibt der Designer die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateSplashScreen%2A>-Methode mit einer Methode, die die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>-Eigenschaft auf eine neue Instanz des Begrüßungsbildschirmformulars festlegt.

2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartup%2A> Stellt einen Erweiterungspunkt für das Auslösen des `Startup`-Ereignisses bereit. Die Anwendungsstartsequenz wird angehalten, wenn diese Funktion `False` zurückgibt.

     Standardmäßig löst diese Methode das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>-Ereignis aus. Wenn der Ereignishandler die <xref:System.ComponentModel.CancelEventArgs.Cancel>-Eigenschaft des Ereignisarguments auf `True` festlegt, gibt die Methode `False` zurück, um den Anwendungsstart abzubrechen.

3. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnRun%2A> Stellt den Startpunkt bereit, wenn die Ausführung der Hauptanwendung begonnen werden kann, nachdem die Initialisierung abgeschlossen ist.

     Standardmäßig ruft diese Methode die Methoden `OnCreateMainForm` (um das Hauptformular der Anwendung zu erstellen) und `HideSplashScreen` (um den Begrüßungsbildschirm zu schließen) auf, bevor sie die Windows Forms-Nachrichtenschleife startet:

    1. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> Stellt eine Möglichkeit für Designer bereit, Code auszugeben, der das Hauptformular initialisiert.

         Standardmäßig hat diese Methode keine Auswirkungen. Wenn Sie jedoch ein Hauptformular für Ihre Anwendung im **Projekt-Designer** in Visual Basic auswählen, überschreibt der Designer die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>-Methode mit einer Methode, die die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>-Eigenschaft auf eine neue Instanz des Hauptformulars festlegt.

    2. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.HideSplashScreen%2A> Wenn für die Anwendung ein Begrüßungsbildschirm definiert ist und er geöffnet ist, schließt diese Methode den Begrüßungsbildschirm.

         Standardmäßig schließt diese Methode den Begrüßungsbildschirm.

4. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A> Stellt eine Möglichkeit bereit, anzupassen, wie sich eine Einzelinstanzanwendung verhält, wenn eine andere Instanz der Anwendung gestartet wird.

     Standardmäßig löst diese Methode das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>-Ereignis aus.

5. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnShutdown%2A> Stellt einen Erweiterungspunkt für das Auslösen des `Shutdown`-Ereignisses bereit. Diese Methode wird nicht ausgeführt, wenn ein Ausnahmefehler in der Hauptanwendung auftritt.

     Standardmäßig löst diese Methode das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>-Ereignis aus.

6. <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnUnhandledException%2A> Wird ausgeführt, wenn ein Ausnahmefehler in einer der oben aufgeführten Methoden auftritt.

     Standardmäßig löst diese Methode das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>-Ereignis aus, solange der Debugger nicht angefügt ist und die Anwendung das `UnhandledException`-Ereignis behandelt.

 Wenn es sich bei der Anwendung um eine Einzelinstanzanwendung handelt und die Anwendung bereits ausgeführt wird, ruft die anschließende Instanz der Anwendung die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance%2A>-Methode auf der ursprünglichen Instanz der Anwendung auf und wird dann beendet.

 Der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnStartupNextInstance(Microsoft.VisualBasic.ApplicationServices.StartupNextInstanceEventArgs)>-Konstruktor ruft die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>-Eigenschaft auf, um zu bestimmen, welche Textrendering-Engine für die Formulare der Anwendung verwendet werden soll. Standardmäßig gibt die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>-Eigenschaft `False` zurück, was darauf hinweist, dass die GDI-Textrendering-Engine verwendet werden soll. Dabei handelt es sich um den Standardwert für Visual Basic 2005 und höhere Versionen. Sie können die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UseCompatibleTextRendering%2A>-Eigenschaft überschreiben, damit `True` zurückgegeben wird, was darauf hinweist, dass die GDI+-Textrendering-Engine verwendet werden soll. Dabei handelt es sich um den Standardwert für Visual Basic .NET 2002 und Visual Basic .NET 2003.

## <a name="configuring-the-application"></a>Konfigurieren der Anwendung

 Als Teil des Anwendungsmodells in Visual Basic stellt die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>-Klasse geschützte Eigenschaften bereit, die die Anwendung konfigurieren. Diese Eigenschaften sollten im Konstruktor der implementierenden Klasse festgelegt werden.

 In einem Windows Forms-Standardprojekt erstellt der **Projekt-Designer** Code, um die Eigenschaften mit den Einstellungen des Designers festzulegen. Die Eigenschaften werden nur verwendet, wenn die Anwendung gestartet wird. Wenn sie festgelegt werden, nachdem die Anwendung gestartet wurde, hat dies keine Auswirkungen.

|Eigenschaft|Bestimmt…|Einstellung im Anwendungsbereich des Projekt-Designers|
|---|---|---|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.IsSingleInstance%2A>|… ob die Anwendung als Einzelinstanzanwendung oder Anwendung mit mehreren Instanzen ausgeführt wird.|Kontrollkästchen **Einzelinstanzanwendung erstellen**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.EnableVisualStyles%2A>|… ob die Anwendung visuelle Stile verwendet, die denen von Windows entsprechen.|Kontrollkästchen **Visuelle XP-Stile aktivieren**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SaveMySettingsOnExit%2A>|… ob die Anwendung automatisch die Änderungen an Benutzereinstellungen speichert, wenn die Anwendung beendet wird.|Kontrollkästchen **My.Settings beim Herunterfahren speichern**|
|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.ShutdownStyle%2A>|… was dazu führt, dass die Anwendung beendet wird, z. B. wenn das Startformular geschlossen wird oder das letzte Formular geschlossen wird.|Liste **Modus für das Herunterfahren**|

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- [Übersicht über das Visual Basic-Anwendungsmodell](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
- [Seite „Anwendung“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
