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
# <a name="non-persisted-workflow-instances"></a><span data-ttu-id="9fc1a-102">Nicht beibehaltene Workflowinstanzen</span><span class="sxs-lookup"><span data-stu-id="9fc1a-102">Non-Persisted Workflow Instances</span></span>
<span data-ttu-id="9fc1a-103">Wenn eine neue Workflowinstanz erstellt wird, deren Zustandsinformationen persistent in <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> gespeichert werden, erstellt der Diensthost einen Eintrag für diesen Dienst im Instanzspeicher.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-103">When a new instance of a workflow is created that persists its state in the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, the service host creates an entry for that service in the instance store.</span></span> <span data-ttu-id="9fc1a-104">Wenn die Workflowinstanz zum ersten Mal persistent gespeichert wird, wird anschließend der derzeitige Zustand der Instanz in <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-104">Subsequently, when the workflow instance is persisted for the first time, the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> stores the current instance state.</span></span> <span data-ttu-id="9fc1a-105">Wenn der Workflow im Windows-Prozessaktivierungsdienst gehostet wird, werden die Bereitstellungsdaten für den Dienst auch dann in den Instanzspeicher geschrieben, wenn die Instanz zum ersten Mal persistent gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-105">If the workflow is hosted in the Windows Process Activation Service, the service deployment data is also written to the instance store when the instance is persisted for the first time.</span></span>  
  
 <span data-ttu-id="9fc1a-106">Solange die Workflowinstanz nicht beibehalten wurde, ist es einem **nicht persistenter** Zustand.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-106">As long as the workflow instance has not been persisted, it is in a **non-persisted** state.</span></span> <span data-ttu-id="9fc1a-107">In diesem Zustand kann die Workflowinstanz bei Wiederherstellung einer Anwendungsdomäne oder einem Ausfall des Hosts oder Computers nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-107">While in this state, the workflow instance cannot be recovered after an application domain recycle, host failure, or computer failure.</span></span>  
  
## <a name="the-non-persisted-state"></a><span data-ttu-id="9fc1a-108">Nicht persistenter Zustand</span><span class="sxs-lookup"><span data-stu-id="9fc1a-108">The Non-Persisted State</span></span>  
 <span data-ttu-id="9fc1a-109">Permanente Workflowinstanzen, die noch nicht persistent gespeichert wurden, behalten in den folgenden Fällen den Zustand nicht persistent bei:</span><span class="sxs-lookup"><span data-stu-id="9fc1a-109">Durable workflow instances that have not been persisted remain in a non-persisted state in the following cases:</span></span>  
  
-   <span data-ttu-id="9fc1a-110">Der Diensthost stürzt ab, bevor die Workflowinstanz zum ersten Mal persistent gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-110">The service host crashes before the workflow instance is persisted for the first time.</span></span> <span data-ttu-id="9fc1a-111">Die Workflowinstanz verbleibt im Instanzspeicher und wird nicht wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-111">The workflow instance remains in the instance store and is not recovered.</span></span> <span data-ttu-id="9fc1a-112">Bei Empfang einer korrelierten Meldung wird die Workflowinstanz erneut aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-112">If a correlated message arrives, the workflow instance becomes active again.</span></span>  
  
