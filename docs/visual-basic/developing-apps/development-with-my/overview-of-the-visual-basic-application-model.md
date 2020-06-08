---
title: Übersicht über das Visual Basic-Anwendungsmodell
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: 46177d0af7e5df767eb8421caf424880baac615e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411726"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Übersicht über das Visual Basic-Anwendungsmodell

Visual Basic bietet mit dem Visual Basic-Anwendungsmodell ein klar definiertes Modell zur Steuerung des Verhaltens von Windows Forms-Anwendungen. Dieses Modell enthält Ereignisse, um den Start und das Herunterfahren der Anwendung zu verarbeiten sowie zum Abfangen von Ausnahmefehlern. Es bietet auch Unterstützung für die Entwicklung von Einzelinstanzanwendungen. Da das Anwendungsmodell zudem erweiterbar ist, können Entwickler, die mehr Kontrolle benötigen, die überschreibbaren Methoden anpassen.  
  
## <a name="uses-for-the-application-model"></a>Verwendungsmöglichkeiten für das Anwendungsmodell  

 In der Regel führt eine Anwendung beim Starten und beim Herunterfahren Aufgaben aus. Beispielsweise kann sie beim Starten einen Begrüßungsbildschirm anzeigen, Datenbankverbindungen herstellen oder einen gespeicherten Zustand laden. Beim Herunterfahren kann die Anwendung etwa Datenbankverbindungen schließen, den aktuellen Zustand speichern usw. Außerdem kann die Anwendung einen bestimmten Code ausführen, wenn sie unerwartet heruntergefahren wird, z. B. bei einem Ausnahmefehler.  
  
 Mithilfe des Visual Basic-Anwendungsmodells können Sie ganz einfach eine *Einzelinstanzanwendung* erstellen. Eine Einzelinstanzanwendung unterscheidet sich von einer normalen Anwendung dadurch, dass jeweils nur eine Instanz der Anwendung ausgeführt werden kann. Der Versuch, eine weitere Instanz einer Einzelinstanzanwendung zu starten, führt dazu, dass die ursprüngliche Instanz mithilfe des Ereignisses `StartupNextInstance` darüber informiert wird, dass ein weiterer Startversuch durchgeführt wurde. Die Benachrichtigung enthält die Befehlszeilenargumente der nachfolgenden Instanz. Bevor eine Initialisierung erfolgen kann, wird die nachfolgende Instanz der Anwendung geschlossen.  
  
 Eine Einzelinstanzanwendung überprüft nach dem Start, ob sie die erste Instanz oder eine nachfolgende Instanz der Anwendung ist:  
  
- Handelt es sich um die erste Instanz, wird die Anwendung wie üblich gestartet.  
  
- Jeder nachfolgende Versuch, die Anwendung während der Ausführung der ersten Instanz zu starten, führt zu einem ganz anderen Verhalten. Die nachfolgende Instanz übergibt die Befehlszeilenargumente an die erste Instanz und wird dann sofort beendet. Die erste Instanz verarbeitet das Ereignis `StartupNextInstance` zur Bestimmung der Befehlszeilenargumente der nachfolgenden Instanz und wird weiter ausgeführt.  
  
     Im folgenden Diagramm wird die Signalübergabe von der nachfolgenden Instanz an die erste Instanz dargestellt:  
  
     ![Diagramm einer Einzelinstanzanwendung](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 Über die Behandlung des Ereignisses `StartupNextInstance` können Sie steuern, wie sich die Einzelinstanzanwendung verhalten soll. Microsoft Outlook wird z. B. in der Regel als Einzelinstanzanwendung ausgeführt. Wenn Sie nun versuchen, Outlook erneut zu starten, obwohl es bereits ausgeführt wird, wechselt der Fokus auf die ursprüngliche Instanz, es wird jedoch keine weitere Instanz geöffnet.  
  
## <a name="events-in-the-application-model"></a>Ereignisse im Anwendungsmodell  

 Folgende Ereignisse können im Anwendungsmodell auftreten:  
  
- **Starten der Anwendung**: Beim Startvorgang löst die Anwendung das Ereignis <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> aus. Bei der Behandlung dieses Ereignisses können Sie Code hinzufügen, durch den die Anwendung vor dem Laden des Hauptformulars initialisiert wird. Über das `Startup`-Ereignis können Sie die Ausführung der Anwendung in dieser Phase des Startvorgangs gegebenenfalls auch abbrechen.  
  
     Sie können die Anwendung so konfigurieren, dass während der Ausführung des Startcodes ein Begrüßungsbildschirm angezeigt wird. Standardmäßig wird der Begrüßungsbildschirm vom Anwendungsmodell unterdrückt, wenn eines der beiden Befehlszeilenargumente `/nosplash` oder `-nosplash` verwendet wird.  
  
- **Einzelinstanzanwendungen**: Wird eine nachfolgende Instanz einer Einzelinstanzanwendung gestartet, wird das Ereignis <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> ausgelöst. Dieses übergibt die Befehlszeilenargumente der nachfolgenden Instanz.  
  
- **Ausnahmefehler**: Bei einem Ausnahmefehler wird das Ereignis <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> ausgelöst. Der Handler für dieses Ereignis kann die Ausnahme untersuchen und entscheiden, ob die Ausführung fortgesetzt werden soll.  
  
     Unter bestimmten Umständen wird das Ereignis `UnhandledException` nicht ausgelöst. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
- **Änderungen der Netzwerkkonnektivität**: Bei Änderungen der Verfügbarkeit des Computernetzwerks wird das Ereignis <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> ausgelöst.  
  
     Unter bestimmten Umständen wird das Ereignis `NetworkAvailabilityChanged` nicht ausgelöst. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
- **Herunterfahren der Anwendung**: Über das Ereignis <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> signalisiert die Anwendung, dass sie gleich heruntergefahren wird. In diesem Ereignishandler können Sie festlegen, dass die erforderlichen Vorgänge (wie z. B. Schließen und Speichern) auch abgeschlossen werden. Sie können die Anwendung so konfigurieren, dass sie beim Schließen des Hauptformulars heruntergefahren wird oder erst dann, wenn alle Formulare geschlossen werden.  
  
## <a name="availability"></a>Verfügbarkeit  

 Das Visual Basic-Anwendungsmodell ist standardmäßig für Windows Forms-Projekte verfügbar. Wenn Sie für die Anwendung ein anderes Startobjekt konfigurieren, oder wenn Sie den Anwendungscode mit einer benutzerdefinierten `Sub Main`-Klasse starten, muss das Objekt bzw. die Klasse möglicherweise eine Implementierung der Klasse <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>bereitstellen, um das Anwendungsmodell verwenden zu können. Informationen zum Ändern des Startobjekts finden Sie unter [Seite „Anwendung“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Erweitern des Visual Basic-Anwendungsmodells](../customizing-extending-my/extending-the-visual-basic-application-model.md)
