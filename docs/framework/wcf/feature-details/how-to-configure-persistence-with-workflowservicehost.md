---
title: 'Vorgehensweise: Konfigurieren der Persistenz mit WorkflowServiceHost'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: de177180dc22fc3236924da691cf9b1f594519ce
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a><span data-ttu-id="46e08-102">Vorgehensweise: Konfigurieren der Persistenz mit WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="46e08-102">How to: Configure Persistence with WorkflowServiceHost</span></span>
<span data-ttu-id="46e08-103">In diesem Thema wird beschrieben, wie Sie die Funktion "SQL-Workflowinstanzspeicher" konfigurieren, um die Beibehaltung für Workflows zu aktivieren, die in <xref:System.ServiceModel.Activities.WorkflowServiceHost> mit einer Konfigurationsdatei gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="46e08-103">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for workflows hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> by using a configuration file.</span></span> <span data-ttu-id="46e08-104">Vor dem Verwenden der Funktion „SQL-Workflowinstanzspeicher“ müssen Sie eine SQL-Datenbank erstellen, die verwendet wird, um Workflowinstanzen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="46e08-104">Before using the SQL Workflow Instance Store feature you must create a SQL database that is used to persist workflow instances.</span></span> <span data-ttu-id="46e08-105">Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von SQL-Persistenz für Workflows und Workflowdienste](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="46e08-105">For more information, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a><span data-ttu-id="46e08-106">So konfigurieren Sie den SQL-Workflowinstanzspeicher in einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="46e08-106">To Configure the SQL Workflow Instance Store in Configuration</span></span>  
  
1.  <span data-ttu-id="46e08-107">Die Eigenschaften des SQL-Workflowinstanzspeichers können mithilfe von <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> konfiguriert werden. Dabei handelt es sich um ein Dienstverhalten, mit dem Sie die Einstellungen per XML-Konfiguration ändern können.</span><span class="sxs-lookup"><span data-stu-id="46e08-107">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through XML configuration.</span></span> <span data-ttu-id="46e08-108">Im folgenden Konfigurationsbeispiel wird gezeigt, wie Sie den SQL-Workflowinstanzspeicher konfigurieren, indem Sie das <`sqlWorkflowInstanceStore`>-Verhaltenselement in einer Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="46e08-108">The following configuration example shows how to configure the SQL workflow instance store by using the <`sqlWorkflowInstanceStore`> behavior element in a configuration file.</span></span>  
  
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
            <sqlWorkflowInstanceStore/>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     <span data-ttu-id="46e08-109">Weitere Informationen zum Konfigurieren des SQL-workflowinstanzspeichers finden Sie unter [Vorgehensweise: Aktivieren von SQL-Persistenz für Workflows und Workflowdienste](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="46e08-109">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="46e08-110">Weitere Informationen zu den einzelnen Einstellungen für die <`sqlWorkflowInstanceStore`> verhaltenselement, finden Sie unter [SQL-Workflowinstanzspeicher](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="46e08-110">For more information about the individual settings for the <`sqlWorkflowInstanceStore`> behavior element, see [SQL Workflow Instance Store](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="46e08-111">Windows Server AppFabric stellt einen eigenen Persistenzspeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="46e08-111">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="46e08-112">Weitere Informationen finden Sie unter [Windows Server App Fabric-Persistenz](http://go.microsoft.com/fwlink/?LinkId=193121).</span><span class="sxs-lookup"><span data-stu-id="46e08-112">For more information, see [Windows Server App Fabric Persistence](http://go.microsoft.com/fwlink/?LinkId=193121).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="46e08-113">Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="46e08-113">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="46e08-114">Weitere Informationen finden Sie unter [vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="46e08-114">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a><span data-ttu-id="46e08-115">So konfigurieren Sie den SQL-Workflowinstanzspeicher in Code</span><span class="sxs-lookup"><span data-stu-id="46e08-115">To Configure the SQL Workflow Instance Store in Code</span></span>  
  
1.  <span data-ttu-id="46e08-116">Die Eigenschaften des SQL-Workflowinstanzspeichers können mithilfe von <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> konfiguriert werden. Dabei handelt es sich um ein Dienstverhalten, mit dem Sie die Einstellungen per Code ändern können.</span><span class="sxs-lookup"><span data-stu-id="46e08-116">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through code.</span></span> <span data-ttu-id="46e08-117">Im folgenden Beispiel wird gezeigt, wie Sie den SQL-Workflowinstanzspeicher konfigurieren, indem Sie das <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>-Verhaltenselement in Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="46e08-117">The following example shows how to configure the SQL workflow instance store by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element in a code</span></span>  
  
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
  
     <span data-ttu-id="46e08-118">Weitere Informationen zum Konfigurieren des SQL-workflowinstanzspeichers finden Sie unter [Vorgehensweise: Aktivieren von SQL-Persistenz für Workflows und Workflowdienste](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="46e08-118">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="46e08-119">Weitere Informationen zu den einzelnen Einstellungen für die <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> verhaltenselement, finden Sie unter [SQL-Workflowinstanzspeicher](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="46e08-119">For more information about the individual settings for the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element, see [SQL Workflow Instance Store](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="46e08-120">Windows Server AppFabric stellt einen eigenen Persistenzspeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="46e08-120">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="46e08-121">Weitere Informationen finden Sie unter [Windows Server App Fabric-Persistenz](http://go.microsoft.com/fwlink/?LinkId=193121).</span><span class="sxs-lookup"><span data-stu-id="46e08-121">For more information, see [Windows Server App Fabric Persistence](http://go.microsoft.com/fwlink/?LinkId=193121).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="46e08-122">Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="46e08-122">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="46e08-123">Weitere Informationen finden Sie unter [vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="46e08-123">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)</span></span>  
  
     <span data-ttu-id="46e08-124">So konfigurieren Sie die Persistenz programmgesteuert ein Beispiel finden Sie unter [Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="46e08-124">For an example of how to configure persistence programmatically see [How to: Enable Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e08-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46e08-125">See Also</span></span>  
 [<span data-ttu-id="46e08-126">Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="46e08-126">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="46e08-127">Workflowpersistenz</span><span class="sxs-lookup"><span data-stu-id="46e08-127">Workflow Persistence</span></span>](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [<span data-ttu-id="46e08-128">Windows Server AppFabric-Persistenz</span><span class="sxs-lookup"><span data-stu-id="46e08-128">Windows Server App Fabric Persistence</span></span>](http://go.microsoft.com/fwlink/?LinkId=193121)