-   <span data-ttu-id="9fc1a-113">Es tritt eine nicht behandelte Ausnahme auf, bevor die Workflowinstanz zum ersten Mal persistent gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-113">The workflow instance experiences an exception before it is persisted for the first time.</span></span> <span data-ttu-id="9fc1a-114">Abhängig von der zurückgegebenen <xref:System.Activities.UnhandledExceptionAction> ergeben sich folgende Szenarien:</span><span class="sxs-lookup"><span data-stu-id="9fc1a-114">Depending on the <xref:System.Activities.UnhandledExceptionAction> returned, the following scenarios occur:</span></span>  
  
    -   <span data-ttu-id="9fc1a-115"><xref:System.Activities.UnhandledExceptionAction> ist auf <xref:System.Activities.UnhandledExceptionAction.Abort> festgelegt: Bei einer Ausnahme werden die Bereitstellungsinformationen in den Instanzspeicher geschrieben, und die Workflowinstanz wird aus dem Speicher entladen.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-115"><xref:System.Activities.UnhandledExceptionAction> is set to <xref:System.Activities.UnhandledExceptionAction.Abort>: When an exception occurs, service deployment information is written to the instance store, and the workflow instance is unloaded from memory.</span></span> <span data-ttu-id="9fc1a-116">Die Workflowinstanz verbleibt im nicht persistenten Zustand und kann nicht erneut geladen werden.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-116">The workflow instance remains in a non-persisted state and cannot be reloaded.</span></span>  
  
    -   <span data-ttu-id="9fc1a-117"><xref:System.Activities.UnhandledExceptionAction> ist auf <xref:System.Activities.UnhandledExceptionAction.Cancel> oder <xref:System.Activities.UnhandledExceptionAction.Terminate> festgelegt: Bei einer Ausnahme werden die Bereitstellungsinformationen in den Instanzspeicher geschrieben, und der Zustand der Aktivitätsinstanz wird auf <xref:System.Activities.ActivityInstanceState.Closed> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-117"><xref:System.Activities.UnhandledExceptionAction> is set to <xref:System.Activities.UnhandledExceptionAction.Cancel> or <xref:System.Activities.UnhandledExceptionAction.Terminate>: When an exception occurs, service deployment information is written to the instance store, and the activity instance state is set to <xref:System.Activities.ActivityInstanceState.Closed>.</span></span>  
  
 <span data-ttu-id="9fc1a-118">Um das Risiko bezüglich des Entladens nicht persistenter Workflowinstanzen zu minimieren, wird empfohlen, den Workflow zu einem frühen Zeitpunkt des Lebenszyklus persistent zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-118">To minimize the risk of encountering unloaded non-persisted workflow instances, we recommend persisting the workflow early in its life cycle.</span></span>  
  
## <a name="detection-and-removal-of-non-persisted-instances"></a><span data-ttu-id="9fc1a-119">Erkennen und Entfernen nicht persistenter Instanzen</span><span class="sxs-lookup"><span data-stu-id="9fc1a-119">Detection and Removal of Non-Persisted Instances</span></span>  
 <span data-ttu-id="9fc1a-120"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> entfernt nicht persistent gespeicherte Workflowinstanzen nicht aus dem Instanzspeicher.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-120">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> does not remove any non-persisted workflow instances from the instance store.</span></span> <span data-ttu-id="9fc1a-121">Besitzer von abgelaufenen Sperren, die mit nicht persistent gespeicherten Workflowinstanzen verknüpft sind, werden ebenfalls nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-121">It also does not remove any expired lock owners that have non-persisted workflow instances associated with them.</span></span>  
  
 <span data-ttu-id="9fc1a-122">Es wird empfohlen, den Instanzspeicher vom Administrator in regelmäßigen Abständen auf nicht persistent gespeicherte Instanzen überprüfen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-122">We recommend that the administrator periodically checks the instance store for non-persisted instances.</span></span> <span data-ttu-id="9fc1a-123">Entsprechende Instanzen können vom Administrator aus dem Instanzspeicher entfernt werden, solange feststeht, dass sie keine korrelierten Meldungen empfangen.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-123">Administrators can remove those instances from the instance store as long as they know that this workflow will not receive correlated messages.</span></span> <span data-ttu-id="9fc1a-124">Beispiel: Wenn eine Instanz sich bereits mehrere Monate in der Datenbank befindet und bekannt ist, dass der Workflow in der Regel eine Lebensdauer von einigen Tagen hat, können Sie sicher davon ausgehen, dass es sich um eine initialisierte Instanz handelt, die abgestürzt ist.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-124">For example, if the instance has been in the database for several months and it is known that the workflow typically has a lifetime of several days, it would be safe to assume that this was an initialized instance that had crashed.</span></span>  
  
 <span data-ttu-id="9fc1a-125">Mit folgenden SQL-Abfragen können Sie nach nicht persistent gespeicherten Instanzen im SQL-Workflowinstanzspeicher suchen:</span><span class="sxs-lookup"><span data-stu-id="9fc1a-125">To find non-persisted instances in the SQL Workflow Instance Store you can use the following SQL queries:</span></span>  
  
