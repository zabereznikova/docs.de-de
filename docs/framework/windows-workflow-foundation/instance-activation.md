---
title: Instanzaktivierung
ms.date: 03/30/2017
ms.assetid: 134c3f70-5d4e-46d0-9d49-469a6643edd8
ms.openlocfilehash: 1fd30d9d440c06c03e726ed1f1ddbebb0d5f7e8c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279934"
---
# <a name="instance-activation"></a>Instanzaktivierung

Der SQL-Workflowinstanzspeicher führt eine interne Aufgabe aus, die in regelmäßigen Abständen aktiviert wird und ausführbare oder aktivierbare Workflowinstanzen in der Persistenzdatenbank ermittelt. Wenn eine ausführbare Workflowinstanz gefunden wird, erfolgt die Benachrichtigung des Workflowhosts, der die Instanz aktivieren kann. Wenn der Instanzspeicher eine aktivierbare Workflowinstanz findet, wird ein generischer Host benachrichtigt, der einen Workflowhost aktiviert, der wiederum die Workflowinstanz ausführt. In den folgenden Abschnitten dieses Themas wird der Instanzaktivierungsprozess detailliert erläutert.  
  
## <a name="detecting-and-activating-runnable-workflow-instances"></a><a name="RunnableSection"></a> Erkennen und Aktivieren von ausführbaren Workflow Instanzen  

 Der SQL-workflowinstanzspeicher berücksichtigt eine Ausführ *Bare* Workflow Instanz, wenn die Instanz nicht den Status "angehalten" oder "abgeschlossen" aufweist und die folgenden Bedingungen erfüllt:  
  
- Die Instanz ist nicht gesperrt und weist einen ausstehenden Timer auf, der abgelaufen ist.  
  
- Die Instanz weist eine abgelaufene Sperre auf.  
  
- Die Instanz ist entsperrt, und Ihr Status lautet "wird **ausgeführt**".  
  
 Der SQL-Workflowinstanzspeicher löst das <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> aus, wenn eine ausführbare Instanz gefunden wird. Anschließend wird die Überwachung gestoppt, bis <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand> einmal für den Speicher aufgerufen wird.  
  
 Ein Workflowhost, der das <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent>-Element abonniert hat und die Instanz laden kann, führt das <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>-Element für den Instanzspeicher aus, um die Instanz in den Arbeitsspeicher zu laden. Ein Workflow Host ist als in der Lage, eine Workflow Instanz zu laden, wenn für den Host und die Instanz die Metadateneigenschaft " **workflowservicetype** " auf denselben Wert festgelegt ist.  
  
## <a name="detecting-and-activating-activatable-workflow-instances"></a>Erkennen und Aktivieren von aktivierbaren Workflowinstanzen  

 Eine Workflow Instanz gilt als *aktivierbar* , wenn die Instanz ausgeführt werden kann, und es ist kein Workflow Host vorhanden, der die Instanz laden kann, die auf dem Computer ausgeführt wird. Die Definition einer ausführbaren Workflowinstanz finden Sie weiter oben unter "Erkennen und Aktivieren von ausführbaren Workflowinstanzen".  
  
 Der SQL-Workflowinstanzspeicher löst das <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> aus, wenn eine aktivierbare Workflowinstanz in der Datenbank gefunden wird. Anschließend wird die Überwachung gestoppt, bis <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand> einmal für den Speicher aufgerufen wird.  
  
 Wenn ein generischer Host, der das <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent>-Element abonniert hat, das Ereignis empfängt, wird das <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>-Element für den Instanzspeicher ausgeführt, um die zur Erstellung eines Workflowhosts erforderlichen Aktivierungsparameter abzurufen. Der generische Host erstellt mit diesen Aktivierungsparametern einen Workflowhost, der die ausführbare Dienstinstanz dann lädt und ausführt.  
  
## <a name="generic-hosts"></a>Generische Hosts  

 Ein generischer Host ist ein Host mit dem Wert der Metadateneigenschaft **workflowservicetype** für generische Hosts ist auf **workflowservicetype. Any** festgelegt, um anzugeben, dass der Workflow Typ verarbeitet werden kann. Ein generischer Host hat einen XName-Parameter mit dem Namen **ActivationType**.  
  
 Zurzeit unterstützt der SQL-workflowinstanzspeicher generische Hosts, deren Wert dem ActivationType-Parameter auf **was** festgelegt ist. Wenn der ActivationType-Parameter nicht den Wert WAS aufweist, löst der SQL-Workflowinstanzspeicher einen <xref:System.Runtime.DurableInstancing.InstancePersistenceException>-Fehler aus. Der Workflow Verwaltungsdienst, der mit den Hostingfeatures von Windows Server AppFabric ausgeliefert wird, ist ein generischer Host, dessen Aktivierungstyp auf **was** festgelegt ist.  
  
 Zur WAS-Aktivierung erfordert ein generischer Host einen Satz von Aktivierungsparametern, um die Endpunktadresse abzuleiten, an der neue Hosts aktiviert werden können. Die Aktivierungsparameter zu WAS-Aktivierung sind der Name der Site, der Anwendungspfad relativ zur Website und der Dienstpfad relativ zur Anwendung. Der SQL-Workflowinstanzspeicher speichert diese Aktivierungsparameter während der Ausführung des <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>-Objekts.  
  
## <a name="runnable-instances-detection-period"></a>Runnable Instances Detection Period  

 Die Eigenschaft Ausführungs Zeitraum für Ausführ **Bare Instanzen** des SQL-workflowinstanzspeichers gibt den Zeitraum an, nach dem der SQL-workflowinstanzspeicher eine Erkennungs Aufgabe ausführt, um ausführbare oder aktivierbare Workflow Instanzen in der Persistenzdatenbank nach dem vorherigen Erkennungs Durchlauf zu erkennen. Weitere Informationen zu dieser Eigenschaft finden Sie unter [Ermittlungs Zeitraum für ausführbare Instanzen](runnable-instances-detection-period.md) .
