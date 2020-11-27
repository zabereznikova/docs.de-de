---
title: Grundlegende Konzepte für Windows-Workflows
description: In diesem Artikel werden einige der Konzepte der Workflow Entwicklung in den .NET Framework 4.6.1 beschrieben, die einigen Entwicklern möglicherweise nicht vertraut sind.
ms.date: 03/30/2017
ms.assetid: 0e930e80-5060-45d2-8a7a-95c0690105d4
ms.openlocfilehash: a7683791c7aed54beed9256ab08010dfeebe9936
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265296"
---
# <a name="fundamental-windows-workflow-concepts"></a>Grundlegende Konzepte für Windows-Workflows

Bei der Workflowentwicklung in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] werden Konzepte verwendet, die für einige Entwickler möglicherweise neu sind. In diesem Thema werden einige dieser Konzepte und ihre Implementierung beschrieben.  
  
## <a name="workflows-and-activities"></a>Workflows und Aktivitäten  

 Ein Workflow ist eine strukturierte Auflistung von Aktionen zur Modellierung eines Prozesses. Jede Aktion im Workflow wird als Aktivität modelliert. Ein Host verwendet bei der Interaktion mit einem Workflow ein <xref:System.Activities.WorkflowInvoker>-Element zum Aufrufen eines Workflows wie eine Methode, <xref:System.Activities.WorkflowApplication> zur expliziten Steuerung der Ausführung einer einzelnen Workflowinstanz und <xref:System.ServiceModel.WorkflowServiceHost> für nachrichtenbasierte Interaktionen in Szenarios mit mehreren Instanzen. Die Schritte des Workflows setzen sich aus einer Hierarchie von Aktivitäten zusammen, und der Workflow selbst wird durch die Aktivität auf oberster Ebene in der Hierarchie definiert. Dieses Hierarchiemodell tritt an die Stelle der expliziten `SequentialWorkflow`-Klasse und `StateMachineWorkflow`-Klasse in früheren Versionen. Die einzelnen Aktivitäten können entweder als Auflistungen anderer Aktivitäten (mit der <xref:System.Activities.Activity>-Klasse als Basis, in der Regel mit XAML definiert) entwickelt oder neu erstellt werden, entweder mit der <xref:System.Activities.CodeActivity>-Klasse, die die Laufzeit für den Datenzugriff nutzen kann, oder mit der <xref:System.Activities.NativeActivity>-Klasse, die die Workflowlaufzeit für den Aktivitätsautor verfügbar macht. Mit <xref:System.Activities.CodeActivity> und <xref:System.Activities.NativeActivity> entwickelte Aktivitäten werden mit CLR-kompatiblen Sprachen wie C# erstellt.  
  
## <a name="activity-data-model"></a>Aktivitätsdatenmodell  

 Aktivitäten nutzen die Typen in der folgenden Tabelle zum Speichern und Freigeben von Daten.  
  
|||  
|-|-|  
|Variable|Speichert Daten in einer Aktivität.|  
|Argument|Verschiebt Daten in eine bzw. aus einer Aktivität.|  
|Ausdruck|Eine Aktivität mit einem eskalierten Rückgabewert in Argumentbindungen.|  
  
## <a name="workflow-runtime"></a>Workflow-Laufzeit  

 Die Workflowlaufzeit ist die Umgebung, in der Workflows ausgeführt werden. <xref:System.Activities.WorkflowInvoker> ist die einfachste Möglichkeit, einen Workflow auszuführen. Der Host verwendet <xref:System.Activities.WorkflowInvoker> für folgende Aktionen:  
  
- Synchrones Aufrufen eines Workflows  
  
- Bereitstellen von Eingabedaten bzw. Abrufen von Ausgabedaten eines Workflows  
  
- Hinzufügen von Erweiterungen für Aktivitäten  
  
 <xref:System.Activities.ActivityInstance> ist der threadsichere Proxy, über den Hosts mit der Laufzeit interagieren können. Der Host verwendet <xref:System.Activities.ActivityInstance> für folgende Aktionen:  
  
