---
title: Workflowpersistenz
description: .NET Framework 4.6.1 schließt die SqlWorkflowInstanceStore-Klasse ein, die die Persistenz von Workflow Daten und Metadaten in einer SQL Server Datenbank ermöglicht.
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
ms.openlocfilehash: c609ec5e67ce3bb0605f543806085f893acba37c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557527"
---
# <a name="workflow-persistence"></a>Workflowpersistenz
Workflowpersistenz bezeichnet die dauerhafte Erfassung des Zustands einer Workflowinstanz unabhängig von Prozess- oder Computerinformationen. Sie wird durchgeführt, um einen bekannten Wiederherstellungspunkt für die Workflowinstanz im Fall eines Systemfehlers bereitzustellen oder um Arbeitsspeicher beizubehalten, indem Workflowinstanzen entladen werden, die gerade nicht aktiv sind, bzw. um den Zustand der Workflowinstanz von einem Knoten zu einem anderen Knoten in einer Serverfarm zu verschieben.  
  
 Die Persistenz aktiviert die Flexibilität, Skalierbarkeit und Wiederherstellung von Prozessen bei einem Fehler und bietet die Möglichkeit, den Arbeitsspeicher effizienter zu verwalten. Der Persistenzvorgang umfasst die Identifikation eines Persistenzpunkts, das Sammeln der zu speichernden Daten und schließlich die Delegierung des tatsächlichen Speichers der Daten an einen Persistenzanbieter.  
  
 Um die Persistenz für einen Workflow zu aktivieren, müssen Sie der **WorkflowApplication** oder Workflow **Service Host** einen Instanzspeicher zuordnen, wie unter Gewusst [wie: Aktivieren der Persistenz für Workflows und Workflow Dienste](how-to-enable-persistence-for-workflows-and-workflow-services.md)beschrieben. Die Workflow **Application** und Workflow **Service Host** verwenden den Instanzspeicher, der Ihnen zugeordnet ist, um das Beibehalten von Workflow Instanzen in einen Persistenzspeicher und das Laden von Workflow Instanzen in den Arbeitsspeicher auf Grundlage der im Beibehaltungs Speicher gespeicherten Workflowinstanzdaten zu ermöglichen.  
  
 Die [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] wird mit der **SqlWorkflowInstanceStore** -Klasse ausgeliefert, die die Persistenz von Daten und Metadaten zu Workflow Instanzen in eine SQL Server 2005-oder SQL Server 2008-Datenbank ermöglicht. Weitere Informationen finden Sie unter [SQL-workflowinstanzspeicher](sql-workflow-instance-store.md) .  
  
 Zum Speichern und Laden Ihrer anwendungsspezifischen Daten zusammen mit den Informationen zur Workflowinstanz können Sie Persistenzteilnehmer erstellen, die die <xref:System.Activities.Persistence.PersistenceParticipant>-Klasse erweitern. Ein Persistenzteilnehmer nimmt am Persistenzvorgang teil, um benutzerdefinierte serialisierbare Daten in den persistenten Speicher zu speichern, die Daten aus dem Instanzspeicher in den Arbeitsspeicher zu laden und ggf. die zusätzliche Logik einer Persistenztransaktion auszuführen. Weitere Informationen finden Sie unter [persistenzteilnehmer](persistence-participants.md).  
  
 Windows Server AppFabric vereinfacht die Konfiguration von Persistenz. Weitere Informationen finden Sie unter [Persistenzkonzepte mit Windows Server-App-Fabric](/previous-versions/appfabric/ee677272(v=azure.10)) .  
  
## <a name="implicit-persistence-points"></a>Implizite Persistenzpunkte  
 Die folgende Liste enthält Beispiele der Bedingungen, zu denen ein Workflow beibehalten wird, wenn ein Instanzspeicher einem Workflow zugeordnet ist.  
  
- Wenn eine **transaktionscope** -Aktivität abgeschlossen ist oder eine **transactedreceivescope** -Aktivität abgeschlossen wird.  
  
- Wenn eine Workflow Instanz in den Leerlauf wechselt und **workflowidlebehavior** auf dem Workflow Host festgelegt ist. Dies tritt z. b. auf, wenn Sie Messaging Aktivitäten oder eine **Verzögerungs** Aktivität verwenden.  
  
- Wenn eine WorkflowApplication in den Leerlauf wechselt und die **PersistableIdle** -Eigenschaft der Anwendung auf **persistableidleaction. persistent**festgelegt ist.  
  
- Wenn eine Hostanwendung angewiesen ist, eine Workflowinstanz beizubehalten oder zu entladen.  
  
- Wenn eine Workflowinstanz beendet oder fertig gestellt wird.  
  
- Wenn eine **persistenzaktivität** ausgeführt wird.  
  
- Wenn eine Instanz eines Workflows, die mit einer früheren Version von Windows Workflow Foundation entwickelt wurde, während einer interoperablen Ausführung auf einen Persistenzpunkt trifft.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
- [SQL-Workflowinstanzspeicher](sql-workflow-instance-store.md)  
  
- [Instanzspeicher](instance-stores.md)  
  
- [Persistenzteilnehmer](persistence-participants.md)  
  
- [Empfohlene Vorgehensweisen für die Persistenz](persistence-best-practices.md)  
  
- [Nicht beibehaltene Workflowinstanzen](non-persisted-workflow-instances.md)  
  
- [Anhalten und Fortsetzen eines Workflows](pausing-and-resuming-a-workflow.md)
