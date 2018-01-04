---
title: Nicht beibehaltene Workflowinstanzen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e01af77-6b14-4964-91a5-7dfd143449c0
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54ed92ee666a55b52db22abbbe46922189b3f8fb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="non-persisted-workflow-instances"></a>Nicht beibehaltene Workflowinstanzen
Wenn eine neue Workflowinstanz erstellt wird, deren Zustandsinformationen persistent in <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> gespeichert werden, erstellt der Diensthost einen Eintrag für diesen Dienst im Instanzspeicher. Wenn die Workflowinstanz zum ersten Mal persistent gespeichert wird, wird anschließend der derzeitige Zustand der Instanz in <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> gespeichert. Wenn der Workflow im Windows-Prozessaktivierungsdienst gehostet wird, werden die Bereitstellungsdaten für den Dienst auch dann in den Instanzspeicher geschrieben, wenn die Instanz zum ersten Mal persistent gespeichert wird.  
  
 Solange die Workflowinstanz nicht beibehalten wurde, ist es einem **nicht persistenter** Zustand. In diesem Zustand kann die Workflowinstanz bei Wiederherstellung einer Anwendungsdomäne oder einem Ausfall des Hosts oder Computers nicht wiederhergestellt werden.  
  
## <a name="the-non-persisted-state"></a>Nicht persistenter Zustand  
 Permanente Workflowinstanzen, die noch nicht persistent gespeichert wurden, behalten in den folgenden Fällen den Zustand nicht persistent bei:  
  
-   Der Diensthost stürzt ab, bevor die Workflowinstanz zum ersten Mal persistent gespeichert wurde. Die Workflowinstanz verbleibt im Instanzspeicher und wird nicht wiederhergestellt. Bei Empfang einer korrelierten Meldung wird die Workflowinstanz erneut aktiviert.  
  
-   Es tritt eine nicht behandelte Ausnahme auf, bevor die Workflowinstanz zum ersten Mal persistent gespeichert wurde. Abhängig von der zurückgegebenen <xref:System.Activities.UnhandledExceptionAction> ergeben sich folgende Szenarien:  
  
    -   <xref:System.Activities.UnhandledExceptionAction> ist auf <xref:System.Activities.UnhandledExceptionAction.Abort> festgelegt: Bei einer Ausnahme werden die Bereitstellungsinformationen in den Instanzspeicher geschrieben, und die Workflowinstanz wird aus dem Speicher entladen. Die Workflowinstanz verbleibt im nicht persistenten Zustand und kann nicht erneut geladen werden.  
  
    -   <xref:System.Activities.UnhandledExceptionAction> ist auf <xref:System.Activities.UnhandledExceptionAction.Cancel> oder <xref:System.Activities.UnhandledExceptionAction.Terminate> festgelegt: Bei einer Ausnahme werden die Bereitstellungsinformationen in den Instanzspeicher geschrieben, und der Zustand der Aktivitätsinstanz wird auf <xref:System.Activities.ActivityInstanceState.Closed> festgelegt.  
  
 Um das Risiko bezüglich des Entladens nicht persistenter Workflowinstanzen zu minimieren, wird empfohlen, den Workflow zu einem frühen Zeitpunkt des Lebenszyklus persistent zu speichern.  
  
## <a name="detection-and-removal-of-non-persisted-instances"></a>Erkennen und Entfernen nicht persistenter Instanzen  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> entfernt nicht persistent gespeicherte Workflowinstanzen nicht aus dem Instanzspeicher. Besitzer von abgelaufenen Sperren, die mit nicht persistent gespeicherten Workflowinstanzen verknüpft sind, werden ebenfalls nicht entfernt.  
  
 Es wird empfohlen, den Instanzspeicher vom Administrator in regelmäßigen Abständen auf nicht persistent gespeicherte Instanzen überprüfen zu lassen. Entsprechende Instanzen können vom Administrator aus dem Instanzspeicher entfernt werden, solange feststeht, dass sie keine korrelierten Meldungen empfangen. Beispiel: Wenn eine Instanz sich bereits mehrere Monate in der Datenbank befindet und bekannt ist, dass der Workflow in der Regel eine Lebensdauer von einigen Tagen hat, können Sie sicher davon ausgehen, dass es sich um eine initialisierte Instanz handelt, die abgestürzt ist.  
  
 Mit folgenden SQL-Abfragen können Sie nach nicht persistent gespeicherten Instanzen im SQL-Workflowinstanzspeicher suchen:  
  
-   Mit dieser Abfrage wird nach allen Instanzen gesucht, die nicht persistent gespeichert wurden, und die zugehörige ID sowie der Zeitpunkt der Erstellung (in UTC-Zeit) werden zurückgegeben.  
  
    ```sql  
    select InstanceId, CreationTime   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0  
    ```  
  
-   Mit dieser Abfrage wird nach allen Instanzen gesucht, die nicht persistent gespeichert wurden und nicht geladen sind, und die zugehörige ID sowie der Zeitpunkt der Erstellung (in UTC-Zeit) werden zurückgegeben.  
  
    ```sql  
    select InstanceId, CreationTime   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0   
            and CurrentMachine is NULL  
    ```  
  
-   Mit dieser Abfrage wird nach allen angehaltenen Instanzen gesucht, die nicht persistent gespeichert wurden, und die zugehörige ID, der Zeitpunkt der Erstellung (in UTC-Zeit), der Grund für die Unterbrechung und der Name der Ausnahme werden zurückgegeben.  
  
    ```sql  
    select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0   
            and IsSuspended = 1  
    ```  
  
 Gehen Sie beim Löschen nicht persistent gespeicherter Instanzen mit Bedacht vor. Im Allgemeinen ist es sicher, von <xref:System.ServiceModel.Activities.WorkflowServiceHost> erstellte nicht persistente Instanzen zu entfernen, die angehalten wurden oder nicht geladen sind. Diese Instanzen können aus dem Speicher entfernt werden, indem sie aus der `[System.Activities.DurableInstancing].[Instances]`-Sicht gelöscht werden. Verwenden Sie dazu den folgenden SQL-Befehl, und geben Sie die korrekte Instanz-ID an.  
  
```sql  
delete [System.Activities.DurableInstancing].[Instances]   
    where InstanceId=’078a9bc4-ada5-4f9e-8cce-b0eb0009995f’  
```  
  
> [!WARNING]
>  Es wird nicht empfohlen, alle nicht persistent gespeicherten Instanzen zu entfernen, da davon auch Instanzen betroffen sein können, die erst kürzlich erstellt und noch nicht persistent gespeichert wurden.
