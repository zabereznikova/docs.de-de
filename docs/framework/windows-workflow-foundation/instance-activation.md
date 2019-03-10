---
title: Instanzaktivierung
ms.date: 03/30/2017
ms.assetid: 134c3f70-5d4e-46d0-9d49-469a6643edd8
ms.openlocfilehash: 41dfc076bdee72c2f4d0c781c6588caa927c740e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703399"
---
# <a name="instance-activation"></a>Instanzaktivierung
Der SQL-Workflowinstanzspeicher führt eine interne Aufgabe aus, die in regelmäßigen Abständen aktiviert wird und ausführbare oder aktivierbare Workflowinstanzen in der Persistenzdatenbank ermittelt. Wenn eine ausführbare Workflowinstanz gefunden wird, erfolgt die Benachrichtigung des Workflowhosts, der die Instanz aktivieren kann. Wenn der Instanzspeicher eine aktivierbare Workflowinstanz findet, wird ein generischer Host benachrichtigt, der einen Workflowhost aktiviert, der wiederum die Workflowinstanz ausführt. In den folgenden Abschnitten dieses Themas wird der Instanzaktivierungsprozess detailliert erläutert.  
  
## <a name="RunnableSection"></a> Erkennen und Aktivieren von ausführbaren Workflowinstanzen  
 Die SQL-Workflow-Instanz Store erkennt eine Workflowinstanz als *ausführbare* Wenn die Instanz befindet sich nicht im Zustand "angehalten" oder den Status "abgeschlossen", und die folgenden Bedingungen erfüllt:  
  
-   Die Instanz ist nicht gesperrt und weist einen ausstehenden Timer auf, der abgelaufen ist.  
  
-   Die Instanz weist eine abgelaufene Sperre auf.  
  
-   Die Instanz entsperrt ist und der Status ist **ausführen**.  
  
 Der SQL-Workflowinstanzspeicher löst das <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> aus, wenn eine ausführbare Instanz gefunden wird. Anschließend wird die Überwachung gestoppt, bis <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand> einmal für den Speicher aufgerufen wird.  
  
 Ein Workflowhost, der das <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent>-Element abonniert hat und die Instanz laden kann, führt das <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>-Element für den Instanzspeicher aus, um die Instanz in den Arbeitsspeicher zu laden. Gilt als ein Workflowhost kann eine Workflowinstanz zu laden, wenn der Host und die Instanz Metadateneigenschaft haben **WorkflowServiceType** auf den gleichen Wert festgelegt.  
  
## <a name="detecting-and-activating-activatable-workflow-instances"></a>Erkennen und Aktivieren von aktivierbaren Workflowinstanzen  
 Eine Workflowinstanz *aktivierbare* , wenn die Instanz ausführbar ist, und es gibt kein Workflowhost, der die Instanz laden kann, auf dem Computer ausgeführt wird. Die Definition einer ausführbaren Workflowinstanz finden Sie weiter oben unter "Erkennen und Aktivieren von ausführbaren Workflowinstanzen".  
  
 Der SQL-Workflowinstanzspeicher löst das <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> aus, wenn eine aktivierbare Workflowinstanz in der Datenbank gefunden wird. Anschließend wird die Überwachung gestoppt, bis <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand> einmal für den Speicher aufgerufen wird.  
  
 Wenn ein generischer Host, der das <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent>-Element abonniert hat, das Ereignis empfängt, wird das <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>-Element für den Instanzspeicher ausgeführt, um die zur Erstellung eines Workflowhosts erforderlichen Aktivierungsparameter abzurufen. Der generische Host erstellt mit diesen Aktivierungsparametern einen Workflowhost, der die ausführbare Dienstinstanz dann lädt und ausführt.  
  
## <a name="generic-hosts"></a>Generische Hosts  
 Ein generischer Host ist ein Host mit dem Wert der Metadateneigenschaft **WorkflowServiceType** für generische Hosts nastaven NA hodnotu **WorkflowServiceType.Any** um anzugeben, dass sie jeden Workflowtyp verarbeiten kann. Ein generischer Host verfügt über einen XName-Parameter, die mit dem Namen **ActivationType**.  
  
 Derzeit unterstützt der SQL-Workflow-Instanz Store generische Hosts mit dem Wert des ActivationType-Parameters festgelegt **WAS**. Wenn der ActivationType-Parameter nicht den Wert WAS aufweist, löst der SQL-Workflowinstanzspeicher einen <xref:System.Runtime.DurableInstancing.InstancePersistenceException>-Fehler aus. Die Workflow-Verwaltungsdiensts, die im Lieferumfang der [!INCLUDE[dublin](../../../includes/dublin-md.md)] ist ein generischer Host, die die Aktivierungstyp **WAS**.  
  
 Zur WAS-Aktivierung erfordert ein generischer Host einen Satz von Aktivierungsparametern, um die Endpunktadresse abzuleiten, an der neue Hosts aktiviert werden können. Die Aktivierungsparameter zu WAS-Aktivierung sind der Name der Site, der Anwendungspfad relativ zur Website und der Dienstpfad relativ zur Anwendung. Der SQL-Workflowinstanzspeicher speichert diese Aktivierungsparameter während der Ausführung des <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>-Objekts.  
  
## <a name="runnable-instances-detection-period"></a>Runnable Instances Detection Period  
 Die **Runnable Instances Detection Period** Eigenschaft von der SQL-Workflow-Instanz Store gibt den Zeitraum, nach dem die SQL-Workflow-Instanz Store, eine erkennungsaufgabe zum Erkennen von einem Workflow ausführbare oder aktivierbare ausführt, die Instanzen in der Persistenzdatenbank nach dem vorhergehenden ermittlungslauf. Finden Sie unter [Runnable Instances Detection Period](runnable-instances-detection-period.md) für Weitere Informationen zu dieser Eigenschaft.