- Abrufen einer Instanz durch Erstellen oder Laden aus einem Instanzspeicher  
  
- Aktivieren von Benachrichtigungen bei Instanzlebenszyklusereignissen  
  
- Steuern der Workflowausführung  
  
- Bereitstellen von Eingabedaten bzw. Abrufen von Ausgabedaten eines Workflows  
  
- Signalisieren einer Workflowfortsetzung und Übergeben von Werten in den Workflow  
  
- Aufbewahren von Workflowdaten  
  
- Hinzufügen von Erweiterungen für Aktivitäten  
  
 Aktivitäten erhalten Zugriff auf die Workflowlaufzeitumgebung, indem sie die entsprechende abgeleitete <xref:System.Activities.ActivityContext>-Klasse wie <xref:System.Activities.NativeActivityContext> oder <xref:System.Activities.CodeActivityContext> verwenden. Sie verwenden diese zum Auflösen von Argumenten und Variablen, zum Planen von untergeordneten Aktivitäten und zu vielen anderen Zwecken.  
  
## <a name="services"></a>Dienste  

 Workflows bieten eine natürliche Möglichkeit zum Implementieren von und zum Zugreifen auf lose verknüpfte Dienste mithilfe von Messagingaktivitäten. Messaging Aktivitäten basieren auf WCF und sind der primäre Mechanismus, der verwendet wird, um Daten in einen und aus einem Workflow zu übernehmen. Sie können Messagingaktivitäten kombinieren, um beliebige Arten von Nachrichtenaustauschmustern zu modellieren. Weitere Informationen finden Sie unter [Messaging Aktivitäten](../wcf/feature-details/messaging-activities.md). Workflowdienste werden mit der <xref:System.ServiceModel.Activities.WorkflowServiceHost>-Klasse gehostet. Weitere Informationen finden Sie unter [Hosting Workflow Services Overview](../wcf/feature-details/hosting-workflow-services-overview.md). Weitere Informationen zu Workflow Diensten finden Sie unter [Workflow Dienste](../wcf/feature-details/workflow-services.md)  
  
## <a name="persistence-unloading-and-long-running-workflows"></a>Persistenz, Entladen und langfristige Workflows  

 Windows Workflow vereinfacht die Erstellung von langfristigen reaktiven Programmen durch die folgenden Punkte:  
  
- Aktivitäten, die auf externe Eingabedaten zugreifen.  
  
- Die Möglichkeit zur Erstellung von <xref:System.Activities.Bookmark>-Objekten, die von einer Host-Listeneranwendung übernommen werden können.  
  
- Die Möglichkeit zum Aufbewahren der Daten eines Workflows und zum Entladen des Workflows und zum anschließenden erneuten Laden und Aktivieren des Workflows basierend auf der Wiederaufnahme von <xref:System.Activities.Bookmark>-Objekten in einem bestimmten Workflow.  
  
 Ein Workflow führt kontinuierlich Aktivitäten aus, bis keine Aktivitäten mehr auszuführen sind bzw. bis für alle ausgeführten Aktivitäten eine Eingabe aussteht. Im letzteren Fall befindet sich der Workflow im Leerlauf. Workflows im Leerlauf werden von einem Host häufig entladen und dann neu geladen, um die Ausführung fortzusetzen, wenn eine Nachricht eingeht. <xref:System.ServiceModel.Activities.WorkflowServiceHost> stellt Funktionen für dieses Feature sowie eine erweiterbare Entladerichtlinie bereit. Für Ausführungsblöcke mit Daten im flüchtigen Zustand bzw. anderen Daten, die nicht dauerhaft gespeichert werden können, kann in einer Aktivität mit <xref:System.Activities.NoPersistHandle> angegeben werden, dass die Daten nicht dauerhaft gespeichert werden sollen. Die Daten eines Workflows können auch mit der <xref:System.Activities.Statements.Persist>-Aktivität explizit auf einem dafür vorgesehenen Speichermedium dauerhaft gespeichert werden.
