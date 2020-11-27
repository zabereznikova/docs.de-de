---
title: Aktivitätserstellungsoptionen in WF
ms.date: 03/30/2017
ms.assetid: b9061f5f-12c3-47f0-adbe-1330e2714c94
ms.openlocfilehash: e80750b3865a21d072f45b0245ae114660012e66
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289203"
---
# <a name="activity-authoring-options-in-wf"></a>Aktivitätserstellungsoptionen in WF

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] stellt mehrere Optionen zum Erstellen von benutzerdefinierten Aktivitäten bereit. Die richtige Methode zum Erstellen einer bestimmten Aktivität hängt davon ab, welche Laufzeitfunktionen erforderlich sind.  
  
## <a name="deciding-which-base-activity-class-to-use-for-authoring-custom-activities"></a>Festlegen der Basisaktivitätsklasse für das Erstellen von benutzerdefinierten Aktivitäten  

 In der folgenden Tabelle werden die Funktionen aufgeführt, die in den benutzerdefinierten Aktivitätsbasisklassen verfügbar sind.  
  
|Basisaktivitätsklasse|Verfügbare Funktionen|  
|-------------------------|------------------------|  
|<xref:System.Activities.Activity>|Kombiniert Gruppen von vom System bereitgestellten und benutzerdefinierten Aktivitäten in einer zusammengesetzten Aktivität.|  
|<xref:System.Activities.CodeActivity>|Implementiert imperative Funktionalität durch das Bereitstellen einer <xref:System.Activities.CodeActivity%601.Execute%2A>-Methode, die überschrieben werden kann. Bietet außerdem Zugriff auf die Überwachung, Variablen und Argumente.|  
|<xref:System.Activities.NativeActivity>|Stellt alle Funktionen der <xref:System.Activities.CodeActivity> sowie zum Abbrechen der Ausführung einer Aktivität oder einer untergeordneten Aktivität, zur Verwendung von Lesezeichen und zum Planen von Aktivitäten, Aktivitätsaktionen und Funktionen bereit.|  
|<xref:System.Activities.DynamicActivity>|Stellt einen DOM-ähnlichen Ansatz für das Erstellen von Aktivitäten bereit, der eine Schnittstelle mit dem WF-Designer und den Laufzeitvorgängen über <xref:System.ComponentModel.ICustomTypeDescriptor> bietet. Damit können neue Aktivitäten ohne die Definition neuer Typen erstellt werden.|  
  
## <a name="authoring-activities-using-activity"></a>Erstellen von Aktivitäten mit Activity  

 Bei Aktivitäten, die von <xref:System.Activities.Activity> abgeleitet werden, wird die Funktionalität aus der Kombination anderer vorhandener Aktivitäten zusammengesetzt. Bei diesen Aktivitäten kann es sich um benutzerdefinierte Aktivitäten und Aktivitäten aus der [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]-Aktivitätsbibliothek handeln. Das Zusammenfügen dieser Aktivitäten stellt die grundlegendste Möglichkeit für das Erstellen benutzerdefinierter Funktionalität dar. Der Ansatz wird in der Regel angewendet, wenn eine visuelle Entwurfsumgebung zum Erstellen von Workflows verwendet wird.  
  
