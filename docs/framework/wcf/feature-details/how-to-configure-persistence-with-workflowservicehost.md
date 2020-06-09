---
title: 'Vorgehensweise: Konfigurieren der Persistenz mit WorkflowServiceHost'
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 4ed9c76f091e75cf6ba7658f0314d2e21bbe962e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599112"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a>Vorgehensweise: Konfigurieren der Persistenz mit WorkflowServiceHost
In diesem Thema wird beschrieben, wie Sie die Funktion „SQL-Workflowinstanzspeicher“ konfigurieren, um die Beibehaltung für Workflows zu aktivieren, die in <xref:System.ServiceModel.Activities.WorkflowServiceHost> mit einer Konfigurationsdatei gehostet werden. Vor dem Verwenden der Funktion „SQL-Workflowinstanzspeicher“ müssen Sie eine SQL-Datenbank erstellen, die verwendet wird, um Workflowinstanzen beizubehalten. Weitere Informationen finden Sie unter Gewusst [wie: Aktivieren der SQL-Persistenz für Workflows und Workflow Dienste](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a>So konfigurieren Sie den SQL-Workflowinstanzspeicher in einer Konfigurationsdatei  
  
1. Die Eigenschaften des SQL-Workflowinstanzspeichers können mithilfe von <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> konfiguriert werden. Dabei handelt es sich um ein Dienstverhalten, mit dem Sie die Einstellungen per XML-Konfiguration ändern können. Im folgenden Konfigurationsbeispiel wird gezeigt, wie der SQL-workflowinstanzspeicher mithilfe des <`sqlWorkflowInstanceStore`> Behavior-Elements in einer Konfigurationsdatei konfiguriert wird.  
  
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
  
     Weitere Informationen zum Konfigurieren des SQL-workflowinstanzspeichers finden Sie unter Gewusst [wie: Aktivieren der SQL-Persistenz für Workflows und Workflow Dienste](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md). Weitere Informationen zu den einzelnen Einstellungen für das <`sqlWorkflowInstanceStore`> Behavior-Element finden Sie unter SQL-workflowinstanzspeicher. [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md) Windows Server AppFabric stellt einen eigenen Persistenzspeicher bereit. Weitere Informationen finden Sie unter [Windows Server App Fabric-Persistenz](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10)).  
  
    > [!NOTE]
    > Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet. Weitere Informationen finden Sie unter [vereinfachte Konfiguration](../simplified-configuration.md) .  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a>So konfigurieren Sie den SQL-Workflowinstanzspeicher in Code  
  
1. Die Eigenschaften des SQL-Workflowinstanzspeichers können mithilfe von <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> konfiguriert werden. Dabei handelt es sich um ein Dienstverhalten, mit dem Sie die Einstellungen per Code ändern können. Im folgenden Beispiel wird gezeigt, wie Sie den SQL-Workflowinstanzspeicher konfigurieren, indem Sie das <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>-Verhaltenselement in Code verwenden.  
  
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
  
     Weitere Informationen zum Konfigurieren des SQL-workflowinstanzspeichers finden Sie unter Gewusst [wie: Aktivieren der SQL-Persistenz für Workflows und Workflow Dienste](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md). Weitere Informationen zu den einzelnen Einstellungen für das <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> Behavior-Element finden Sie unter SQL-workflowinstanzspeicher [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md). Windows Server AppFabric stellt einen eigenen Persistenzspeicher bereit. Weitere Informationen finden Sie unter [Windows Server App Fabric-Persistenz](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10)).  
  
    > [!NOTE]
    > Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet. Weitere Informationen finden Sie unter [vereinfachte Konfiguration](../simplified-configuration.md) .  
  
     Ein Beispiel für die programmgesteuerte Konfiguration der Persistenz finden Sie unter Gewusst [wie: Aktivieren der Persistenz für Workflows und Workflow Dienste](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Workflowdienste](workflow-services.md)
- [Workflowpersistenz](../../windows-workflow-foundation/workflow-persistence.md)
- [Windows Server AppFabric-Persistenz](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))
