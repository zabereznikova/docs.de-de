---
title: Workflowpersistenz
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9e65f07fc01d0d364d7271c4f1378b968b687881
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-persistence"></a>Workflowpersistenz
Workflowpersistenz bezeichnet die dauerhafte Erfassung des Zustands einer Workflowinstanz unabhängig von Prozess- oder Computerinformationen. Sie wird durchgeführt, um einen bekannten Wiederherstellungspunkt für die Workflowinstanz im Fall eines Systemfehlers bereitzustellen oder um Arbeitsspeicher beizubehalten, indem Workflowinstanzen entladen werden, die gerade nicht aktiv sind, bzw. um den Zustand der Workflowinstanz von einem Knoten zu einem anderen Knoten in einer Serverfarm zu verschieben.  
  
 Die Persistenz aktiviert die Flexibilität, Skalierbarkeit und Wiederherstellung von Prozessen bei einem Fehler und bietet die Möglichkeit, den Arbeitsspeicher effizienter zu verwalten. Der Persistenzvorgang umfasst die Identifikation eines Persistenzpunkts, das Sammeln der zu speichernden Daten und schließlich die Delegierung des tatsächlichen Speichers der Daten an einen Persistenzanbieter.  
  
 Um die Persistenz für einen Workflow zu aktivieren, müssen Sie mit einen Instanzspeicher Zuordnen der **WorkflowApplication** oder **WorkflowServiceHost** Siehe [wie: Aktivieren der Persistenz für Workflows und Workflowdienste](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md). Die **WorkflowApplication** und **WorkflowServiceHost** verwenden Sie den Instanzspeicher, die ihnen zugeordneten zum Beibehalten von Workflowinstanzen in einem persistenten Speicher und das Laden von Workflowinstanzen in aktivieren Arbeitsspeicher auf Grundlage der im persistenten Speicher gespeicherten workflowinstanzdaten.  
  
 Die [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] im Lieferumfang der **SqlWorkflowInstanceStore** -Klasse, die Persistenz von Daten und Metadaten zu Workflowinstanzen in einer SQL Server 2005 oder SQL Server 2008-Datenbank ermöglicht. Finden Sie unter [SQL-Workflowinstanzspeicher](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) Weitere Details.  
  
 Zum Speichern und Laden Ihrer anwendungsspezifischen Daten zusammen mit den Informationen zur Workflowinstanz können Sie Persistenzteilnehmer erstellen, die die <xref:System.Activities.Persistence.PersistenceParticipant>-Klasse erweitern. Ein Persistenzteilnehmer nimmt am Persistenzvorgang teil, um benutzerdefinierte serialisierbare Daten in den persistenten Speicher zu speichern, die Daten aus dem Instanzspeicher in den Arbeitsspeicher zu laden und ggf. die zusätzliche Logik einer Persistenztransaktion auszuführen. Weitere Informationen finden Sie unter [Persistenzteilnehmer](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).  
  
 Windows Server AppFabric vereinfacht die Konfiguration von Persistenz. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Persistenz Konzepte mit Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201200)  
  
## <a name="implicit-persistence-points"></a>Implizite Persistenzpunkte  
 Die folgende Liste enthält Beispiele der Bedingungen, zu denen ein Workflow beibehalten wird, wenn ein Instanzspeicher einem Workflow zugeordnet ist.  
  
-   Wenn eine **TransactionScope** Aktivität abgeschlossen wird oder ein **TransactedReceiveScope** Aktivität abgeschlossen wird.  
  
-   Wenn eine Workflowinstanz im Leerlauf ist und die **WorkflowIdleBehavior** auf den Workflowhost festgelegt ist. In diesem Fall z. B. Wenn Sie messagingaktivitäten verwenden oder eine **Verzögerung** Aktivität.  
  
-   Wenn eine Leerlauf und der **PersistableIdle** der Anwendung ist-Eigenschaftensatz auf **PersistableIdleAction.Persist**.  
  
-   Wenn eine Hostanwendung angewiesen ist, eine Workflowinstanz beizubehalten oder zu entladen.  
  
-   Wenn eine Workflowinstanz beendet oder fertig gestellt wird.  
  
-   Wenn eine **Persist** Aktivität ausgeführt wird.  
  
-   Wenn eine Instanz eines Workflows, die mit einer früheren Version von Windows Workflow Foundation entwickelt wurde, während einer interoperablen Ausführung auf einen Persistenzpunkt trifft.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
-   [SQL-Workflowinstanzspeicher](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)  
  
-   [Instanzspeicher](../../../docs/framework/windows-workflow-foundation/instance-stores.md)  
  
-   [Persistenzteilnehmer](../../../docs/framework/windows-workflow-foundation/persistence-participants.md)  
  
-   [Empfohlene Vorgehensweisen für die Persistenz](../../../docs/framework/windows-workflow-foundation/persistence-best-practices.md)  
  
-   [Nicht beibehaltene Workflowinstanzen](../../../docs/framework/windows-workflow-foundation/non-persisted-workflow-instances.md)  
  
-   [Anhalten und Fortsetzen eines Workflows](../../../docs/framework/windows-workflow-foundation/pausing-and-resuming-a-workflow.md)
