---
title: Übersicht über das Visual Basic-Anwendungsmodell
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
ms.openlocfilehash: 0144c92e01e617081ae05003e6a7175c63166891
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622795"
---
# <a name="overview-of-the-visual-basic-application-model"></a>Übersicht über das Visual Basic-Anwendungsmodell
Visual Basic bietet ein klar definiertes Modell zur Steuerung des Verhaltens von Windows Forms-Anwendungen: das Visual Basic-Anwendungsmodell. Dieses Modell enthält Ereignisse für die Behandlung von der Anwendung starten und Herunterfahren, als auch Ereignisse für das Abfangen von nicht behandelten Ausnahmen. Darüber hinaus Unterstützung für die Entwicklung von Einzel-Instanz-Anwendungen. Das Anwendungsmodell ist erweiterbar und, damit Entwickler, die mehr Kontrolle benötigen die überschreibbaren Methoden anpassen können.  
  
## <a name="uses-for-the-application-model"></a>Verwendet für das Anwendungsmodell  
 Eine typische Anwendung muss Aufgaben auszuführen, wenn er gestartet und beendet. Z. B. beim Starten, kann die Anwendung einen Begrüßungsbildschirm anzuzeigen, stellen Verbindungen mit der Datenbank, einen gespeicherten Zustand zu laden, usw. Beim Herunterfahren der Anwendungs können Datenbankverbindungen zu schließen, den aktuellen Zustand zu speichern, und so weiter. Darüber hinaus kann die Anwendung bestimmten Code ausführen, wenn die Anwendung beendet wird nach-unten-unerwartet, z. B. während einer nicht behandelten Ausnahme.  
  
 Das Visual Basic-Anwendungsmodell erleichtert Ihnen die Erstellung einer *Einzelinstanz-* Anwendung. Eine einzelinstanzanwendung unterscheidet sich von in, das eine normale Anwendung nur eine Instanz der Anwendung zu einem Zeitpunkt ausgeführt werden kann. Versuch um eine andere Instanz von einer einzelinstanzanwendung zu starten, führt zu der ursprünglichen Instanz, die benachrichtigt wird, von der `StartupNextInstance` Ereignis –, die von einem anderen Start-es wurde versucht. Die Benachrichtigung enthält die Befehlszeilenargumente der nachfolgenden-Instanz. Anschließend wird die nachfolgende Instanz der Anwendung geschlossen, bevor eine Initialisierung erfolgen kann.  
  
 Eine einzelinstanzanwendung wird gestartet und überprüft, ob es sich um die erste Instanz oder eine nachfolgende Instanz der Anwendung ist:  
  
- Ist dies die erste Instanz, startet es wie gewohnt.  
  
- Jedem nachfolgender Versuch, die die Anwendung zu starten, wenn die erste Instanz ausgeführt wird, führt zu sehr unterschiedliches Verhalten. Der nächste Versuch benachrichtigt die erste Instanz über die Befehlszeilenargumente, und klicken Sie dann sofort beendet. Die erste Instanz verarbeitet die `StartupNextInstance` Ereignis, um zu bestimmen, was die Befehlszeilenargumente der nachfolgenden Instanz wurden und weiterhin ausgeführt.  
  
     Dieses Diagramm zeigt, wie eine nachfolgende Instanz die erste Instanz signalisiert:  
  
     ![Das Diagramm, das ein Bild zur einzelinstanzanwendung anzeigt.](./media/overview-of-the-visual-basic-application-model/single-instance-application.gif)  
  
 Verarbeiten der `StartupNextInstance` Ereignis können Sie steuern das Verhalten Ihrer Anwendung Einzel-Instanz. Microsoft Outlook wird z. B. in der Regel als Einzelinstanz-Anwendung. Wenn Outlook ausgeführt wird, und Sie versuchen, das Starten von Outlook in diesem Fall wechselt der Fokus mit der ursprünglichen Instanz, aber einer anderen Instanz ist nicht geöffnet werden.  
  
## <a name="events-in-the-application-model"></a>Ereignisse in das Anwendungsmodell  
 Die folgenden Ereignisse werden in das Anwendungsmodell gefunden:  
  
- **Starten der Anwendung**. Die Anwendung löst das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> Ereignis, wenn er startet. Dieses Ereignis wird behandelt, können Sie Code hinzufügen, die die Anwendung initialisiert, bevor das Hauptformular geladen wird. Die `Startup` Ereignis bietet auch zum Abbrechen der Ausführung der Anwendung während dieser Phase des Startvorgangs, falls gewünscht.  
  
     Sie können konfigurieren, dass die Anwendung einen Begrüßungsbildschirm angezeigt wird, während der Code für den Anwendungsstart ausgeführt wird. Standardmäßig unterdrückt den Begrüßungsbildschirm Bildschirm, wenn entweder die `/nosplash` oder `-nosplash` Befehlszeilenargument wird verwendet.  
  
- **Einzel-Instanz-Anwendungen**. Die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> Ereignis wird ausgelöst, wenn eine nachfolgende Instanz einer einzelinstanzanwendung gestartet wird. Das Ereignis übergibt die Befehlszeilenargumente der nachfolgenden-Instanz.  
  
- **Nicht behandelte Ausnahmen**. Wenn die Anwendung eine nicht behandelte Ausnahme auftritt, löst es das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> Ereignis. Ihre Handler für dieses Ereignis kann die Ausnahme untersuchen und bestimmen, ob die Ausführung dort fortzusetzen.  
  
     Die `UnhandledException` Ereignis wird in einigen Fällen nicht ausgelöst. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
- **Netzwerkkonnektivität Änderungen**. Wenn die Verfügbarkeit des Netzwerks des Computers geändert wird, löst die Anwendung aus der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged> Ereignis.  
  
     Die `NetworkAvailabilityChanged` Ereignis wird in einigen Fällen nicht ausgelöst. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
- **Beenden der Anwendung**. Die Anwendung bietet das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> Ereignis, das signalisiert wird, wenn er beendet wird. In diesem Fall Handler auf, Sie können sicherstellen, dass die Vorgänge Ihre Anwendung ausführen muss, schließen und speichern, z. B. – abgeschlossen sind. Sie können konfigurieren, dass die Anwendung heruntergefahren wird, wenn das Hauptformular geschlossen wird oder heruntergefahren, nur wenn alle Formulare zu schließen.  
  
## <a name="availability"></a>Verfügbarkeit  
 Standardmäßig ist das Visual Basic-Anwendungsmodell für Windows Forms-Projekte verfügbar. Wenn Sie die konfigurieren Sie die Anwendung eine andere Startdatei-Objekt verwendet wird, oder starten den Anwendungscode mit einem benutzerdefinierten `Sub Main`, dieses Objekt oder eine Implementierung der Klasse müssen möglicherweise die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Klasse, die das Anwendungsmodell verwendet. Weitere Informationen zum Ändern des Startobjekts, finden Sie unter [Anwendungsseite, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Erweitern des Visual Basic-Anwendungsmodells](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
