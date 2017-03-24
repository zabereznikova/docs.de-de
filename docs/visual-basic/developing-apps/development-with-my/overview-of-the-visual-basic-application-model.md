---
title: "Übersicht über das Visual Basic-Anwendungsmodell | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Application object, Visual Basic application model
- Visual Basic application model
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
caps.latest.revision: 30
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 0925bb102c148480d82128b91cbf1762de24e7ec
ms.lasthandoff: 03/13/2017

---
# <a name="overview-of-the-visual-basic-application-model"></a>Übersicht über das Visual Basic-Anwendungsmodell
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]bietet eine klar definierte Modell zur Steuerung des Verhaltens der Windows Forms-Anwendung: die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Anwendungsmodell. Dieses Modell umfasst Ereignisse für der Anwendungsverzeichnis starten und Herunterfahren sowie Ereignisse zum Abfangen von nicht behandelten Ausnahmen behandeln. Es bietet auch Unterstützung für die Entwicklung von Einzel-Instanz-Anwendungen. Das Anwendungsmodell ist erweiterbar, sodass Entwickler, die mehr Kontrolle benötigen die überschreibbaren Methoden anpassen können.  
  
## <a name="uses-for-the-application-model"></a>Verwendet für das Anwendungsmodell  
 Eine typische Anwendung muss Aufgaben auszuführen, wenn er gestartet und beendet. Z. B. beim Systemstart, kann die Anwendung anzeigen eines Begrüßungsbildschirms, stellen Datenbankverbindungen, laden einen gespeicherten Zustand, usw. Wenn die Anwendung heruntergefahren wird, kann es Datenbankverbindungen zu schließen, Speichern des aktuellen Zustands, usw. Darüber hinaus kann die Anwendung speziellen Code ausführen, wenn die Anwendung beendet wird unten unerwartet, z. B. während einer nicht behandelten Ausnahme.  
  
 Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Anwendungsmodell erleichtert das Erstellen einer *Einzelinstanz-* Anwendung. Eine Einzelinstanz-Anwendung unterscheidet sich von einer normalen Anwendung in, das nur eine Instanz der Anwendung zu einem Zeitpunkt ausgeführt werden kann. Versuch, eine andere Instanz eine Einzelinstanz-Anwendung zu starten, die in der ursprünglichen Instanz benachrichtigt wird führt – von der `StartupNextInstance` Ereignis –, die Einführung wurde versucht. Die Benachrichtigung umfasst die nachfolgende Instanz verwendeten Befehlszeilenargumente. Die nachfolgende Instanz der Anwendung wird dann geschlossen, bevor eine Initialisierung erfolgen kann.  
  
 Eine Einzelinstanz-Anwendung startet und prüft, ob sie die erste Instanz oder eine nachfolgende Instanz der Anwendung:  
  
-   Wenn sie die erste Instanz ist, wird wie gewohnt.  
  
-   Jedem nachfolgenden Versuch, die Anwendung zu starten, während die erste Instanz ausgeführt wird, führt zu sehr unterschiedliches Verhalten. Die nachfolgende Instanz benachrichtigt die erste Instanz über die Befehlszeilenargumente und dann sofort beendet. Die erste Instanz verarbeitet das `StartupNextInstance` Ereignis, um zu ermitteln, was die nachfolgende Instanz verwendeten Befehlszeilenargumente wurden weiterhin ausgeführt.  
  
     Die folgende Abbildung zeigt, wie eine nachfolgende Instanz die erste Instanz benachrichtigt.  
  
     ![Einzelne Instanz Anwendungsabbild](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 Durch das Behandeln der `StartupNextInstance` -Ereignis, können Sie steuern, wie die Einzelinstanz-Anwendung verhält. Microsoft Outlook wird z. B. in der Regel als Einzelinstanz-Anwendung. Wenn Outlook ausgeführt wird und Sie versuchen, starten Outlook erneut, Fokus auf der ursprünglichen Instanz, aber einer anderen Instanz wird nicht geöffnet.  
  
## <a name="events-in-the-application-model"></a>Ereignisse im Anwendungsmodell  
 Die folgenden Ereignisse sind im Anwendungsmodell verfügbar:  
  
-   **Beim Start der Anwendung**. Die Anwendung löst die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>Ereignis beim Start.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> Dieses Ereignis wird behandelt, können Sie Code hinzufügen, die die Anwendung initialisiert, bevor das Hauptformular geladen wird. Die `Startup` Ereignis wird auch zum Abbrechen der Ausführung der Anwendung in dieser Phase des Startvorgangs, bietet bei Bedarf.  
  
     Sie können konfigurieren, dass die Anwendung ein Begrüßungsbildschirm angezeigt, während des Startvorgangs ausgeführt wird. Standardmäßig unterdrückt den Begrüßungsbildschirm Bildschirm, wenn entweder der `/nosplash` oder `-nosplash` Befehlszeilenargument verwendet wird.  
  
-   **Einzelinstanz-Applikationen**. Das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>-Ereignis wird ausgelöst, wenn eine nachfolgende Instanz einer Einzelinstanz-Anwendung gestartet wird.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance> Das Ereignis übergibt die Befehlszeilenargumente für die nachfolgende Instanz.  
  
-   **Nicht behandelte Ausnahmen**. Wenn die Anwendung eine nicht behandelte Ausnahme auftritt, löst es das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>Ereignis.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> Der Handler für dieses Ereignis kann die Ausnahme untersuchen und bestimmen, ob die Ausführung fortgesetzt werden.  
  
     Die `UnhandledException` Ereignis wird unter Umständen nicht ausgelöst. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>  
  
-   **Netzwerkkonnektivität Änderungen**. Wenn die Verfügbarkeit des Netzwerks des Computers geändert wird, löst die Anwendung die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>Ereignis.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
  
     Die `NetworkAvailabilityChanged` Ereignis wird unter Umständen nicht ausgelöst. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>  
  
-   **Herunterfahren der Anwendung**. Die Anwendung bietet die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>Ereignis, das signalisiert wird, wenn er beendet wird.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> In diesem Fall Handler auf, Sie können sicherstellen, dass die erforderlichen Vorgänge ausführen, schließen und speichern, z. B. – abgeschlossen sind. Sie können konfigurieren, dass die Anwendung heruntergefahren wird, wenn das Hauptformular geschlossen wird oder nur, wenn alle Formulare schließen heruntergefahren.  
  
## <a name="availability"></a>Verfügbarkeit  
 In der Standardeinstellung die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Anwendungsmodell für Windows Forms-Projekte verfügbar ist. Wenn Sie die Anwendung zur Verwendung eines anderen Startobjekts konfigurieren oder den Anwendungscode mit einem benutzerdefinierten `Sub Main`, dieses Objekt oder diese Klasse eine Implementierung bereitstellen müssen möglicherweise die <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>Klasse, um das Anwendungsmodell verwenden.</xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> Informationen zum Ändern des Startobjekts finden Sie unter [Anwendungsseite, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Erweitern des Visual Basic-Anwendungsmodells](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
