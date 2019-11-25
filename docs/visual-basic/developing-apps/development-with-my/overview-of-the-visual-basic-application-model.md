---
title: Übersicht über das Visual Basic-Anwendungsmodell
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: aa47304cf2bded93bdb95ffe7dfa35bb37d9a643
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976458"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Übersicht über das Visual Basic-Anwendungsmodell

Visual Basic bietet ein klar definiertes Modell zum Steuern des Verhaltens von Windows Forms Anwendungen: das Visual Basic Anwendungsmodell. Dieses Modell enthält Ereignisse für die Handhabung des Starts und herunter Fahrens der Anwendung sowie für Ereignisse zum Abfangen von Ausnahme Fehlern. Es bietet auch Unterstützung für die Entwicklung von Einzelinstanzanwendungen. Das Anwendungsmodell ist erweiterbar, sodass Entwickler, die mehr Kontrolle benötigen, ihre über schreibbaren Methoden anpassen können.  
  
## <a name="uses-for-the-application-model"></a>Verwendungszwecke für das Anwendungsmodell  

 Eine typische Anwendung muss Aufgaben ausführen, wenn Sie gestartet und heruntergefahren wird. Beispielsweise kann die Anwendung beim Starten einen Begrüßungsbildschirm anzeigen, Datenbankverbindungen herstellen, einen gespeicherten Zustand laden usw. Wenn die Anwendung heruntergefahren wird, kann Sie Datenbankverbindungen schließen, den aktuellen Zustand speichern usw. Außerdem kann die Anwendung bestimmten Code ausführen, wenn die Anwendung unerwartet heruntergefahren wird, z. b. während einer nicht behandelten Ausnahme.  
  
 Das Visual Basic-Anwendungsmodell erleichtert das Erstellen einer *Einzelinstanzanwendung* . Eine Einzelinstanzanwendung unterscheidet sich von einer normalen Anwendung darin, dass jeweils nur eine Instanz der Anwendung ausgeführt werden kann. Der Versuch, eine andere Instanz einer Einzelinstanzanwendung zu starten, führt dazu, dass die ursprüngliche Instanz benachrichtigt wird – mithilfe des `StartupNextInstance` Ereignisses –, dass ein weiterer Startversuch durchgeführt wurde. Die Benachrichtigung enthält die Befehlszeilenargumente der nachfolgenden Instanz. Die nachfolgende Instanz der Anwendung wird dann geschlossen, bevor eine Initialisierung erfolgen kann.  
  
 Eine Einzelinstanzanwendung wird gestartet und überprüft, ob es sich um die erste Instanz oder eine nachfolgende Instanz der Anwendung handelt:  
  
- Wenn es sich um die erste Instanz handelt, wird Sie wie üblich gestartet.  
  
- Jeder nachfolgende Versuch zum Starten der Anwendung, während die erste Instanz ausgeführt wird, führt zu einem sehr unterschiedlichen Verhalten. Der nachfolgende Versuch benachrichtigt die erste Instanz über die Befehlszeilenargumente und beendet diese sofort. Die erste Instanz behandelt das `StartupNextInstance` Ereignis, um zu bestimmen, was die Befehlszeilenargumente der nachfolgenden Instanz waren, und wird weiterhin ausgeführt.  
  
     Dieses Diagramm zeigt, wie eine nachfolgende Instanz die erste Instanz signalisiert:  
  
     ![Diagramm, das ein einzelnes instanzanwendungsbild anzeigt.](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 Wenn Sie das `StartupNextInstance`-Ereignis behandeln, können Sie steuern, wie sich die Einzelinstanzanwendung verhält. Beispielsweise wird Microsoft Outlook in der Regel als Einzelinstanzanwendung ausgeführt. Wenn Outlook ausgeführt wird und Sie versuchen, Outlook erneut zu starten, wird der Fokus auf die ursprüngliche Instanz verlagert, es wird jedoch keine andere Instanz geöffnet.  
  
## <a name="events-in-the-application-model"></a>Ereignisse im Anwendungsmodell  

 Im Anwendungsmodell sind folgende Ereignisse zu finden:  
  
- **Anwendungsstart**. Die Anwendung löst das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>-Ereignis aus, wenn es gestartet wird. Durch die Behandlung dieses Ereignisses können Sie Code hinzufügen, der die Anwendung initialisiert, bevor das Hauptformular geladen wird. Das `Startup` Ereignis ermöglicht auch das Abbrechen der Ausführung der Anwendung während dieser Phase des Start Prozesses, falls gewünscht.  
  
     Sie können die Anwendung so konfigurieren, dass ein Begrüßungsbildschirm angezeigt wird, während der Startcode der Anwendung ausgeführt wird. Standardmäßig wird der Begrüßungsbildschirm vom Anwendungsmodell unterdrückt, wenn entweder das Befehlszeilenargument `/nosplash` oder `-nosplash` verwendet wird.  
  
- **Einzelinstanzanwendungen**. Das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>-Ereignis wird ausgelöst, wenn eine nachfolgende Instanz einer Einzelinstanzanwendung gestartet wird. Das-Ereignis übergibt die Befehlszeilenargumente der nachfolgenden Instanz.  
  
- **Nicht behandelte Ausnahmen**. Wenn die Anwendung auf eine nicht behandelte Ausnahme stößt, löst Sie das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>-Ereignis aus. Der Handler für dieses Ereignis kann die Ausnahme untersuchen und bestimmen, ob die Ausführung fortgesetzt werden soll.  
  
     Das `UnhandledException`-Ereignis wird in einigen Fällen nicht ausgelöst. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
- **Netzwerkkonnektivitätsänderungen**. Wenn die Netzwerkverfügbarkeit des Computers geändert wird, löst die Anwendung das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>-Ereignis aus.  
  
     Das `NetworkAvailabilityChanged`-Ereignis wird in einigen Fällen nicht ausgelöst. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
- Die **Anwendung wurde heruntergefahren**. Die Anwendung stellt das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> Ereignis bereit, um zu signalisieren, wann das Herunterfahren beendet wird. In diesem Ereignishandler können Sie sicherstellen, dass die Vorgänge, die Ihre Anwendung ausführen muss – schließen und speichern, z. b. –, abgeschlossen sind. Sie können Ihre Anwendung so konfigurieren, dass Sie heruntergefahren wird, wenn das Hauptformular geschlossen wird, oder nur Herunterfahren, wenn alle Formulare geschlossen werden.  
  
## <a name="availability"></a>Verfügbarkeit  

 Standardmäßig ist das Visual Basic Anwendungsmodell für Windows Forms Projekte verfügbar. Wenn Sie die Anwendung so konfigurieren, dass ein anderes Start Objekt verwendet wird, oder wenn Sie den Anwendungscode mit einem benutzerdefinierten `Sub Main`starten, muss dieses Objekt bzw. diese Klasse möglicherweise eine Implementierung der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>-Klasse zur Verwendung des Anwendungs Modells bereitstellen. Informationen zum Ändern des Start Objekts finden Sie unter [Seite "Anwendung", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Erweitern des Visual Basic-Anwendungsmodells](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
