---
title: Übersicht über das Visual Basic-Anwendungsmodell
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: 5194810574f594e2c117fef8d8998b7ecebbc981
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591598"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Übersicht über das Visual Basic-Anwendungsmodell
Visual Basic bietet eine klar definierte Modell zur Steuerung des Verhaltens von Windows Forms-Anwendungen: die Visual Basic-Anwendungsmodell. Dieses Modell enthält Ereignisse für der Anwendungsverzeichnis starten und Herunterfahren, sowie Ereignisse für das Abfangen von nicht behandelten Ausnahmen behandeln. Es bietet auch Unterstützung für die Entwicklung von Einzelinstanz-Anwendungen. Das Anwendungsmodell ist erweiterbar, damit Entwickler, die mehr Kontrolle benötigen die überschreibbaren Methoden anpassen können.  
  
## <a name="uses-for-the-application-model"></a>Verwendet für das Anwendungsmodell  
 Eine typische Anwendung muss Aufgaben ausführen, wenn er startet und beendet. Z. B. beim Starten, kann die Anwendung einen Begrüßungsbildschirm anzuzeigen, stellen Verbindungen mit der Datenbank, laden einen gespeicherten Zustand usw. Wenn die Anwendung heruntergefahren wird, kann es Datenbankverbindungen zu schließen, Speichern des aktuellen Zustands, usw. Darüber hinaus kann die Anwendung bestimmten Code ausgeführt, wenn die Anwendung beendet wird unten unerwartet, etwa wie in der eine nicht behandelte Ausnahme.  
  
 Das Visual Basic-Anwendungsmodell erleichtert das Erstellen einer *Einzelinstanz-* Anwendung. Eine einzelinstanzanwendung unterscheidet sich von einer normalen Anwendung in, das nur eine Instanz der Anwendung zu einem Zeitpunkt ausgeführt werden kann. Versuch, eine andere Instanz einer einzelinstanzanwendung starten führt in der ursprünglichen Instanz benachrichtigt – mithilfe von der `StartupNextInstance` Ereignis –, die eine andere Launch-es wurde versucht. Die Benachrichtigung umfasst die nachfolgenden Instanz Befehlszeilenargumente. Die nachfolgende Instanz der Anwendung wird dann geschlossen, bevor eine Initialisierung erfolgen kann.  
  
 Eine einzelinstanzanwendung wird gestartet und überprüft, ob es sich um die erste Instanz oder eine nachfolgende Instanz der Anwendung ist:  
  
-   Ist dies die erste Instanz, startet er wie gewohnt.  
  
-   Jeder nachfolgende Versuch, die Anwendung zu starten, während die erste Instanz ausgeführt wird, führt zu sehr unterschiedlich Verhalten. Der nächste Versuch benachrichtigt die erste Instanz über die Befehlszeilenargumente und dann sofort beendet. Die erste Instanz verarbeitet die `StartupNextInstance` Ereignis, um zu bestimmen, was die nachfolgende Instanz Befehlszeilenargumente wurden, und wird weiterhin ausgeführt.  
  
     Die folgende Abbildung zeigt, wie eine nachfolgende Instanz die erste Instanz signalisiert.  
  
     ![Einzelne Instanz Anwendungsimage](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 Durch Verarbeiten der `StartupNextInstance` -Ereignis können Sie steuern, wie die Einzelinstanz-Anwendung verhält. Microsoft Outlook führt z. B. in der Regel als eine einzelinstanzanwendung; Wenn Outlook ausgeführt wird und Sie versuchen, starten Outlook erneut, wechselt der Fokus mit der ursprünglichen Instanz, jedoch eine andere Instanz wird nicht geöffnet.  
  
## <a name="events-in-the-application-model"></a>Ereignisse in das Anwendungsmodell  
 Die folgenden Ereignisse werden in das Anwendungsmodell gefunden:  
  
-   **Start der Anwendung**. Die Anwendung löst das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> Ereignis, wenn er startet. Durch die Behandlung dieses Ereignisses, können Sie Code hinzufügen, die die Anwendung initialisiert, bevor das Hauptformular geladen wird. Die `Startup` Ereignis bietet auch zum Abbrechen der Ausführung der Anwendung während dieser Phase des Startvorgangs, falls gewünscht.  
  
     Sie können konfigurieren, dass die Anwendung aus, um einen Begrüßungsbildschirm anzuzeigen, während die Anwendungsstartcode ausgeführt wird. Standardmäßig unterdrückt den Begrüßungsbildschirm Bildschirm, wenn entweder die `/nosplash` oder `-nosplash` Befehlszeilenargument verwendet wird.  
  
-   **Einzelinstanz-Anwendungen**. Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> Ereignis wird ausgelöst, wenn eine nachfolgende Instanz einer Einzelinstanz-Anwendung gestartet wird. Das Ereignis übergibt die Befehlszeilenargumente für die nachfolgende Instanz.  
  
-   **Nicht behandelte Ausnahmen**. Wenn die Anwendung eine nicht behandelte Ausnahme auftritt, löst die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> Ereignis. Der Handler für dieses Ereignis kann die Ausnahme untersuchen und bestimmen, ob die Ausführung fortgesetzt werden.  
  
     Die `UnhandledException` Ereignis wird nicht unter bestimmten Umständen. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
-   **Netzwerkkonnektivität Änderungen**. Wenn der Computer netzwerkverfügbarkeit geändert wird, löst die Anwendung die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> Ereignis.  
  
     Die `NetworkAvailabilityChanged` Ereignis wird nicht unter bestimmten Umständen. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
-   **Beenden der Anwendung**. Die Anwendung stellt die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> Ereignis zu signalisieren, wenn es beendet ist. In diesem Ereignis Handler auf, Sie können sicherstellen, dass die Vorgänge für das Ausführen Ihrer Anwendung muss – schließen und speichern, z. B. – abgeschlossen sind. Sie können konfigurieren, dass die Anwendung heruntergefahren wird, wenn das Hauptformular geschlossen wird oder nur, wenn alle Formulare schließen beendet.  
  
## <a name="availability"></a>Verfügbarkeit  
 Standardmäßig wird das Visual Basic-Anwendungsmodell für Windows Forms-Projekte verfügbar. Wenn Sie die Anwendung zur Verwendung eines anderen Startobjekts konfigurieren, oder starten den Code der Anwendung mit einem benutzerdefinierten `Sub Main`, dieses Objekt oder Klasse eine Implementierung bereitstellen müssen möglicherweise die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Klasse, um das Anwendungsmodell verwenden. Informationen zum Ändern des Startobjekts finden Sie unter [Anwendungsseite, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 [Erweitern des Visual Basic-Anwendungsmodells](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
