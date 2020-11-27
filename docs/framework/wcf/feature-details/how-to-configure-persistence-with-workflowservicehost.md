---
title: 'Vorgehensweise: Konfigurieren der Persistenz mit WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 3d8b7183b11c138b8da1f04d9084f8b94b7dcaa6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257339"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a><span data-ttu-id="82181-102">Vorgehensweise: Konfigurieren der Persistenz mit WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="82181-102">How to: Configure Persistence with WorkflowServiceHost</span></span>

<span data-ttu-id="82181-103">In diesem Thema wird beschrieben, wie Sie die Funktion „SQL-Workflowinstanzspeicher“ konfigurieren, um die Beibehaltung für Workflows zu aktivieren, die in <xref:System.ServiceModel.Activities.WorkflowServiceHost> mit einer Konfigurationsdatei gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="82181-103">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for workflows hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> by using a configuration file.</span></span> <span data-ttu-id="82181-104">Vor dem Verwenden der Funktion „SQL-Workflowinstanzspeicher“ müssen Sie eine SQL-Datenbank erstellen, die verwendet wird, um Workflowinstanzen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="82181-104">Before using the SQL Workflow Instance Store feature you must create a SQL database that is used to persist workflow instances.</span></span> <span data-ttu-id="82181-105">Weitere Informationen finden Sie unter Gewusst [wie: Aktivieren der SQL-Persistenz für Workflows und Workflow Dienste](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="82181-105">For more information, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a><span data-ttu-id="82181-106">So konfigurieren Sie den SQL-Workflowinstanzspeicher in einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="82181-106">To Configure the SQL Workflow Instance Store in Configuration</span></span>  
  
1. <span data-ttu-id="82181-107">Die Eigenschaften des SQL-Workflowinstanzspeichers können mithilfe von <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> konfiguriert werden. Dabei handelt es sich um ein Dienstverhalten, mit dem Sie die Einstellungen per XML-Konfiguration ändern können.</span><span class="sxs-lookup"><span data-stu-id="82181-107">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through XML configuration.</span></span> <span data-ttu-id="82181-108">Im folgenden Konfigurationsbeispiel wird gezeigt, wie der SQL-workflowinstanzspeicher mithilfe des <`sqlWorkflowInstanceStore`> Behavior-Elements in einer Konfigurationsdatei konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="82181-108">The following configuration example shows how to configure the SQL workflow instance store by using the <`sqlWorkflowInstanceStore`> behavior element in a configuration file.</span></span>  
  
    ```xml  
    <serviceBehaviors>  
        <behavior name="">  
            <sqlWorkflowInstanceStore
                 connectionString="provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                 instanceEncodingOption="GZip | None"  
                 instanceCompletionAction="DeleteAll | DeleteNothing"  
                 instanceLockedExceptionAction="NoRetry | SimpleRetry | AggressiveRetry"  
                 hostLockRenewalPeriod="00:00:30"
                 runnableInstancesDetectionPeriod="00:00:05">  
            </sqlWorkflowInstanceStore>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     <span data-ttu-id="82181-109">Weitere Informationen zum Konfigurieren des SQL-workflowinstanzspeichers finden Sie unter Gewusst [wie: Aktivieren der SQL-Persistenz für Workflows und Workflow Dienste](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="82181-109">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="82181-110">Weitere Informationen zu den einzelnen Einstellungen für das <`sqlWorkflowInstanceStore`> Behavior-Element finden Sie unter SQL-workflowinstanzspeicher. [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md)</span><span class="sxs-lookup"><span data-stu-id="82181-110">For more information about the individual settings for the <`sqlWorkflowInstanceStore`> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="82181-111">Windows Server AppFabric stellt einen eigenen Persistenzspeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="82181-111">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="82181-112">Weitere Informationen finden Sie unter [Windows Server App Fabric-Persistenz](/previous-versions/appfabric/ee677272(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="82181-112">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="82181-113">Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="82181-113">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="82181-114">Weitere Informationen finden Sie unter [vereinfachte Konfiguration](../simplified-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="82181-114">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a><span data-ttu-id="82181-115">So konfigurieren Sie den SQL-Workflowinstanzspeicher in Code</span><span class="sxs-lookup"><span data-stu-id="82181-115">To Configure the SQL Workflow Instance Store in Code</span></span>  
  
1. <span data-ttu-id="82181-116">Die Eigenschaften des SQL-Workflowinstanzspeichers können mithilfe von <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> konfiguriert werden. Dabei handelt es sich um ein Dienstverhalten, mit dem Sie die Einstellungen per Code ändern können.</span><span class="sxs-lookup"><span data-stu-id="82181-116">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through code.</span></span> <span data-ttu-id="82181-117">Im folgenden Beispiel wird gezeigt, wie Sie den SQL-Workflowinstanzspeicher konfigurieren, indem Sie das <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>-Verhaltenselement in Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="82181-117">The following example shows how to configure the SQL workflow instance store by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element in a code</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new SqlWorkflowInstanceStoreBehavior  
    {  
       ConnectionString = "provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true",  
       InstanceEncodingOption = "GZip | None",  
       InstanceCompletionAction = "DeleteAll | DeleteNothing",  
       InstanceLockedExceptionAction = "NoRetry | SimpleRetry | AggressiveRetry",  
       HostLockRenewalPeriod = new TimeSpan(00, 00, 30),  
       RunnableInstancesDetectionPeriod = new TimeSpan(00, 00, 05)  
    });  
    ```  
  
     <span data-ttu-id="82181-118">Weitere Informationen zum Konfigurieren des SQL-workflowinstanzspeichers finden Sie unter Gewusst [wie: Aktivieren der SQL-Persistenz für Workflows und Workflow Dienste](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="82181-118">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="82181-119">Weitere Informationen zu den einzelnen Einstellungen für das <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> Behavior-Element finden Sie unter SQL-workflowinstanzspeicher [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="82181-119">For more information about the individual settings for the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="82181-120">Windows Server AppFabric stellt einen eigenen Persistenzspeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="82181-120">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="82181-121">Weitere Informationen finden Sie unter [Windows Server App Fabric-Persistenz](/previous-versions/appfabric/ee677272(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="82181-121">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="82181-122">Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="82181-122">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="82181-123">Weitere Informationen finden Sie unter [vereinfachte Konfiguration](../simplified-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="82181-123">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
     <span data-ttu-id="82181-124">Ein Beispiel für die programmgesteuerte Konfiguration der Persistenz finden Sie unter Gewusst [wie: Aktivieren der Persistenz für Workflows und Workflow Dienste](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="82181-124">For an example of how to configure persistence programmatically see [How to: Enable Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82181-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82181-125">See also</span></span>

- [<span data-ttu-id="82181-126">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="82181-126">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="82181-127">Workflowpersistenz</span><span class="sxs-lookup"><span data-stu-id="82181-127">Workflow Persistence</span></span>](../../windows-workflow-foundation/workflow-persistence.md)
- <span data-ttu-id="82181-128">[Windows Server AppFabric-Persistenz](/previous-versions/appfabric/ee677272(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="82181-128">[Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10))</span></span>
