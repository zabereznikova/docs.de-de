---
title: "Instanzaktivierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 134c3f70-5d4e-46d0-9d49-469a6643edd8
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Instanzaktivierung
Der SQL\-Workflowinstanzspeicher führt eine interne Aufgabe aus, die in regelmäßigen Abständen aktiviert wird und ausführbare oder aktivierbare Workflowinstanzen in der Persistenzdatenbank ermittelt.Wenn eine ausführbare Workflowinstanz gefunden wird, erfolgt die Benachrichtigung des Workflowhosts, der die Instanz aktivieren kann.Wenn der Instanzspeicher eine aktivierbare Workflowinstanz findet, wird ein generischer Host benachrichtigt, der einen Workflowhost aktiviert, der wiederum die Workflowinstanz ausführt.In den folgenden Abschnitten dieses Themas wird der Instanzaktivierungsprozess detailliert erläutert.  
  
##  <a name="RunnableSection"></a> Erkennen und Aktivieren von ausführbaren Workflowinstanzen  
 Der SQL\-Workflowinstanzspeicher erkennt eine Workflowinstanz als *ausführbar*, wenn die Instanz sich nicht im Zustand "Angehalten" oder "Abgeschlossen" befindet und die folgenden Bedingungen erfüllt:  
  
-   Die Instanz ist nicht gesperrt und weist einen ausstehenden Zeitgeber auf, der abgelaufen ist.  
  
-   Die Instanz weist eine abgelaufene Sperre auf.  
  
-   Die Instanz ist nicht gesperrt und weist den Zustand **Wird ausgeführt** auf.  
  
 Der SQL\-Workflowinstanzspeicher löst das <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> aus, wenn eine ausführbare Instanz gefunden wird.Anschließend wird die Überwachung gestoppt, bis <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand> einmal für den Speicher aufgerufen wird.  
  
 Ein Workflowhost, der das <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent>\-Element abonniert hat und die Instanz laden kann, führt das <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>\-Element für den Instanzspeicher aus, um die Instanz in den Arbeitsspeicher zu laden.Ein Workflowhost kann eine Workflowinstanz laden, wenn die Metadateneigenschaft **WorkflowServiceType** des Hosts und der Instanz denselben Wert aufweist.  
  
## Erkennen und Aktivieren von aktivierbaren Workflowinstanzen  
 Eine Workflowinstanz wird als *aktivierbar* erkannt, wenn die Instanz ausführbar ist und auf dem Computer kein Workflowhost ausgeführt wird, der die Instanz laden kann.Die Definition einer ausführbaren Workflowinstanz finden Sie weiter oben unter "Erkennen und Aktivieren von ausführbaren Workflowinstanzen".  
  
 Der SQL\-Workflowinstanzspeicher löst das <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> aus, wenn eine aktivierbare Workflowinstanz in der Datenbank gefunden wird.Anschließend wird die Überwachung gestoppt, bis <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand> einmal für den Speicher aufgerufen wird.  
  
 Wenn ein generischer Host, der das <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent>\-Element abonniert hat, das Ereignis empfängt, wird das <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>\-Element für den Instanzspeicher ausgeführt, um die zur Erstellung eines Workflowhosts erforderlichen Aktivierungsparameter abzurufen.Der generische Host erstellt mit diesen Aktivierungsparametern einen Workflowhost, der die ausführbare Dienstinstanz dann lädt und ausführt.  
  
## Generische Hosts  
 Ein generischer Host ist ein Host, bei dem der Wert der Metadateneigenschaft **WorkflowServiceType** für generische Hosts auf **WorkflowServiceType.Any** festgelegt ist, um anzugeben, dass der Host jeden Workflowtyp verarbeiten kann.Ein generischer Host verfügt über einen XName\-Parameter mit dem Namen **ActivationType**.  
  
 Derzeit unterstützt der SQL\-Workflowinstanzspeicher generische Hosts, bei denen der Wert des ActivationType\-Parameters auf **WAS** festgelegt ist.Wenn der ActivationType\-Parameter nicht den Wert WAS aufweist, löst der SQL\-Workflowinstanzspeicher einen <xref:System.Runtime.DurableInstancing.InstancePersistenceException>\-Fehler aus.Der im Lieferumfang von [!INCLUDE[dublin](../../../includes/dublin-md.md)] enthaltene Workflowverwaltungsdienst ist ein generischer Host, dessen Aktivierungstyp auf **WAS** festgelegt ist.  
  
 Zur WAS\-Aktivierung erfordert ein generischer Host einen Satz von Aktivierungsparametern, um die Endpunktadresse abzuleiten, an der neue Hosts aktiviert werden können.Die Aktivierungsparameter zu WAS\-Aktivierung sind der Name der Site, der Anwendungspfad relativ zur Website und der Dienstpfad relativ zur Anwendung.Der SQL\-Workflowinstanzspeicher speichert diese Aktivierungsparameter während der Ausführung des <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>\-Objekts.  
  
## Runnable Instances Detection Period  
 Die Eigenschaft **Runnable Instances Detection Period** des SQL\-Workflowinstanzspeichers gibt den Zeitraum an, nach dem der SQL\-Workflowinstanzspeicher eine Ermittlungsaufgabe ausführt, um alle ausführbaren oder aktivierbaren Workflowinstanzen in der Persistenzdatenbank nach dem vorhergehenden Ermittlungslauf zu erkennen.Nähere Informationen zu dieser Eigenschaft finden Sie unter [Runnable Instances Detection Period](../../../docs/framework/windows-workflow-foundation//runnable-instances-detection-period.md).