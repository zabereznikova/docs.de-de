---
title: 'Vorgehensweise: Erstellen Sie eine benutzerdefinierte Instanz Store'
ms.date: 03/30/2017
ms.assetid: 593c4e9d-8a49-4e12-8257-cee5e6b4c075
ms.openlocfilehash: de3602b928a861500e7984fe88bbb2176d58b840
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503189"
---
# <a name="how-to-create-a-custom-instance-store"></a><span data-ttu-id="55a03-102">Vorgehensweise: Erstellen Sie eine benutzerdefinierte Instanz Store</span><span class="sxs-lookup"><span data-stu-id="55a03-102">How to: Create a Custom Instance Store</span></span>

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="55a03-103">enthält <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, einen Instanzspeicher, der SQL Server verwendet, um Workflowdaten beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="55a03-103">contains <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, an instance store that uses SQL Server to persist workflow data.</span></span> <span data-ttu-id="55a03-104">Wenn die Anwendung Workflowdaten auf einem anderen Medium, z. B. einer anderen Datenbank oder einem anderen Dateisystem dauerhaft speichern muss, können Sie einen benutzerdefinierten Instanzspeicher implementieren.</span><span class="sxs-lookup"><span data-stu-id="55a03-104">If your application is required to persist workflow data to another medium, such as a different database or a file system, you can implement a custom instance store.</span></span> <span data-ttu-id="55a03-105">Ein benutzerdefinierter Instanzspeicher wird erstellt, indem die abstrakte <xref:System.Runtime.DurableInstancing.InstanceStore>-Klasse erweitert wird und die Methoden implementiert werden, die für die Implementierung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="55a03-105">A custom instance store is created by extending the abstract <xref:System.Runtime.DurableInstancing.InstanceStore> class and implementing the methods that are required for the implementation.</span></span> <span data-ttu-id="55a03-106">Eine vollständige Implementierung eines benutzerdefinierten instanzspeichers finden Sie unter den [Unternehmenseinkaufsprozess](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="55a03-106">For a complete implementation of a custom instance store, see the [Corporate Purchase Process](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) sample.</span></span>

## <a name="implementing-the-begintrycommand-method"></a><span data-ttu-id="55a03-107">Implementieren der BeginTryCommand-Methode</span><span class="sxs-lookup"><span data-stu-id="55a03-107">Implementing the BeginTryCommand method</span></span>

<span data-ttu-id="55a03-108"><xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> wird vom Instanzspeicher an das Persistenzmodul gesendet.</span><span class="sxs-lookup"><span data-stu-id="55a03-108">The <xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> is sent to the instance store by the persistence engine.</span></span> <span data-ttu-id="55a03-109">Der Typ des `command`-Parameters gibt an, welcher Befehl ausgeführt wird. Dieser Parameter kann folgende Typen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="55a03-109">The type of the `command` parameter indicates which command is being executed; this parameter can be of the following types:</span></span>

- <span data-ttu-id="55a03-110"><xref:System.Activities.DurableInstancing.SaveWorkflowCommand>: Das persistenzmodul sendet diesen Befehl an den Instanzspeicher, wenn ein Workflow ist auf dem Speichermedium beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="55a03-110"><xref:System.Activities.DurableInstancing.SaveWorkflowCommand>: The persistence engine sends this command to the instance store when a workflow is to be persisted to the storage medium.</span></span> <span data-ttu-id="55a03-111">Die Persistenzdaten des Workflows werden im <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A>-Member des `command`-Parameters für die Methode bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="55a03-111">The workflow persistence data is provided to the method in the <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> member of the `command` parameter.</span></span>

- <span data-ttu-id="55a03-112"><xref:System.Activities.DurableInstancing.LoadWorkflowCommand>: Das persistenzmodul sendet diesen Befehl an den Instanzspeicher, wenn ein Workflow vom Speichermedium geladen werden.</span><span class="sxs-lookup"><span data-stu-id="55a03-112"><xref:System.Activities.DurableInstancing.LoadWorkflowCommand>: The persistence engine sends this command to the instance store when a workflow is to be loaded from the storage medium.</span></span> <span data-ttu-id="55a03-113">Die Instanz-ID des zu ladenden Workflows wird für die Methode im `instanceId`-Parameter der <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A>-Eigenschaft des `context`-Parameters bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="55a03-113">The instance ID of the workflow to be loaded is provided to the method in the `instanceId` parameter of the <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> property of the `context` parameter.</span></span>

- <span data-ttu-id="55a03-114"><xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>: Das persistenzmodul sendet diesen Befehl, um die Instanz zu speichern, wenn eine <xref:System.ServiceModel.Activities.WorkflowServiceHost> muss als sperrbesitzer registriert werden.</span><span class="sxs-lookup"><span data-stu-id="55a03-114"><xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>: The persistence engine sends this command to the instance store when a <xref:System.ServiceModel.Activities.WorkflowServiceHost> must be registered as a lock owner.</span></span> <span data-ttu-id="55a03-115">Die Instanz-ID des aktuellen Workflows sollte für den Instanzspeicher unter Verwendung der <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A>-Methode des `context`-Parameters bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="55a03-115">The instance ID of the current workflow should be provided to the instance store using <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> method of the `context` parameter.</span></span>

     <span data-ttu-id="55a03-116">Der folgende Codeausschnitt zeigt, wie der CreateWorkflowOwner-Befehl implementiert wird, um einen expliziten Sperrbesitzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="55a03-116">The following code snippet demonstrates how to implement the CreateWorkflowOwner command to assign an explicit lock owner.</span></span>

    ```csharp
    XName WFInstanceScopeName = XName.Get(scopeName, "<namespace>");
    ...
    CreateWorkflowOwnerCommand createCommand = new CreateWorkflowOwnerCommand()
    {
        InstanceOwnerMetadata =
        {
            { WorkflowHostTypeName, new InstanceValue(WFInstanceScopeName) },
        }
    };
    InstanceHandle ownerHandle = store.CreateInstanceHandle();
    store.DefaultInstanceOwner = store.Execute(
                                   ownerHandle,
                                   createCommand,
                                   TimeSpan.FromSeconds(30)).InstanceOwner;
    childInstance.AddInitialInstanceValues(new Dictionary<XName, object>() { { WorkflowHostTypeName, WFInstanceScopeName } });
    ```

- <span data-ttu-id="55a03-117"><xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>: Das persistenzmodul sendet diesen Befehl an den Instanzspeicher, wenn die Instanz-ID eines sperrbesitzers aus dem Instanzspeicher entfernt werden kann.</span><span class="sxs-lookup"><span data-stu-id="55a03-117"><xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>: The persistence engine sends this command to the instance store when the instance ID of a lock owner can be removed from the instance store.</span></span> <span data-ttu-id="55a03-118">Wie bei <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand> sollte die ID des Sperrbesitzers von der Anwendung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="55a03-118">As with <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>, the ID of the lock owner should be provided by the application.</span></span>

     <span data-ttu-id="55a03-119">Der folgende Codeausschnitt zeigt, wie eine Sperre mit <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand> aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="55a03-119">The following code snippet demonstrates how to release a lock using <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>.</span></span>

    ```csharp
    static void FreeHandleAndDeleteOwner(InstanceStore store, InstanceHandle handle)
    {
        handle.Free();
        handle = store.CreateInstanceHandle(store.DefaultInstanceOwner);
        try
        {
            // We need this sleep so that we dont prematurely delete the owner, we need time to update the database.
            Thread.Sleep(10000);
            store.Execute(handle, new DeleteWorkflowOwnerCommand(), TimeSpan.FromSeconds(10));
        }
        catch (InstancePersistenceCommandException ex) { Log.Inform(ex.Message); }
        catch (InstanceOwnerException ex) { Log.Inform(ex.Message); }
        catch (OperationCanceledException ex) { Log.Inform(ex.Message); }
        catch (Exception ex) { Log.Inform(ex.Message); }
        finally
        {
            handle.Free();
            store.DefaultInstanceOwner = null;
        }
    }
    ```

     <span data-ttu-id="55a03-120">Die oben dargestellte Methode sollte in einem Try/Catch-Block aufgerufen werden, wenn eine untergeordnete Instanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="55a03-120">The above method should be called in a Try/Catch block when a child instance is run.</span></span>

    ```csharp
    try
    {
        childInstance.Run();
    }
    catch (Exception)
    {
        throw ;
    }
    finally
    {
        FreeHandleAndDeleteOwner(store, ownerHandle);
    }
    ```

- <span data-ttu-id="55a03-121"><xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>: Das persistenzmodul sendet diesen Befehl an den Instanzspeicher, wenn eine Workflowinstanz wird mit Instanzschlüssel des Workflows geladen werden.</span><span class="sxs-lookup"><span data-stu-id="55a03-121"><xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>: The persistence engine sends this command to the instance store when a workflow instance is to be loaded using the workflow’s instance key.</span></span> <span data-ttu-id="55a03-122">Die ID des Instanzschlüssels kann bestimmt werden, indem der <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A>-Parameter des Befehls verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="55a03-122">The ID of the instance key can be determined by using the <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> parameter of the command.</span></span>

- <span data-ttu-id="55a03-123"><xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>: Das persistenzmodul sendet diesen Befehl an den Instanzspeicher aus, um Aktivierungsparameter für beibehaltene Workflows abzurufen, um einen Workflowhost zu erstellen, der dann Workflows laden kann.</span><span class="sxs-lookup"><span data-stu-id="55a03-123"><xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>: The persistence engine sends this command to the instance store to retrieve activation parameters for persisted workflows in order to create a workflow host that can then load workflows.</span></span> <span data-ttu-id="55a03-124">Diesen Befehl sendet die Engine als Reaktion darauf, dass der Instanzspeicher <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> für den Host auslöst, wenn er eine Instanz findet, die aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="55a03-124">This command is sent by the engine in response to the instance store raising the <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> to the host when it locates an instance that can be activated.</span></span> <span data-ttu-id="55a03-125">Der Instanzspeicher sollte abgefragt werden, um zu bestimmen, ob Workflows vorhanden sind, die aktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="55a03-125">The instance store should be polled to determine if there are workflows that can be activated.</span></span>

- <span data-ttu-id="55a03-126"><xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>: Das persistenzmodul sendet diesen Befehl an den Instanzspeicher aus, um ausführbare Workflowinstanzen zu laden.</span><span class="sxs-lookup"><span data-stu-id="55a03-126"><xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>: The persistence engine sends this command to the instance store to load runnable workflow instances.</span></span> <span data-ttu-id="55a03-127">Diesen Befehl sendet die Engine als Reaktion darauf, dass der Instanzspeicher <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> für den Host auslöst, wenn er eine Instanz findet, die ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="55a03-127">This command is sent by the engine in response to the instance store raising the <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> to the host when it locates an instance that can be run.</span></span> <span data-ttu-id="55a03-128">Der Instanzspeicher sollte Workflows abfragen, die ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="55a03-128">The instance store should poll for workflows that can be run.</span></span> <span data-ttu-id="55a03-129">Der folgende Codeausschnitt zeigt, wie ein Instanzspeicher Workflows abfragt, die ausgeführt oder aktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="55a03-129">The following code snippet demonstrates polling an instance store for workflows that can be run or activated.</span></span>

    ```csharp
    public void PollForEvents()
    {
        InstanceOwner[] storeOwners = this.GetInstanceOwners();

        foreach (InstanceOwner owner in storeOwners)
        {
            foreach (InstancePersistenceEvent ppEvent in this.GetEvents(owner))
            {
                if (ppEvent.Equals(HasRunnableWorkflowEvent.Value))
                {
                    bool hasRunnable = GetRunnableEvents(this.StoreId, owner.InstanceOwnerId, isActivatable);
                    if (hasRunnable)
                    {
                        this.SignalEvent(ppEvent, owner);
                    }
                    else
                    {
                        this.ResetEvent(ppEvent, owner);
                    }
                }
                else if(ppEvent.Equals(HasActivatableWorkflowEvent.Value))
                {
                   bool hasActivatable = GetActivatableEvents(this.StoreId, owner.InstanceOwnerId);
                   if (hasActivatable)
                    {
                        this.SignalEvent(ppEvent, owner);
                    }
                    else
                    {
                        this.ResetEvent(ppEvent, owner);
                    }
                }
            }
        }
    }
    ```

     <span data-ttu-id="55a03-130">Im oben stehenden Codeausschnitt fragt der Instanzspeicher die verfügbaren Ereignisse ab und überprüft jedes Ereignis, um zu bestimmen, ob es ein <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent>-Ereignis ist.</span><span class="sxs-lookup"><span data-stu-id="55a03-130">In the above code snippet, the instance store queries the events available and examines each one to determine if it is a <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> event.</span></span> <span data-ttu-id="55a03-131">Wenn ein derartiges Ereignis gefunden wird, wird <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> aufgerufen, um den Host anzuweisen, einen Befehl an den Instanzspeicher zu senden.</span><span class="sxs-lookup"><span data-stu-id="55a03-131">If one is found, <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> is called to signal the host to send a command to the instance store.</span></span> <span data-ttu-id="55a03-132">Der folgende Codeausschnitt zeigt eine Implementierung eines Handlers für diesen Befehl.</span><span class="sxs-lookup"><span data-stu-id="55a03-132">The following code snippet demonstrates an implementation of a handler for this command.</span></span>

    ```csharp
    If (command is TryLoadRunnableWorkflowCommand)
    {
        Owner owner;
        CheckOwner(context, command.Name, out owner);
        // Checking instance.Owner is like an InstanceLockQueryResult.
        context.QueriedInstanceStore(new InstanceLockQueryResult(context.InstanceView.InstanceId, context.InstanceView.InstanceOwner.InstanceOwnerId));

        XName ownerService = null;
        InstanceValue value;
        Instance runnableInstance = default(Instance);
        bool foundRunnableInstance = false;

        value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, owner.Data);
        if (value != null && value.Value is XName)
        {
            ownerService = (XName)value.Value;
        }

        foreach (KeyValuePair<Guid, Instance> instance in MemoryStore.instances)
        {
            if (instance.Value.Owner != Guid.Empty || instance.Value.Completed)
            {
                continue;
            }

            if (ownerService != null)
            {
                value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, instance.Value.Metadata);
                if (value == null || ((XName)value.Value) != ownerService)
                {
                    continue;
                }
            }

            value = QueryPropertyBag(WorkflowServiceNamespace.SuspendReason, instance.Value.Metadata);
            if (value != null && value.Value != null && value.Value is string)
            {
                continue;
            }

            value = QueryPropertyBag(WorkflowNamespace.Status, instance.Value.Data);
            if (value != null && value.Value is string && ((string)value.Value) == "Executing")
            {
                runnableInstance = instance.Value;
                foundRunnableInstance = true;
            }

            if (!foundRunnableInstance)
            {
                value = QueryPropertyBag(XNamespace.Get("urn:schemas-microsoft-com:System.Activities/4.0/properties").GetName("TimerExpirationTime"), instance.Value.Data);
                if (value != null && value.Value is DateTime && ((DateTime)value.Value) <= DateTime.UtcNow)
                {
                    runnableInstance = instance.Value;
                    foundRunnableInstance = true;
                }
            }

            if (foundRunnableInstance)
            {
                runnableInstance.LockVersion++;
                runnableInstance.Owner = context.InstanceView.InstanceOwner.InstanceOwnerId;
                MemoryStore.instances[instance.Key] = runnableInstance;
                context.BindInstance(instance.Key);
                context.BindAcquiredLock(runnableInstance.LockVersion);

                Dictionary<Guid, IDictionary<XName, InstanceValue>> associatedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();
                Dictionary<Guid, IDictionary<XName, InstanceValue>> completedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();
                foreach (KeyValuePair<Guid, Key> keyEntry in MemoryStore.keys)
                {
                if (keyEntry.Value.Instance == context.InstanceView.InstanceId)
                {
                    if (keyEntry.Value.Completed)
                    {
                        completedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));
                    }
                    else
                    {
                        associatedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));
                    }
                }
            }

            context.LoadedInstance(InstanceState.Initialized, DeserializePropertyBag(runnableInstance.Data), DeserializePropertyBag(runnableInstance.Metadata), associatedKeys, completedKeys);
            break;
        }
    }
    ```

    <span data-ttu-id="55a03-133">Im oben stehenden Codeausschnitt sucht der Instanzspeicher ausführbare Instanzen.</span><span class="sxs-lookup"><span data-stu-id="55a03-133">In the above code snippet, the instance store searches for runnable instances.</span></span> <span data-ttu-id="55a03-134">Wenn eine Instanz gefunden wird, wird sie an den Ausführungskontext gebunden und geladen.</span><span class="sxs-lookup"><span data-stu-id="55a03-134">If an instance is found, it is bound to the execution context and loaded.</span></span>

## <a name="using-a-custom-instance-store"></a><span data-ttu-id="55a03-135">Verwenden eines benutzerdefinierten Instanzspeichers</span><span class="sxs-lookup"><span data-stu-id="55a03-135">Using a custom instance store</span></span>

<span data-ttu-id="55a03-136">Um einen benutzerdefinierten Instanzspeicher zu implementieren, weisen Sie <xref:System.Activities.WorkflowApplication.InstanceStore%2A> eine Instanz des Instanzspeichers zu, und implementieren Sie die <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="55a03-136">To implement a custom instance store, assign an instance of the instance store to the <xref:System.Activities.WorkflowApplication.InstanceStore%2A>, and implement the <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> method.</span></span> <span data-ttu-id="55a03-137">Finden Sie unter den [Vorgehensweise: Erstellen und Ausführen einer Workflows mit langer Laufzeit](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md) ausführliche Tutorial.</span><span class="sxs-lookup"><span data-stu-id="55a03-137">See the [How to: Create and Run a Long Running Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md) tutorial for specifics.</span></span>

## <a name="a-sample-instance-store"></a><span data-ttu-id="55a03-138">Beispiel für einen Instanzspeicher</span><span class="sxs-lookup"><span data-stu-id="55a03-138">A sample instance store</span></span>

<span data-ttu-id="55a03-139">Im folgenden Codebeispiel wird eine vollständige Implementierung eines instanzspeichers aus dem [Unternehmenseinkaufsprozess](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="55a03-139">The following code sample is a complete instance store implementation, taken from the [Corporate Purchase Process](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md) sample.</span></span> <span data-ttu-id="55a03-140">Dieser Instanzspeicher speichert Workflowdaten unter Verwendung von XML dauerhaft in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="55a03-140">This instance store persists workflow data to a file using XML.</span></span>

```csharp
using System;
using System.Activities.DurableInstancing;
using System.Collections.Generic;
using System.IO;
using System.Runtime.DurableInstancing;
using System.Runtime.Serialization;
using System.ServiceModel.Persistence;
using System.Xml;
using System.Xml.Linq;

namespace Microsoft.Samples.WF.PurchaseProcess
{

    public class XmlWorkflowInstanceStore : InstanceStore
    {
        Guid ownerInstanceID;

        public XmlWorkflowInstanceStore() : this(Guid.NewGuid())
        {

        }

        public XmlWorkflowInstanceStore(Guid id)
        {
            ownerInstanceID = id;
        }

        //Synchronous version of the Begin/EndTryCommand functions
        protected override bool TryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout)
        {
            return EndTryCommand(BeginTryCommand(context, command, timeout, null, null));
        }

        //The persistence engine will send a variety of commands to the configured InstanceStore,
        //such as CreateWorkflowOwnerCommand, SaveWorkflowCommand, and LoadWorkflowCommand.
        //This method is where we will handle those commands
        protected override IAsyncResult BeginTryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout, AsyncCallback callback, object state)
        {
            IDictionary<XName, InstanceValue> data = null;

            //The CreateWorkflowOwner command instructs the instance store to create a new instance owner bound to the instanace handle
            if (command is CreateWorkflowOwnerCommand)
            {
                context.BindInstanceOwner(ownerInstanceID, Guid.NewGuid());
            }
            //The SaveWorkflow command instructs the instance store to modify the instance bound to the instance handle or an instance key
            else if (command is SaveWorkflowCommand)
            {
                SaveWorkflowCommand saveCommand = (SaveWorkflowCommand)command;
                data = saveCommand.InstanceData;

                Save(data);
            }
            //The LoadWorkflow command instructs the instance store to lock and load the instance bound to the identifier in the instance handle
            else if (command is LoadWorkflowCommand)
            {
                string fileName = IOHelper.GetFileName(this.ownerInstanceID);

                try
                {
                    using (FileStream inputStream = new FileStream(fileName, FileMode.Open))
                    {
                        data = LoadInstanceDataFromFile(inputStream);
                        //load the data into the persistence Context
                        context.LoadedInstance(InstanceState.Initialized, data, null, null, null);
                    }
                }
                catch (Exception exception)
                {
                    throw new PersistenceException(exception.Message);
                }
            }

            return new CompletedAsyncResult<bool>(true, callback, state);
        }

        protected override bool EndTryCommand(IAsyncResult result)
        {
            return CompletedAsyncResult<bool>.End(result);
        }

        //Reads data from xml file and creates a dictionary based off of that.
        IDictionary<XName, InstanceValue> LoadInstanceDataFromFile(Stream inputStream)
        {
            IDictionary<XName, InstanceValue> data = new Dictionary<XName, InstanceValue>();

            NetDataContractSerializer s = new NetDataContractSerializer();

            XmlReader rdr = XmlReader.Create(inputStream);
            XmlDocument doc = new XmlDocument();
            doc.Load(rdr);

            XmlNodeList instances = doc.GetElementsByTagName("InstanceValue");
            foreach (XmlElement instanceElement in instances)
            {
                XmlElement keyElement = (XmlElement)instanceElement.SelectSingleNode("descendant::key");
                XName key = (XName)DeserializeObject(s, keyElement);

                XmlElement valueElement = (XmlElement)instanceElement.SelectSingleNode("descendant::value");
                object value = DeserializeObject(s, valueElement);
                InstanceValue instVal = new InstanceValue(value);

                data.Add(key, instVal);
            }

            return data;
        }

        object DeserializeObject(NetDataContractSerializer serializer, XmlElement element)
        {
            object deserializedObject = null;

            MemoryStream stm = new MemoryStream();
            XmlDictionaryWriter wtr = XmlDictionaryWriter.CreateTextWriter(stm);
            element.WriteContentTo(wtr);
            wtr.Flush();
            stm.Position = 0;

            deserializedObject = serializer.Deserialize(stm);

            return deserializedObject;
        }

        //Saves the persistence data to an xml file.
        void Save(IDictionary<XName, InstanceValue> instanceData)
        {
            string fileName = IOHelper.GetFileName(this.ownerInstanceID);
            XmlDocument doc = new XmlDocument();
            doc.LoadXml("<InstanceValues/>");

            foreach (KeyValuePair<XName,InstanceValue> valPair in instanceData)
            {
                XmlElement newInstance = doc.CreateElement("InstanceValue");

                XmlElement newKey = SerializeObject("key", valPair.Key, doc);
                newInstance.AppendChild(newKey);

                XmlElement newValue = SerializeObject("value", valPair.Value.Value, doc);
                newInstance.AppendChild(newValue);

                doc.DocumentElement.AppendChild(newInstance);
            }
            doc.Save(fileName);
       }

        XmlElement SerializeObject(string elementName, object o, XmlDocument doc)
        {
            NetDataContractSerializer s = new NetDataContractSerializer();
            XmlElement newElement = doc.CreateElement(elementName);
            MemoryStream stm = new MemoryStream();

            s.Serialize(stm, o);
            stm.Position = 0;
            StreamReader rdr = new StreamReader(stm);
            newElement.InnerXml = rdr.ReadToEnd();

            return newElement;
        }
    }
}
```
