---
title: 'Vorgehensweise: Erstellen Sie eine benutzerdefinierte Instanz Store'
ms.date: 03/30/2017
ms.assetid: 593c4e9d-8a49-4e12-8257-cee5e6b4c075
ms.openlocfilehash: cacee7d95a543525ba031de0cc0636d05fc72fc8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707767"
---
# <a name="how-to-create-a-custom-instance-store"></a>Vorgehensweise: Erstellen Sie eine benutzerdefinierte Instanz Store

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] enthält <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, einen Instanzspeicher, der SQL Server verwendet, um Workflowdaten beizubehalten. Wenn die Anwendung Workflowdaten auf einem anderen Medium, z. B. einer anderen Datenbank oder einem anderen Dateisystem dauerhaft speichern muss, können Sie einen benutzerdefinierten Instanzspeicher implementieren. Ein benutzerdefinierter Instanzspeicher wird erstellt, indem die abstrakte <xref:System.Runtime.DurableInstancing.InstanceStore>-Klasse erweitert wird und die Methoden implementiert werden, die für die Implementierung erforderlich sind. Eine vollständige Implementierung eines benutzerdefinierten instanzspeichers finden Sie unter den [Unternehmenseinkaufsprozess](./samples/corporate-purchase-process.md) Beispiel.

## <a name="implementing-the-begintrycommand-method"></a>Implementieren der BeginTryCommand-Methode

<xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> wird vom Instanzspeicher an das Persistenzmodul gesendet. Der Typ des `command`-Parameters gibt an, welcher Befehl ausgeführt wird. Dieser Parameter kann folgende Typen aufweisen:

- <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>: Das persistenzmodul sendet diesen Befehl an den Instanzspeicher, wenn ein Workflow ist auf dem Speichermedium beibehalten werden. Die Persistenzdaten des Workflows werden im <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A>-Member des `command`-Parameters für die Methode bereitgestellt.

- <xref:System.Activities.DurableInstancing.LoadWorkflowCommand>: Das persistenzmodul sendet diesen Befehl an den Instanzspeicher, wenn ein Workflow vom Speichermedium geladen werden. Die Instanz-ID des zu ladenden Workflows wird für die Methode im `instanceId`-Parameter der <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A>-Eigenschaft des `context`-Parameters bereitgestellt.

- <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>: Das persistenzmodul sendet diesen Befehl, um die Instanz zu speichern, wenn eine <xref:System.ServiceModel.Activities.WorkflowServiceHost> muss als sperrbesitzer registriert werden. Die Instanz-ID des aktuellen Workflows sollte für den Instanzspeicher unter Verwendung der <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A>-Methode des `context`-Parameters bereitgestellt werden.

     Der folgende Codeausschnitt zeigt, wie der CreateWorkflowOwner-Befehl implementiert wird, um einen expliziten Sperrbesitzer zuzuweisen.

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

- <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>: Das persistenzmodul sendet diesen Befehl an den Instanzspeicher, wenn die Instanz-ID eines sperrbesitzers aus dem Instanzspeicher entfernt werden kann. Wie bei <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand> sollte die ID des Sperrbesitzers von der Anwendung bereitgestellt werden.

     Der folgende Codeausschnitt zeigt, wie eine Sperre mit <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand> aufgehoben wird.

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

     Die oben dargestellte Methode sollte in einem Try/Catch-Block aufgerufen werden, wenn eine untergeordnete Instanz ausgeführt wird.

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

- <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>: Das persistenzmodul sendet diesen Befehl an den Instanzspeicher, wenn eine Workflowinstanz wird mit Instanzschlüssel des Workflows geladen werden. Die ID des Instanzschlüssels kann bestimmt werden, indem der <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A>-Parameter des Befehls verwendet wird.

- <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>: Das persistenzmodul sendet diesen Befehl an den Instanzspeicher aus, um Aktivierungsparameter für beibehaltene Workflows abzurufen, um einen Workflowhost zu erstellen, der dann Workflows laden kann. Diesen Befehl sendet die Engine als Reaktion darauf, dass der Instanzspeicher <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> für den Host auslöst, wenn er eine Instanz findet, die aktiviert werden kann. Der Instanzspeicher sollte abgefragt werden, um zu bestimmen, ob Workflows vorhanden sind, die aktiviert werden können.

- <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>: Das persistenzmodul sendet diesen Befehl an den Instanzspeicher aus, um ausführbare Workflowinstanzen zu laden. Diesen Befehl sendet die Engine als Reaktion darauf, dass der Instanzspeicher <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> für den Host auslöst, wenn er eine Instanz findet, die ausgeführt werden kann. Der Instanzspeicher sollte Workflows abfragen, die ausgeführt werden können. Der folgende Codeausschnitt zeigt, wie ein Instanzspeicher Workflows abfragt, die ausgeführt oder aktiviert werden können.

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

     Im oben stehenden Codeausschnitt fragt der Instanzspeicher die verfügbaren Ereignisse ab und überprüft jedes Ereignis, um zu bestimmen, ob es ein <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent>-Ereignis ist. Wenn ein derartiges Ereignis gefunden wird, wird <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> aufgerufen, um den Host anzuweisen, einen Befehl an den Instanzspeicher zu senden. Der folgende Codeausschnitt zeigt eine Implementierung eines Handlers für diesen Befehl.

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

    Im oben stehenden Codeausschnitt sucht der Instanzspeicher ausführbare Instanzen. Wenn eine Instanz gefunden wird, wird sie an den Ausführungskontext gebunden und geladen.

## <a name="using-a-custom-instance-store"></a>Verwenden eines benutzerdefinierten Instanzspeichers

Um einen benutzerdefinierten Instanzspeicher zu implementieren, weisen Sie <xref:System.Activities.WorkflowApplication.InstanceStore%2A> eine Instanz des Instanzspeichers zu, und implementieren Sie die <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>-Methode. Finden Sie unter den [Vorgehensweise: Erstellen und Ausführen einer Workflows mit langer Laufzeit](how-to-create-and-run-a-long-running-workflow.md) ausführliche Tutorial.

## <a name="a-sample-instance-store"></a>Beispiel für einen Instanzspeicher

Im folgenden Codebeispiel wird eine vollständige Implementierung eines instanzspeichers aus dem [Unternehmenseinkaufsprozess](./samples/corporate-purchase-process.md) Beispiel. Dieser Instanzspeicher speichert Workflowdaten unter Verwendung von XML dauerhaft in einer Datei.

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