## <a name="authoring-activities-using-codeactivity-or-asynccodeactivity"></a>Erstellen von Aktivitäten mit CodeActivity oder AsyncCodeActivity  

 Aktivitäten, die von <xref:System.Activities.CodeActivity> oder von <xref:System.Activities.AsyncCodeActivity> abgeleitet werden, können imperative Funktionalität implementieren, indem sie die <xref:System.Activities.CodeActivity%601.Execute%2A>-Methode mit benutzerdefiniertem imperativem Code überschreiben. Der benutzerdefinierte Code wird ausgeführt, wenn die Aktivität von der Laufzeit ausgeführt wird. Auf diese Weise erstellte Aktivitäten können auf benutzerdefinierte Funktionalität zugreifen, jedoch nicht auf sämtliche Funktionen der Laufzeit. So verfügen sie nicht über Vollzugriff auf die Ausführungsumgebung und sind nicht in der Lage, untergeordnete Aktivitäten zu planen, Lesezeichen zu erstellen oder die Cancel-Methode und die Abort-Methode zu unterstützen. Wenn eine <xref:System.Activities.CodeActivity> ausgeführt wird, verfügt diese über Zugriff auf eine eingeschränkte Version der Ausführungsumgebung (durch die <xref:System.Activities.CodeActivityContext>-Klasse oder die <xref:System.Activities.AsyncCodeActivityContext>-Klasse). Mit der <xref:System.Activities.CodeActivity> erstellte Aktivitäten verfügen über Zugriff auf Argument- und Variablenauflösung, Erweiterungen und Überwachung. Asynchronen Aktivitäten können mit <xref:System.Activities.AsyncCodeActivity> geplant werden.  
  
## <a name="authoring-activities-using-nativeactivity"></a>Erstellen von Aktivitäten mit NativeActivity  

 Mit Aktivitäten, die von der <xref:System.Activities.NativeActivity> abgeleitet werden (etwa von der <xref:System.Activities.CodeActivity> abgeleitete Aktivitäten), wird eine imperative Funktionalität erzeugt, indem <xref:System.Activities.NativeActivity.Execute%2A> überschrieben wird. Es besteht jedoch über den <xref:System.Activities.NativeActivityContext>, der an die <xref:System.Activities.NativeActivity.Execute%2A>-Methode weitergegeben wird, Zugriff auf die gesamte Funktionalität der Workflowlaufzeit. Dieser Kontext bietet Unterstützung für das Planen und Abbrechen von untergeordneten Aktivitäten, das Ausführen von <xref:System.Activities.ActivityAction>- und <xref:System.Activities.ActivityFunc%601>-Objekten, das Übertragen von Transaktionen in einen Workflow, das Aufrufen asynchroner Prozesse, das Abbrechen der Ausführung, den Zugriff auf Ausführungseigenschaften und -erweiterungen sowie Lesezeichen (Handles zum Fortsetzen von angehaltenen Workflows).  
  
## <a name="authoring-activities-using-dynamicactivity"></a>Erstellen von Aktivitäten mit DynamicActivity  

 Im Gegensatz zu den anderen drei Aktivitätstypen wird Funktionalität nicht durch das Ableiten neuer Typen von der <xref:System.Activities.DynamicActivity> erstellt (die Klasse ist versiegelt), sondern durch das Zusammenfügen von Funktionalität in der <xref:System.Activities.DynamicActivity.Properties%2A>-Eigenschaft und der <xref:System.Activities.DynamicActivity.Implementation%2A>-Eigenschaft mit einem Dokumentobjektmodell (DOM) für Aktivitäten.  
  
## <a name="authoring-activities-that-return-a-result"></a>Erstellen von Aktivitäten, die ein Ergebnis zurückgeben  

 Viele Aktivitäten müssen nach ihrer Ausführung ein Ergebnis zurückgeben. Es ist möglich, zu diesem Zweck ein benutzerdefiniertes <xref:System.Activities.OutArgument%601> für eine Aktivität anzugeben, aber es empfiehlt sich, stattdessen die <xref:System.Activities.Activity%601> oder eine Ableitung von der <xref:System.Activities.CodeActivity%601> oder <xref:System.Activities.NativeActivity%601> zu verwenden. Jede dieser Basisklassen verfügt über ein <xref:System.Activities.OutArgument%601> mit dem Namen Result, das die Aktivität für den Rückgabewert verwenden kann. Aktivitäten, die ein Ergebnis zurückgeben, sollten nur verwendet werden, wenn nur ein Ergebnis aus einer Aktivität zurückgegeben werden muss. Wenn mehrere Ergebnisse zurückgegeben werden müssen, sollten stattdessen separate <xref:System.Activities.OutArgument%601>-Member verwendet werden.
