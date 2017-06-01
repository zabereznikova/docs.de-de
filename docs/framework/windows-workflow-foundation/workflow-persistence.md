---
title: "Workflowpersistenz | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Programmieren [WF], Persistenz"
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# Workflowpersistenz
Workflowpersistenz bezeichnet die permanente Erfassung des Zustands einer Workflowinstanz unabhängig von Prozess\- oder Computerinformationen.Sie wird durchgeführt, um einen bekannten Wiederherstellungspunkt für die Workflowinstanz im Fall eines Systemfehlers bereitzustellen oder um Arbeitsspeicher beizubehalten, indem Workflowinstanzen entladen werden, die gerade nicht aktiv sind, bzw. um den Zustand der Workflowinstanz von einem Knoten zu einem anderen Knoten in einer Serverfarm zu verschieben.  
  
 Die Persistenz aktiviert die Flexibilität, Skalierbarkeit und Wiederherstellung von Prozessen bei einem Fehler und bietet die Möglichkeit, den Arbeitsspeicher effizienter zu verwalten.Der Persistenzvorgang umfasst die Identifikation eines Persistenzpunkts, das Sammeln der zu speichernden Daten und schließlich die Delegierung des tatsächlichen Speichers der Daten an einen Persistenzanbieter.  
  
 Um die Persistenz für einen Workflow zu aktivieren, müssen Sie der **WorkflowApplication** oder dem **WorkflowServiceHost** einen Instanzspeicher zuordnen, wie in [Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste](../../../docs/framework/windows-workflow-foundation//how-to-enable-persistence-for-workflows-and-workflow-services.md) beschrieben.Die **WorkflowApplication** und der **WorkflowServiceHost** verwenden den Instanzspeicher, der Ihnen zugeordnet wurde, um das Speichern von Workflowinstanzen in einen persistenten Speicher und das Laden von Workflowinstanzen in den Arbeitsspeicher auf Grundlage der im persistenten Speicher gespeicherten Workflowinstanzdaten zu aktivieren.  
  
 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] enthält die **SqlWorkflowInstanceStore**\-Klasse, die die Persistenz von Daten und Metadaten zu Workflowinstanzen in eine Datenbank von SQL Server 2005 oder SQL Server 2008 zulässt.Weitere Informationen finden Sie unter [SQL\-Workflowinstanzspeicher](../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md).  
  
 Zum Speichern und Laden Ihrer anwendungsspezifischen Daten zusammen mit den Informationen zur Workflowinstanz können Sie Persistenzteilnehmer erstellen, die die <xref:System.Activities.Persistence.PersistenceParticipant>\-Klasse erweitern.Ein Persistenzteilnehmer nimmt am Persistenzvorgang teil, um benutzerdefinierte serialisierbare Daten in den persistenten Speicher zu speichern, die Daten aus dem Instanzspeicher in den Arbeitsspeicher zu laden und ggf. die zusätzliche Logik einer Persistenztransaktion auszuführen.Weitere Informationen finden Sie unter [Persistenzteilnehmer](../../../docs/framework/windows-workflow-foundation//persistence-participants.md).  
  
 Windows Server AppFabric vereinfacht die Konfiguration von Persistenz.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Persistenzkonzepte mit Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201200)  
  
## Implizite Persistenzpunkte  
 Die folgende Liste enthält Beispiele der Bedingungen, zu denen ein Workflow beibehalten wird, wenn ein Instanzspeicher einem Workflow zugeordnet ist.  
  
-   Wenn eine **TransactionScope**\-Aktivität oder eine **TransactedReceiveScope**\-Aktivität abgeschlossen wird.  
  
-   Wenn eine Workflowinstanz in den Leerlauf wechselt und das **WorkflowIdleBehavior** auf den Workflowhost festgelegt ist.Dies ist z. B. der Fall, wenn Sie Messagingaktivitäten oder eine **Delay**\-Aktivität verwenden.  
  
-   Wenn eine Workflowanwendung in den Leerlauf wechselt und die **PersistableIdle**\-Eigenschaft der Anwendung auf **PersistableIdleAction.Persist** festgelegt ist.  
  
-   Wenn eine Hostanwendung angewiesen ist, eine Workflowinstanz beizubehalten oder zu entladen.  
  
-   Wenn eine Workflowinstanz beendet oder fertig gestellt wird.  
  
-   Wenn eine **Persist**\-Aktivität ausgeführt wird.  
  
-   Wenn eine Instanz eines Workflows, die mit einer früheren Version von Windows Workflow Foundation entwickelt wurde, während einer interoperablen Ausführung auf einen Persistenzpunkt trifft.  
  
## In diesem Abschnitt  
  
-   [SQL\-Workflowinstanzspeicher](../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md)  
  
-   [Instanzspeicher](../../../docs/framework/windows-workflow-foundation//instance-stores.md)  
  
-   [Persistenzteilnehmer](../../../docs/framework/windows-workflow-foundation//persistence-participants.md)  
  
-   [Empfohlene Vorgehensweisen für die Persistenz](../../../docs/framework/windows-workflow-foundation//persistence-best-practices.md)  
  
-   [Nicht beibehaltene Workflowinstanzen](../../../docs/framework/windows-workflow-foundation//non-persisted-workflow-instances.md)  
  
-   [Anhalten und Fortsetzen eines Workflows](../../../docs/framework/windows-workflow-foundation//pausing-and-resuming-a-workflow.md)