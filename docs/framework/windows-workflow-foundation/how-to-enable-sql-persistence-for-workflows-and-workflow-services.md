---
title: 'Vorgehensweise: Aktivieren der SQL-Persistenz für Workflows und Workflowdienste'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ca7bf77f-3e5d-4b23-b17a-d0b60f46411d
ms.openlocfilehash: 55869c3c8a957de98962378cc1a93e7058e24e38
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524869"
---
# <a name="how-to-enable-sql-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="8dae6-102">Vorgehensweise: Aktivieren der SQL-Persistenz für Workflows und Workflowdienste</span><span class="sxs-lookup"><span data-stu-id="8dae6-102">How to: Enable SQL Persistence for Workflows and Workflow Services</span></span>

<span data-ttu-id="8dae6-103">In diesem Thema wird beschrieben, wie Sie die Funktion „SQL-Workflowinstanzspeicher“ konfigurieren, um die Persistenz für Workflows und Workflowdienste sowohl programmgesteuert als auch mithilfe einer Konfigurationsdatei zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8dae6-103">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for your workflows and workflow services both programmatically and by using a configuration file.</span></span>  
  
<span data-ttu-id="8dae6-104">Windows Server AppFabric vereinfacht die Konfiguration von Persistenz.</span><span class="sxs-lookup"><span data-stu-id="8dae6-104">Windows Server App Fabric simplifies the process of configuring persistence.</span></span> <span data-ttu-id="8dae6-105">Weitere Informationen finden Sie unter [Persistenz-Fabric-App-Konfiguration](https://go.microsoft.com/fwlink/?LinkId=201204)</span><span class="sxs-lookup"><span data-stu-id="8dae6-105">For more information, see [App Fabric Persistence Configuration](https://go.microsoft.com/fwlink/?LinkId=201204)</span></span>  
  
<span data-ttu-id="8dae6-106">Erstellen Sie vor dem Verwenden der Funktion „SQL-Workflowinstanzspeicher“ eine Datenbank erstellen, die die Funktion zum Beibehalten von Workflowinstanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8dae6-106">Before using the SQL Workflow Instance Store feature, create a database that the feature uses to persist workflow instances.</span></span> <span data-ttu-id="8dae6-107">Das [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Setupprogramm kopiert die SQL-Skriptdateien, die der Funktion "SQL-Workflowinstanzspeicher" zugeordnet sind, in den Ordner "%WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN".</span><span class="sxs-lookup"><span data-stu-id="8dae6-107">The [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] set-up program copies SQL script files associated with the SQL Workflow Instance Store feature to the %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN folder.</span></span> <span data-ttu-id="8dae6-108">Führen Sie diese Skriptdateien für eine SQL Server 2005- oder SQL Server 2008-Datenbank aus, die der SQL-Workflowinstanzspeicher zum Beibehalten von Workflowinstanzen verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="8dae6-108">Run these script files against a SQL Server 2005 or SQL Server 2008 database that you want the SQL Workflow Instance Store to use to persist workflow instances.</span></span> <span data-ttu-id="8dae6-109">Führen Sie zuerst die Datei "SqlWorkflowInstanceStoreSchema.sql" und dann die Datei "SqlWorkflowInstanceStoreLogic.sql" aus.</span><span class="sxs-lookup"><span data-stu-id="8dae6-109">Run the SqlWorkflowInstanceStoreSchema.sql file first and then run the SqlWorkflowInstanceStoreLogic.sql file.</span></span>

> [!NOTE]
> <span data-ttu-id="8dae6-110">Um die Persistenzdatenbank so zu bereinigen, dass sie eine neue Datenbank aufweist, führen Sie die Skripts in "%WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN" in der folgenden Reihenfolge aus.</span><span class="sxs-lookup"><span data-stu-id="8dae6-110">To clean up the persistence database to have a fresh database, run the scripts in %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN in the following order.</span></span>  
>
> 1. <span data-ttu-id="8dae6-111">SqlWorkflowInstanceStoreSchema.sql</span><span class="sxs-lookup"><span data-stu-id="8dae6-111">SqlWorkflowInstanceStoreSchema.sql</span></span>
> 2. <span data-ttu-id="8dae6-112">SqlWorkflowInstanceStoreLogic.sql</span><span class="sxs-lookup"><span data-stu-id="8dae6-112">SqlWorkflowInstanceStoreLogic.sql</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8dae6-113">Wenn Sie keine Persistenzdatenbank erstellen, löst die Funktion "SQL-Workflowinstanzspeicher" eine Ausnahme wie unten angegeben aus, sobald ein Host versucht, Workflows beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="8dae6-113">If you do not create a persistence database, the SQL Workflow Instance Store feature throws an exception similar to the following one when a host tries to persist workflows.</span></span>  
> 
> <span data-ttu-id="8dae6-114">System.Data.SqlClient.SqlException: Die gespeicherte Prozedur "System.Activities.DurableInstancing.CreateLockOwner" wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="8dae6-114">System.Data.SqlClient.SqlException: Could not find stored procedure 'System.Activities.DurableInstancing.CreateLockOwner'</span></span>  

<span data-ttu-id="8dae6-115">In den folgenden Abschnitten wird beschrieben, wie Sie die Persistenz für Workflows und Workflowdienste mithilfe des SQL-Workflowinstanzspeichers aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8dae6-115">The following sections describe how to enable persistence for workflows and workflow services using the SQL Workflow Instance Store.</span></span> <span data-ttu-id="8dae6-116">Weitere Informationen zu Eigenschaften, die von der SQL-Workflow-Instanz-Store finden Sie unter [Eigenschaften des SQL-Workflow-Instanz Store](../../../docs/framework/windows-workflow-foundation/properties-of-sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="8dae6-116">For more information about properties of the SQL Workflow Instance Store, see [Properties of SQL Workflow Instance Store](../../../docs/framework/windows-workflow-foundation/properties-of-sql-workflow-instance-store.md).</span></span>  

## <a name="enabling-persistence-for-self-hosted-workflows-that-use-workflowapplication"></a><span data-ttu-id="8dae6-117">Aktivieren der Persistenz für selbst gehostete Workflows, die WorkflowApplication verwenden</span><span class="sxs-lookup"><span data-stu-id="8dae6-117">Enabling Persistence for Self-Hosted Workflows that use WorkflowApplication</span></span>

<span data-ttu-id="8dae6-118">Sie können die Persistenz für selbst gehostete Workflows aktivieren, die <xref:System.Activities.WorkflowApplication> programmgesteuert nutzen, indem Sie das <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Objektmodell verwenden.</span><span class="sxs-lookup"><span data-stu-id="8dae6-118">You can enable persistence for self-hosted workflows that use <xref:System.Activities.WorkflowApplication> programmatically by using the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> object model.</span></span> <span data-ttu-id="8dae6-119">Die folgende Vorgehensweise enthält die dafür erforderlichen Schritte.</span><span class="sxs-lookup"><span data-stu-id="8dae6-119">The following procedure contains steps to do this.</span></span>  

#### <a name="to-enable-persistence-for-self-hosted-workflows"></a><span data-ttu-id="8dae6-120">So aktivieren Sie Persistenz für selbst gehostete Workflows</span><span class="sxs-lookup"><span data-stu-id="8dae6-120">To enable persistence for self-hosted workflows</span></span>

1.  <span data-ttu-id="8dae6-121">Fügen Sie einen Verweis zu "System.Activites.DurableInstancing.dll" hinzu.</span><span class="sxs-lookup"><span data-stu-id="8dae6-121">Add a reference to System.Activites.DurableInstancing.dll.</span></span>  
  
2.  <span data-ttu-id="8dae6-122">Fügen Sie oben in der Quelldatei nach den vorhandenen using-Anweisungen die folgende Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="8dae6-122">Add the following statement at the top of the source file after the existing "using" statements.</span></span>  
  
    ```csharp  
    using System.Activities.DurableInstancing;  
    ```  
  
3.  <span data-ttu-id="8dae6-123">Erstellen Sie einen <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, und weisen Sie ihn dem<xref:System.Activities.WorkflowApplication.InstanceStore%2A> der <xref:System.Activities.WorkflowApplication> wie im folgenden Codebeispiel dargestellt zu.</span><span class="sxs-lookup"><span data-stu-id="8dae6-123">Construct a <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> and assign it to the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> of the <xref:System.Activities.WorkflowApplication> as shown in the following code example.</span></span>
  
    ```csharp
    SqlWorkflowInstanceStore store =
        new SqlWorkflowInstanceStore("Server=.\\SQLEXPRESS;Initial Catalog=Persistence;Integrated Security=SSPI");

    WorkflowApplication wfApp =
        new WorkflowApplication(new Workflow1());

    wfApp.InstanceStore = store;
    ```
  
   > [!NOTE]
   > <span data-ttu-id="8dae6-124">Abhängig von der SQL Server-Version kann der Servername der Verbindungszeichenfolge abweichen.</span><span class="sxs-lookup"><span data-stu-id="8dae6-124">Depending on your edition of SQL Server, the connection string server name may be different.</span></span>  
  
4. <span data-ttu-id="8dae6-125">Rufen Sie die <xref:System.Activities.WorkflowApplication.Persist%2A>-Methode für das <xref:System.Activities.WorkflowApplication>-Objekt auf, um einen Workflow beizubehalten, oder die <xref:System.Activities.WorkflowApplication.Unload%2A>-Methode, um einen Workflow beizubehalten und zu entladen.</span><span class="sxs-lookup"><span data-stu-id="8dae6-125">Invoke the <xref:System.Activities.WorkflowApplication.Persist%2A> method on the <xref:System.Activities.WorkflowApplication> object to persist a workflow, or <xref:System.Activities.WorkflowApplication.Unload%2A> method to persist and unload a workflow.</span></span> <span data-ttu-id="8dae6-126">Sie können auch das vom <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>-Objekt ausgelöste <xref:System.Activities.WorkflowApplication>-Ereignis behandeln und den entsprechenden Member (<xref:System.Activities.PersistableIdleAction.Persist> oder <xref:System.Activities.PersistableIdleAction.Unload>) von <xref:System.Activities.PersistableIdleAction> zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8dae6-126">You can also handle the <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> event raised by the <xref:System.Activities.WorkflowApplication> object and return appropriate (<xref:System.Activities.PersistableIdleAction.Persist> or <xref:System.Activities.PersistableIdleAction.Unload>) member of <xref:System.Activities.PersistableIdleAction>.</span></span>  
  
   ```csharp
   wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
   {
       return PersistableIdleAction.Persist;
   };
   ```

> [!NOTE]
> <span data-ttu-id="8dae6-127">Finden Sie unter der [beibehalten einer Workflowanwendung](../../../docs/framework/windows-workflow-foundation/samples/persisting-a-workflow-application.md) unter [Persistenz](../../../docs/framework/windows-workflow-foundation/samples/persistence.md) ein Beispiel für die Aktivierung der Persistenz für Workflows mithilfe der <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, und die [Vorgehensweise: Erstellen und führen Sie einen Long-Wert Workflows](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md) Schritt von der [Getting Started Tutorial](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md) Schritt-für-Schritt-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="8dae6-127">See the [Persisting a Workflow Application](../../../docs/framework/windows-workflow-foundation/samples/persisting-a-workflow-application.md) sample at [Persistence](../../../docs/framework/windows-workflow-foundation/samples/persistence.md) for an example of enabling persistence for workflows using the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, and the [How to: Create and Run a Long Running Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md) step of the [Getting Started Tutorial](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md) for step by step instructions.</span></span>  

## <a name="enabling-persistence-for-self-hosted-workflow-services-that-use-the-workflowservicehost"></a><span data-ttu-id="8dae6-128">Aktivieren der Persistenz für selbst gehostete Workflowdienste, die WorkflowServiceHost verwenden</span><span class="sxs-lookup"><span data-stu-id="8dae6-128">Enabling Persistence for Self-Hosted Workflow Services that use the WorkflowServiceHost</span></span>

<span data-ttu-id="8dae6-129">Sie können die Persistenz für selbst gehostete Workflowdienste, die <xref:System.ServiceModel.WorkflowServiceHost> verwenden, mithilfe der <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>-Klasse oder der <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A>-Klasse programmgesteuert aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8dae6-129">You can enable persistence for self-hosted workflow services that use <xref:System.ServiceModel.WorkflowServiceHost> programmatically by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> class or the <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> class.</span></span>  

### <a name="using-the-sqlworkflowinstancestorebehavior-class"></a><span data-ttu-id="8dae6-130">Verwenden der SqlWorkflowInstanceStoreBehavior-Klasse</span><span class="sxs-lookup"><span data-stu-id="8dae6-130">Using the SqlWorkflowInstanceStoreBehavior Class</span></span>  

<span data-ttu-id="8dae6-131">Die folgende Vorgehensweise enthält Schritte zum Verwenden der <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>-Klasse zur Aktivierung der Persistenz für selbst gehostete Workflowdienste.</span><span class="sxs-lookup"><span data-stu-id="8dae6-131">The following procedure contains steps to use the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> class to enable persistence for self-hosted workflow services.</span></span>  

##### <a name="to-enable-persistence-using-sqlworkflowinstancestorebehavior"></a><span data-ttu-id="8dae6-132">So aktivieren Sie die Persistenz mit SqlWorkflowInstanceStoreBehavior</span><span class="sxs-lookup"><span data-stu-id="8dae6-132">To enable persistence using SqlWorkflowInstanceStoreBehavior</span></span>

1.  <span data-ttu-id="8dae6-133">Fügen Sie einen Verweis zu "System.ServiceModel.dll" hinzu.</span><span class="sxs-lookup"><span data-stu-id="8dae6-133">Add a reference to the System.ServiceModel.dll.</span></span>  
  
2.  <span data-ttu-id="8dae6-134">Fügen Sie oben in der Quelldatei nach den vorhandenen using-Anweisungen die folgende Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="8dae6-134">Add the following statement at the top of the source file after the existing "using" statements.</span></span>  
  
    ```csharp
    using System.ServiceModel.Activities.Description;
    ```

3.  <span data-ttu-id="8dae6-135">Erstellen Sie eine Instanz von `WorkflowServiceHost`, und fügen Sie Endpunkte für den Workflowdienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="8dae6-135">Create an instance of the `WorkflowServiceHost` and add endpoints for the workflow service.</span></span>  
  
    ```csharp
    WorkflowServiceHost host = new WorkflowServiceHost(new CountingWorkflow(), new Uri(hostBaseAddress));  
    host.AddServiceEndpoint("ICountingWorkflow", new BasicHttpBinding(), "");  
    ``` 

4.  <span data-ttu-id="8dae6-136">Erstellen Sie ein `SqlWorkflowInstanceStoreBehavior`-Objekt, und legen Sie Eigenschaften des Verhaltensobjekts fest.</span><span class="sxs-lookup"><span data-stu-id="8dae6-136">Construct a `SqlWorkflowInstanceStoreBehavior` object and to set properties of the behavior object.</span></span>  
  
    ```csharp
    SqlWorkflowInstanceStoreBehavior instanceStoreBehavior = new SqlWorkflowInstanceStoreBehavior(connectionString);
    instanceStoreBehavior.HostLockRenewalPeriod = new TimeSpan(0, 0, 5);
    instanceStoreBehavior.InstanceCompletionAction = InstanceCompletionAction.DeleteAll;
    instanceStoreBehavior.InstanceLockedExceptionAction = InstanceLockedExceptionAction.AggressiveRetry;
    instanceStoreBehavior.InstanceEncodingOption = InstanceEncodingOption.GZip;
    instanceStoreBehavior.RunnableInstancesDetectionPeriod = new TimeSpan("00:00:02");
    host.Description.Behaviors.Add(instanceStoreBehavior);
    ```

5.  <span data-ttu-id="8dae6-137">Öffnen Sie den Workflowdiensthost.</span><span class="sxs-lookup"><span data-stu-id="8dae6-137">Open the workflow service host.</span></span>

    ```csharp
    host.Open();
    ```

> [!IMPORTANT]
> <span data-ttu-id="8dae6-138">Finden Sie unter den [integrierte Konfiguration](../../../docs/framework/windows-workflow-foundation/samples/built-in-configuration.md) unter [Persistenz](../../../docs/framework/windows-workflow-foundation/samples/persistence.md) ein Beispiel für die Aktivierung der Persistenz für Workflowdienste mithilfe der `SqlWorkflowInstanceStoreBehavior` Klasse.</span><span class="sxs-lookup"><span data-stu-id="8dae6-138">See the [Built-in Configuration](../../../docs/framework/windows-workflow-foundation/samples/built-in-configuration.md) sample at [Persistence](../../../docs/framework/windows-workflow-foundation/samples/persistence.md) for an example of enabling persistence for workflow services using the `SqlWorkflowInstanceStoreBehavior` class.</span></span>  

### <a name="using-the-durableinstancingoptions-property"></a><span data-ttu-id="8dae6-139">Verwenden der DurableInstancingOptions-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8dae6-139">Using the DurableInstancingOptions Property</span></span>

<span data-ttu-id="8dae6-140">Wenn `SqlWorkflowInstanceStoreBehavior` angewendet wird, wird `DurableInstancingOptions.InstanceStore` auf dem `WorkflowServiceHost` auf das `SqlWorkflowInstanceStore`-Element festgelegt, das anhand der Konfigurationswerte erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8dae6-140">When the `SqlWorkflowInstanceStoreBehavior` is applied, the `DurableInstancingOptions.InstanceStore` on the `WorkflowServiceHost` is set to the `SqlWorkflowInstanceStore` object created using the configuration values.</span></span> <span data-ttu-id="8dae6-141">Dies können Sie auch programmgesteuert erreichen, um die <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A>-Eigenschaft von `WorkflowServiceHost` ohne Verwendung der `SqlWorkflowInstanceStoreBehavior`-Klasse festzulegen, wie im folgenden Codebeispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8dae6-141">You can do the same programmatically to set the <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> property of the `WorkflowServiceHost` without using the `SqlWorkflowInstanceStoreBehavior` class as shown in the following code example.</span></span>  

```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;  
```

## <a name="enabling-persistence-for-was-hosted-workflow-services-that-use-the-workflowservicehost-using-a-configuration-file"></a><span data-ttu-id="8dae6-142">Aktivieren der Persistenz für per WAS gehostete Workflowdienste, die WorkflowServiceHost verwenden, mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="8dae6-142">Enabling Persistence for WAS-Hosted Workflow Services that use the WorkflowServiceHost using a Configuration File</span></span>

<span data-ttu-id="8dae6-143">Sie können die Persistenz für selbst gehostete oder per WAS (Windows Process Activation Service) gehostete Workflowdienste mithilfe einer Konfigurationsdatei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8dae6-143">You can enable persistence for self-hosted or Windows Process Activation Service (WAS)-hosted workflow services by using a configuration file.</span></span> <span data-ttu-id="8dae6-144">Ein per WAS gehosteter Workflowdienst verwendet WorkflowServiceHost, wie selbst gehostete Workflowdienste dies auch tun.</span><span class="sxs-lookup"><span data-stu-id="8dae6-144">A WAS-hosted workflow service uses the WorkflowServiceHost as the self-hosted workflow services do.</span></span>  
  
<span data-ttu-id="8dae6-145">Die `SqlWorkflowInstanceStoreBehavior`, ein Dienstverhalten, das Ihnen ermöglicht, problemlos ändern der [SQL Workflow-Instanz Store](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) Eigenschaften über die XML-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8dae6-145">The `SqlWorkflowInstanceStoreBehavior`, a service behavior that allows you to conveniently change the [SQL Workflow Instance Store](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) properties through XML configuration.</span></span> <span data-ttu-id="8dae6-146">Verwenden Sie für per WAS gehostete Workflowdienste die Datei "Web.config".</span><span class="sxs-lookup"><span data-stu-id="8dae6-146">For WAS-hosted workflow services, use the Web.config file.</span></span> <span data-ttu-id="8dae6-147">Im folgenden Konfigurationsbeispiel wird gezeigt, wie Sie den SQL-Workflowinstanzspeicher konfigurieren, indem Sie das `sqlWorkflowInstanceStore`-Verhaltenselement in einer Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="8dae6-147">The following configuration example shows how to configure the SQL Workflow Instance Store by using the `sqlWorkflowInstanceStore` behavior element in a configuration file.</span></span>  
  
```xml  
<serviceBehaviors>
    <behavior name="">
        <sqlWorkflowInstanceStore 
                    connectionString="Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"
                    instanceEncodingOption="GZip | None"
                    instanceCompletionAction="DeleteAll | DeleteNothing"
                    instanceLockedExceptionAction="NoRetry | BasicRetry |AggressiveRetry"
                    hostLockRenewalPeriod="00:00:30" 
                    runnableInstancesDetectionPeriod="00:00:05">

        <sqlWorkflowInstanceStore/>
    </behavior>
</serviceBehaviors>
```
  
<span data-ttu-id="8dae6-148">Falls Sie keine Werte für die `connectionString`- oder `connectionStringName`-Eigenschaft festlegen, verwendet der SQL-Workflowinstanzspeicher die standardmäßige Verbindungszeichenfolge `DefaultSqlWorkflowInstanceStoreConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="8dae6-148">If you do not set values for the `connectionString` or the `connectionStringName` property, the SQL Workflow Instance Store uses the default named connection string `DefaultSqlWorkflowInstanceStoreConnectionString`.</span></span>  
  
<span data-ttu-id="8dae6-149">Wenn `SqlWorkflowInstanceStoreBehavior` angewendet wird, wird `DurableInstancingOptions.InstanceStore` auf dem `WorkflowServiceHost` auf das `SqlWorkflowInstanceStore`-Element festgelegt, das anhand der Konfigurationswerte erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8dae6-149">When the `SqlWorkflowInstanceStoreBehavior` is applied, the `DurableInstancingOptions.InstanceStore` on the `WorkflowServiceHost` is set to the `SqlWorkflowInstanceStore` object created using the configuration values.</span></span> <span data-ttu-id="8dae6-150">Dies können Sie auch programmgesteuert erreichen, indem Sie `SqlWorkflowInstanceStore` mit `WorkflowServiceHost` und ohne das Dienstverhaltenelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="8dae6-150">You can do the same programmatically to use the `SqlWorkflowInstanceStore` with `WorkflowServiceHost` without using the service behavior element.</span></span>  
  
```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;
```
  
> [!IMPORTANT]
> <span data-ttu-id="8dae6-151">Es wird empfohlen, keine vertraulichen Informationen wie Benutzernamen und Kennwörter in der Datei "Web.config" zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8dae6-151">It is recommended that you do not store sensitive information such as user names and passwords in the Web.config file.</span></span> <span data-ttu-id="8dae6-152">Wenn Sie vertrauliche Informationen in der Datei "Web.config" speichern, sollten Sie den Zugriff auf die Datei "Web.config" mit Dateisystem-ACLs (Zugriffssteuerungslisten) sichern.</span><span class="sxs-lookup"><span data-stu-id="8dae6-152">If you do store sensitive information in the Web.config file, you should secure access to the Web.config file by using file system Access Control Lists (ACLs).</span></span> <span data-ttu-id="8dae6-153">Darüber hinaus können sichern Sie auch die Konfigurationswerte innerhalb einer Konfigurationsdatei wie im [Encrypting Configuration Information mithilfe von geschützten Configuration](https://go.microsoft.com/fwlink/?LinkId=178419).</span><span class="sxs-lookup"><span data-stu-id="8dae6-153">In addition, you can also secure the configuration values within a configuration file as mentioned in [Encrypting Configuration Information Using Protected Configuration](https://go.microsoft.com/fwlink/?LinkId=178419).</span></span>

### <a name="machineconfig-elements-related-to-the-sql-workflow-instance-store-feature"></a><span data-ttu-id="8dae6-154">Auf die Funktion „SQL-Workflowinstanzspeicher“ bezogene Elemente von „Machine.config“</span><span class="sxs-lookup"><span data-stu-id="8dae6-154">Machine.config Elements Related to the SQL Workflow Instance Store Feature</span></span>

<span data-ttu-id="8dae6-155">Die [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]-Installation fügt die folgenden Elemente, die sich auf die Funktion "SQL-Workflowinstanzspeicher" beziehen, der Datei "Machine.config" hinzu:</span><span class="sxs-lookup"><span data-stu-id="8dae6-155">The [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] installation adds the following elements related to the SQL Workflow Instance Store feature to the Machine.config file:</span></span>  

-   <span data-ttu-id="8dae6-156">Fügt der Datei "Machine.config" das folgende Verhaltenserweiterungselement hinzu, damit Sie das <`sqlWorkflowInstanceStore`>-Dienstverhaltenelement in der Konfigurationsdatei verwenden können, um die Persistenz für die Dienste zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8dae6-156">Adds the following behavior extension element to the Machine.config file so that you can use the <`sqlWorkflowInstanceStore`> service behavior element in the configuration file to configure persistence for your services.</span></span>

    ```xml
    <configuration>
        <system.serviceModel>
            <extensions>
                <behaviorExtensions>
                    <add name="sqlWorkflowInstanceStore" type="System.Activities.DurableInstancing.SqlWorkflowInstanceStoreElement, System.Activities.DurableInstancing, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />
                </behaviorExtensions>
            </extensions>
        <system.serviceModel>
    <configuration>
    ```