-   <span data-ttu-id="9fc1a-126">Mit dieser Abfrage wird nach allen Instanzen gesucht, die nicht persistent gespeichert wurden, und die zugehörige ID sowie der Zeitpunkt der Erstellung (in UTC-Zeit) werden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-126">This query finds all instances that have not been persisted, and returns the ID and creation time (stored in UTC time) for them.</span></span>  
  
    ```sql  
    select InstanceId, CreationTime   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0  
    ```  
  
-   <span data-ttu-id="9fc1a-127">Mit dieser Abfrage wird nach allen Instanzen gesucht, die nicht persistent gespeichert wurden und nicht geladen sind, und die zugehörige ID sowie der Zeitpunkt der Erstellung (in UTC-Zeit) werden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-127">This query finds all instances that have not been persisted, and that are not loaded, and returns the ID and creation time (stored in UTC time) for them.</span></span>  
  
    ```sql  
    select InstanceId, CreationTime   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0   
            and CurrentMachine is NULL  
    ```  
  
-   <span data-ttu-id="9fc1a-128">Mit dieser Abfrage wird nach allen angehaltenen Instanzen gesucht, die nicht persistent gespeichert wurden, und die zugehörige ID, der Zeitpunkt der Erstellung (in UTC-Zeit), der Grund für die Unterbrechung und der Name der Ausnahme werden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-128">This query finds all suspended instances that have not been persisted, and returns the ID, creation time (stored in UTC time), suspension reason, and exception name for them.</span></span>  
  
    ```sql  
    select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0   
            and IsSuspended = 1  
    ```  
  
 <span data-ttu-id="9fc1a-129">Gehen Sie beim Löschen nicht persistent gespeicherter Instanzen mit Bedacht vor.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-129">Use care when you are deleting non-persisted instances.</span></span> <span data-ttu-id="9fc1a-130">Im Allgemeinen ist es sicher, von <xref:System.ServiceModel.Activities.WorkflowServiceHost> erstellte nicht persistente Instanzen zu entfernen, die angehalten wurden oder nicht geladen sind.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-130">In general, it is safe to remove non-persisted instances created by <xref:System.ServiceModel.Activities.WorkflowServiceHost> that are suspended or are not loaded.</span></span> <span data-ttu-id="9fc1a-131">Diese Instanzen können aus dem Speicher entfernt werden, indem sie aus der `[System.Activities.DurableInstancing].[Instances]`-Sicht gelöscht werden. Verwenden Sie dazu den folgenden SQL-Befehl, und geben Sie die korrekte Instanz-ID an.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-131">Those specific instances can be deleted from the store by deleting them from the `[System.Activities.DurableInstancing].[Instances]` view by using the following SQL command, substituting the correct instance ID.</span></span>  
  
```sql  
delete [System.Activities.DurableInstancing].[Instances]   
    where InstanceId=’078a9bc4-ada5-4f9e-8cce-b0eb0009995f’  
```  
  
> [!WARNING]
>  <span data-ttu-id="9fc1a-132">Es wird nicht empfohlen, alle nicht persistent gespeicherten Instanzen zu entfernen, da davon auch Instanzen betroffen sein können, die erst kürzlich erstellt und noch nicht persistent gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="9fc1a-132">We do not recommend removing all non-persisted instances because this includes instances that have just been created and have not yet been persisted.</span></span>
