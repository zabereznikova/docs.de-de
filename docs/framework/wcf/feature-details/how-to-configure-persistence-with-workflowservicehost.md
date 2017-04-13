---
title: "Vorgehensweise: Konfigurieren der Persistenz mit WorkflowServiceHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Vorgehensweise: Konfigurieren der Persistenz mit WorkflowServiceHost
In diesem Thema wird beschrieben, wie Sie die Funktion "SQL\-Workflowinstanzspeicher" konfigurieren, um die Beibehaltung für Workflows zu aktivieren, die in <xref:System.ServiceHost.Activities.WorkflowServiceHost> mit einer Konfigurationsdatei gehostet werden.  Vor dem Verwenden der Funktion "SQL\-Workflowinstanzspeicher" müssen Sie eine SQL\-Datenbank erstellen, die verwendet wird, um Workflowinstanzen beizubehalten.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vorgehensweise: Aktivieren der SQL\-Persistenz für Workflows und Workflowdienste](../../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  
  
### So konfigurieren Sie den SQL\-Workflowinstanzspeicher in einer Konfigurationsdatei  
  
1.  Die Eigenschaften des SQL\-Workflowinstanzspeichers können mithilfe von <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> konfiguriert werden. Dabei handelt es sich um ein Dienstverhalten, mit dem Sie die Einstellungen per XML\-Konfiguration ändern können.  Im folgenden Konfigurationsbeispiel wird gezeigt, wie Sie den SQL\-Workflowinstanzspeicher konfigurieren, indem Sie das \<`sqlWorkflowInstanceStore`\>\-Verhaltenselement in einer Konfigurationsdatei verwenden.  
  
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
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Konfiguration des SQL\-Workflowinstanzspeichers finden Sie unter [Vorgehensweise: Aktivieren der SQL\-Persistenz für Workflows und Workflowdienste](../../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu den einzelnen Einstellungen für das \<`sqlWorkflowInstanceStore`\>\-Verhaltenselement finden Sie unter [SQL\-Workflowinstanzspeicher](../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md).  Windows Server AppFabric stellt einen eigenen Persistenzspeicher bereit.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Persistenzkonzepte](http://go.microsoft.com/fwlink/?LinkId=193121).  
  
    > [!NOTE]
    >  Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md)  
  
### So konfigurieren Sie den SQL\-Workflowinstanzspeicher in Code  
  
1.  Die Eigenschaften des SQL\-Workflowinstanzspeichers können mithilfe von <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> konfiguriert werden. Dabei handelt es sich um ein Dienstverhalten, mit dem Sie die Einstellungen per Code ändern können.  Im folgenden Beispiel wird gezeigt, wie Sie den SQL\-Workflowinstanzspeicher konfigurieren, indem Sie das <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>\-Verhaltenselement in Code verwenden.  
  
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
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Konfiguration des SQL\-Workflowinstanzspeichers finden Sie unter [Vorgehensweise: Aktivieren der SQL\-Persistenz für Workflows und Workflowdienste](../../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu den einzelnen Einstellungen für das <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>\-Verhaltenselement finden Sie unter [SQL\-Workflowinstanzspeicher](../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md).  Windows Server AppFabric stellt einen eigenen Persistenzspeicher bereit.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Persistenzkonzepte](http://go.microsoft.com/fwlink/?LinkId=193121).  
  
    > [!NOTE]
    >  Im vorangehenden Konfigurationsbeispiel wird die vereinfachte Konfiguration verwendet.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md)  
  
     Ein Beispiel für das programmgesteuerte Konfigurieren der Persistenz finden Sie unter [Vorgehensweise: Aktivieren der Persistenz für Workflows und Workflowdienste](../../../../docs/framework/windows-workflow-foundation//how-to-enable-persistence-for-workflows-and-workflow-services.md).  
  
## Siehe auch  
 [Workflowdienste](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Workflowpersistenz](../../../../docs/framework/windows-workflow-foundation//workflow-persistence.md)   
 [Persistenzkonzepte](http://go.microsoft.com/fwlink/?LinkId=193121)