---
title: Initialisierung der Instanziierung
ms.date: 03/30/2017
ms.assetid: 154d049f-2140-4696-b494-c7e53f6775ef
ms.openlocfilehash: ae01254760219f2b408ef9d9663c4158e2802be8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="instancing-initialization"></a><span data-ttu-id="355bc-102">Initialisierung der Instanziierung</span><span class="sxs-lookup"><span data-stu-id="355bc-102">Instancing Initialization</span></span>
<span data-ttu-id="355bc-103">Dieses Beispiel erweitert die [Pooling](../../../../docs/framework/wcf/samples/pooling.md) durch Definieren einer Schnittstelle Sample `IObjectControl`, die passt die Initialisierung eines Objekts durch das Aktivieren und deaktivieren es an.</span><span class="sxs-lookup"><span data-stu-id="355bc-103">This sample extends the [Pooling](../../../../docs/framework/wcf/samples/pooling.md) sample by defining an interface, `IObjectControl`, which customizes the initialization of an object by activating and deactivating it.</span></span> <span data-ttu-id="355bc-104">Der Client ruft Methoden auf, die das Objekt an den Pool zurückgeben und das Objekt nicht an den Pool zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="355bc-104">The client invokes methods that return the object to the pool and that do not return the object to the pool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="355bc-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="355bc-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="extensibility-points"></a><span data-ttu-id="355bc-106">Erweiterungspunkte</span><span class="sxs-lookup"><span data-stu-id="355bc-106">Extensibility Points</span></span>  
 <span data-ttu-id="355bc-107">Der erste Schritt beim Erstellen einer Windows Communication Foundation (WCF)-Erweiterung ist die zu verwendenden Erweiterungspunkt entscheiden.</span><span class="sxs-lookup"><span data-stu-id="355bc-107">The first step in creating a Windows Communication Foundation (WCF) extension is to decide the extensibility point to use.</span></span> <span data-ttu-id="355bc-108">In WCF der Begriff *EndpointDispatcher* bezieht sich auf eine Laufzeitkomponente verantwortlich, konvertieren eingehende Nachrichten in Methodenaufrufe für den Dienst des Benutzers konvertiert und Rückgabewerte von dieser Methode in eine ausgehende Nachricht .</span><span class="sxs-lookup"><span data-stu-id="355bc-108">In WCF, the term *EndpointDispatcher* refers to a run-time component responsible for converting incoming messages into method invocations on the user’s service and for converting return values from that method to an outgoing message.</span></span> <span data-ttu-id="355bc-109">Ein WCF-Dienst erstellt einen EndpointDispatcher für jeden Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="355bc-109">A WCF service creates an EndpointDispatcher for each endpoint.</span></span>  
  
 <span data-ttu-id="355bc-110">Der EndpointDispatcher stellt mithilfe der <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>-Klasse die Erweiterung des Endpunktbereichs bereit (für alle vom Dienst empfangenen oder gesendeten Nachrichten).</span><span class="sxs-lookup"><span data-stu-id="355bc-110">The EndpointDispatcher offers endpoint scope (for all messages received or sent by the service) extensibility using the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> class.</span></span> <span data-ttu-id="355bc-111">Mit dieser Klasse können Sie verschiedene Eigenschaften anpassen, die das Verhalten von EndpointDispatcher steuern.</span><span class="sxs-lookup"><span data-stu-id="355bc-111">This class allows you to customize various properties that control the behavior of the EndpointDispatcher.</span></span> <span data-ttu-id="355bc-112">In diesem Beispiel wird in erster Linie die <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>-Eigenschaft behandelt, die auf das Objekt zeigt, das die Instanzen der Dienstklasse bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="355bc-112">This sample focuses on the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property that points to the object that provides the instances of the service class.</span></span>  
  
## <a name="iinstanceprovider"></a><span data-ttu-id="355bc-113">IInstanceProvider</span><span class="sxs-lookup"><span data-stu-id="355bc-113">IInstanceProvider</span></span>  
 <span data-ttu-id="355bc-114">In WCF erstellt EndpointDispatcher Instanzen einer Dienstklasse mithilfe eines Instanz-Anbieters, implementiert die <xref:System.ServiceModel.Dispatcher.IInstanceProvider> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="355bc-114">In WCF, the EndpointDispatcher creates instances of a service class by using an instance provider that implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface.</span></span> <span data-ttu-id="355bc-115">Diese Schnittstelle verfügt über nur zwei Methoden:</span><span class="sxs-lookup"><span data-stu-id="355bc-115">This interface has only two methods:</span></span>  
  
-   <span data-ttu-id="355bc-116"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: Wenn eine Nachricht eingeht, ruft der Verteiler die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>-Methode auf, um eine Instanz der Dienstklasse zum Verarbeiten der Nachricht zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="355bc-116"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: When a message arrives, the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method to create an instance of the service class to process the message.</span></span> <span data-ttu-id="355bc-117">Die Häufigkeit der Aufrufe dieser Methode wird von der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft bestimmt.</span><span class="sxs-lookup"><span data-stu-id="355bc-117">The frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span> <span data-ttu-id="355bc-118">Wenn die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft beispielsweise auf <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType> festgelegt ist, wird eine neue Instanz der Dienstklasse erstellt, um alle eingehenden Nachrichten zu verarbeiten. Daher wird <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> immer dann aufgerufen, wenn eine Nachricht eingeht.</span><span class="sxs-lookup"><span data-stu-id="355bc-118">For example if the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property is set to <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType>, a new instance of service class is created to process each message that arrives, so <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> is called whenever a message arrives.</span></span>  
  
-   <span data-ttu-id="355bc-119"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: Wenn die Dienstinstanz das Verarbeiten der Nachricht abgeschlossen hat, ruft EndpointDispatcher die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="355bc-119"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: When the service instance finishes processing the message, the EndpointDispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method.</span></span> <span data-ttu-id="355bc-120">Wie bei der <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>-Methode wird die Häufigkeit der Aufrufe dieser Methode von der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft bestimmt.</span><span class="sxs-lookup"><span data-stu-id="355bc-120">As in the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method, the frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span>  
  
## <a name="the-object-pool"></a><span data-ttu-id="355bc-121">Der Objektpool</span><span class="sxs-lookup"><span data-stu-id="355bc-121">The Object Pool</span></span>  
 <span data-ttu-id="355bc-122">Die `ObjectPoolInstanceProvider`-Klasse enthält die Implementierung des Objektpools.</span><span class="sxs-lookup"><span data-stu-id="355bc-122">The `ObjectPoolInstanceProvider` class contains the implementation for the object pool.</span></span> <span data-ttu-id="355bc-123">Diese Klasse implementiert die <xref:System.ServiceModel.Dispatcher.IInstanceProvider>-Schnittstelle für die Interaktion mit der Dienstmodellebene.</span><span class="sxs-lookup"><span data-stu-id="355bc-123">This class implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface to interact with the service model layer.</span></span> <span data-ttu-id="355bc-124">Wenn EndpointDispatcher die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>-Methode aufruft, erstellt die benutzerdefinierte Implementierung keine neue Instanz, sondern sucht ein vorhandenes Objekt in einem Pool im Speicher.</span><span class="sxs-lookup"><span data-stu-id="355bc-124">When the EndpointDispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method, instead of creating a new instance, the custom implementation looks for an existing object in an in-memory pool.</span></span> <span data-ttu-id="355bc-125">Wenn eines verfügbar ist, wird es zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="355bc-125">If one is available, it is returned.</span></span> <span data-ttu-id="355bc-126">Andernfalls überprüft `ObjectPoolInstanceProvider`, ob die `ActiveObjectsCount`-Eigenschaft (Anzahl der aus dem Pool zurückgegebenen Objekte) die maximale Poolgröße erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="355bc-126">Otherwise, `ObjectPoolInstanceProvider` checks whether the `ActiveObjectsCount` property (number of objects returned from the pool) has reached the maximum pool size.</span></span> <span data-ttu-id="355bc-127">Wenn dies nicht der Fall ist, wird eine neue Instanz erstellt und an den Aufrufer zurückgegeben, und anschließend wird `ActiveObjectsCount` inkrementiert.</span><span class="sxs-lookup"><span data-stu-id="355bc-127">If not, a new instance is created and returned to the caller and `ActiveObjectsCount` is subsequently incremented.</span></span> <span data-ttu-id="355bc-128">Andernfalls wird eine Objekterstellungsanforderung für einen konfigurierten Zeitraum in die Warteschlange gestellt.</span><span class="sxs-lookup"><span data-stu-id="355bc-128">Otherwise an object creation request is queued for a configured period of time.</span></span> <span data-ttu-id="355bc-129">Die Implementierung für `GetObjectFromThePool` wird im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="355bc-129">The implementation for `GetObjectFromThePool` is shown in the following sample code.</span></span>  
  
```  
private object GetObjectFromThePool()  
{  
    bool didNotTimeout =   
       availableCount.WaitOne(creationTimeout, true);  
    if(didNotTimeout)  
    {  
         object obj = null;  
         lock (poolLock)  
        {  
             if (pool.Count != 0)  
             {  
                   obj = pool.Pop();  
                   activeObjectsCount++;  
             }  
             else if (pool.Count == 0)  
             {  
                   if (activeObjectsCount < maxPoolSize)  
                   {  
                        obj = CreateNewPoolObject();  
                        activeObjectsCount++;  
  
                        #if (DEBUG)  
                        WritePoolMessage(  
                             ResourceHelper.GetString("MsgNewObject"));  
                       #endif  
                   }                          
            }  
           idleTimer.Stop();  
      }  
     // Call the Activate method if possible.  
    if (obj is IObjectControl)  
   {  
         ((IObjectControl)obj).Activate();  
   }  
   return obj;  
}  
throw new TimeoutException(  
ResourceHelper.GetString("ExObjectCreationTimeout"));  
}  
```  
  
 <span data-ttu-id="355bc-130">Die benutzerdefinierte `ReleaseInstance`-Implementierung fügt die freigegebene Instanz dem Pool erneut hinzu und dekrementiert den `ActiveObjectsCount`-Wert.</span><span class="sxs-lookup"><span data-stu-id="355bc-130">The custom `ReleaseInstance` implementation adds the released instance back to the pool and decrements the `ActiveObjectsCount` value.</span></span> <span data-ttu-id="355bc-131">EndpointDispatcher kann diese Methoden von unterschiedlichen Threads aus aufrufen. Daher ist ein synchronisierter Zugriff auf die Member der Klassenebene in der `ObjectPoolInstanceProvider`-Klasse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="355bc-131">The EndpointDispatcher can call these methods from different threads, and therefore synchronized access to the class level members in the `ObjectPoolInstanceProvider` class is required.</span></span>  
  
```  
public void ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        // Check whether the object can be pooled.   
        // Call the Deactivate method if possible.  
        if (instance is IObjectControl)  
        {  
            IObjectControl objectControl = (IObjectControl)instance;  
            objectControl.Deactivate();  
  
            if (objectControl.CanBePooled)  
            {  
                pool.Push(instance);  
  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectPooled"));  
                #endif                          
            }  
            else  
            {  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectWasNotPooled"));  
                #endif  
            }  
        }  
        else  
        {  
            pool.Push(instance);  
  
            #if(DEBUG)  
            WritePoolMessage(  
                ResourceHelper.GetString("MsgObjectPooled"));  
            #endif   
        }  
  
        activeObjectsCount--;  
  
        if (activeObjectsCount == 0)  
        {  
            idleTimer.Start();                       
        }  
    }  
  
    availableCount.Release(1);  
}  
```  
  
 <span data-ttu-id="355bc-132">Die `ReleaseInstance` Methode bietet eine *bereinigungsinitialisierung* Funktion.</span><span class="sxs-lookup"><span data-stu-id="355bc-132">The `ReleaseInstance` method provides a *clean up initialization* feature.</span></span> <span data-ttu-id="355bc-133">Normalerweise wird im Pool eine Mindestanzahl von Objekten für die Lebensdauer des Pools beibehalten.</span><span class="sxs-lookup"><span data-stu-id="355bc-133">Normally the pool maintains a minimum number of objects for the lifetime of the pool.</span></span> <span data-ttu-id="355bc-134">Es kann jedoch Zeiten mit übermäßiger Auslastung geben, für die im Pool zusätzliche Objekte erstellt werden müssen, um die in der Konfiguration festgelegte Höchstgrenze zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="355bc-134">However, there can be periods of excessive usage that require creating additional objects in the pool to reach the maximum limit specified in the configuration.</span></span> <span data-ttu-id="355bc-135">Wenn der Pool weniger aktiv ist, stellen diese überzähligen Objekte einen zusätzlichen Aufwand dar.</span><span class="sxs-lookup"><span data-stu-id="355bc-135">Eventually when the pool becomes less active those surplus objects can become an extra overhead.</span></span> <span data-ttu-id="355bc-136">Wenn `activeObjectsCount` daher 0 (null) erreicht, wird ein Leerlaufzeitgeber gestartet, der einen Bereinigungszyklus auslöst und ausführt.</span><span class="sxs-lookup"><span data-stu-id="355bc-136">Therefore when the `activeObjectsCount` reaches zero an idle timer is started that triggers and performs a clean-up cycle.</span></span>  
  
```  
if (activeObjectsCount == 0)  
{  
    idleTimer.Start();   
}  
```  
  
 <span data-ttu-id="355bc-137">ServiceModel-Ebenenerweiterungen werden mithilfe der folgenden Verhalten verknüpft:</span><span class="sxs-lookup"><span data-stu-id="355bc-137">ServiceModel layer extensions are hooked up using the following behaviors:</span></span>  
  
-   <span data-ttu-id="355bc-138">Dienstverhalten: Diese ermöglichen die Anpassung der ganzen Dienstlaufzeit.</span><span class="sxs-lookup"><span data-stu-id="355bc-138">Service Behaviors: These allow for the customization of the entire service runtime.</span></span>  
  
-   <span data-ttu-id="355bc-139">Endpunktverhalten: Diese ermöglichen das Anpassen eines bestimmten Dienstendpunkts, einschließlich EndpointDispatcher.</span><span class="sxs-lookup"><span data-stu-id="355bc-139">Endpoint Behaviors: These allow for the customization of a particular service endpoint, including the EndpointDispatcher.</span></span>  
  
-   <span data-ttu-id="355bc-140">Vertragsverhalten: Diese ermöglichen das Anpassen von <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Klassen oder <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Klassen auf dem Client bzw. Server.</span><span class="sxs-lookup"><span data-stu-id="355bc-140">Contract Behaviors: These allow for the customization of either <xref:System.ServiceModel.Dispatcher.ClientRuntime> or <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes on the client or the service respectively.</span></span>  
  
-   <span data-ttu-id="355bc-141">Vorgangsverhalten: Diese ermöglichen das Anpassen von <xref:System.ServiceModel.Dispatcher.ClientOperation>-Klassen oder <xref:System.ServiceModel.Dispatcher.DispatchOperation>-Klassen auf dem Client bzw. Server.</span><span class="sxs-lookup"><span data-stu-id="355bc-141">Operation Behaviors: These allow for the customization of either <xref:System.ServiceModel.Dispatcher.ClientOperation> or <xref:System.ServiceModel.Dispatcher.DispatchOperation> classes on the client or the service respectively.</span></span>  
  
 <span data-ttu-id="355bc-142">Für den Zweck einer Objektpoolingerweiterung kann ein Endpunktverhalten oder ein Dienstverhalten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="355bc-142">For the purpose of an object pooling extension, either an endpoint behavior or a service behavior can be created.</span></span> <span data-ttu-id="355bc-143">In diesem Beispiel wird ein Dienstverhalten verwendet, das die Objektpoolingfähigkeit auf alle Endpunkte des Diensts anwendet.</span><span class="sxs-lookup"><span data-stu-id="355bc-143">In this example, we use a service behavior, which applies object pooling ability to every endpoint of the service.</span></span> <span data-ttu-id="355bc-144">Dienstverhaltensweisen werden durch Implementieren der <xref:System.ServiceModel.Description.IServiceBehavior>-Schnittstelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="355bc-144">Service behaviors are created by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface.</span></span> <span data-ttu-id="355bc-145">Es gibt mehrere Möglichkeiten, ServiceModel auf die benutzerdefinierten Verhaltensweisen hinzuweisen:</span><span class="sxs-lookup"><span data-stu-id="355bc-145">There are several ways to make the ServiceModel aware of the custom behaviors:</span></span>  
  
-   <span data-ttu-id="355bc-146">Verwenden eines benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="355bc-146">Using a custom attribute.</span></span>  
  
-   <span data-ttu-id="355bc-147">Imperatives Hinzufügen zur Verhaltensauflistung der Dienstbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="355bc-147">Imperatively adding it to the service description’s behaviors collection.</span></span>  
  
-   <span data-ttu-id="355bc-148">Erweitern der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="355bc-148">Extending the configuration file.</span></span>  
  
 <span data-ttu-id="355bc-149">In diesem Beispiel wird ein benutzerdefiniertes Attribut verwendet.</span><span class="sxs-lookup"><span data-stu-id="355bc-149">This sample uses a custom attribute.</span></span> <span data-ttu-id="355bc-150">Beim Erstellen von <xref:System.ServiceModel.ServiceHost> werden die in der Typdefinition des Diensts verwendeten Attribute untersucht, und die verfügbaren Verhalten werden der Verhaltensauflistung der Dienstbeschreibung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="355bc-150">When the <xref:System.ServiceModel.ServiceHost> is constructed, it examines the attributes used in the service’s type definition and adds the available behaviors to the service description’s behaviors collection.</span></span>  
  
 <span data-ttu-id="355bc-151">Die <xref:System.ServiceModel.Description.IServiceBehavior> Schnittstelle verfügt über drei Methoden: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> `,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> `,` und <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span><span class="sxs-lookup"><span data-stu-id="355bc-151">The <xref:System.ServiceModel.Description.IServiceBehavior> interface has three methods: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>`,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>`,` and <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span></span> <span data-ttu-id="355bc-152">Diese Methoden werden aufgerufen, indem Sie WCF bei der <xref:System.ServiceModel.ServiceHost> initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="355bc-152">These methods are called by WCF when the <xref:System.ServiceModel.ServiceHost> is being initialized.</span></span> <span data-ttu-id="355bc-153"><xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType> wird zuerst aufgerufen. So kann der Dienst auf Inkonsistenzen untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="355bc-153"><xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType> is called first; it allows the service to be inspected for inconsistencies.</span></span> <span data-ttu-id="355bc-154"><xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType> wird danach aufgerufen. Diese Methode ist nur in sehr komplexen Szenarios erforderlich.</span><span class="sxs-lookup"><span data-stu-id="355bc-154"><xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType> is called next; this method is only required in very advanced scenarios.</span></span> <span data-ttu-id="355bc-155"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> wird zuletzt aufgerufen und ist für das Konfigurieren der Laufzeit zuständig.</span><span class="sxs-lookup"><span data-stu-id="355bc-155"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> is called last and is responsible for configuring the runtime.</span></span> <span data-ttu-id="355bc-156">Die folgenden Parameter werden in <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> übergeben:</span><span class="sxs-lookup"><span data-stu-id="355bc-156">The following parameters are passed into <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>:</span></span>  
  
-   <span data-ttu-id="355bc-157">`Description`: Dieser Parameter stellt die Dienstbeschreibung für den gesamten Dienst bereit.</span><span class="sxs-lookup"><span data-stu-id="355bc-157">`Description`: This parameter provides the service description for the entire service.</span></span> <span data-ttu-id="355bc-158">Dies kann verwendet werden, um Beschreibungsdaten über die Endpunkte, Verträge, Bindungen und andere Daten zu dem Dienst zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="355bc-158">This can be used to inspect description data about the service’s endpoints, contracts, bindings, and other data associated with the service.</span></span>  
  
-   <span data-ttu-id="355bc-159">`ServiceHostBase`: Dieser Parameter stellt die <xref:System.ServiceModel.ServiceHostBase> bereit, die gerade initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="355bc-159">`ServiceHostBase`: This parameter provides the <xref:System.ServiceModel.ServiceHostBase> that is currently being initialized.</span></span>  
  
 <span data-ttu-id="355bc-160">In der benutzerdefinierten <xref:System.ServiceModel.Description.IServiceBehavior>-Implementierung wird eine neue Instanz von `ObjectPoolInstanceProvider` instanziiert und der <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>-Eigenschaft in jedem <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> zugewiesen, der <xref:System.ServiceModel.ServiceHostBase> angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="355bc-160">In the custom <xref:System.ServiceModel.Description.IServiceBehavior> implementation, a new instance of `ObjectPoolInstanceProvider` is instantiated and assigned to the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property in each <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> that is attached to the <xref:System.ServiceModel.ServiceHostBase>.</span></span>  
  
```  
public void ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    if (enabled)  
    {  
        // Create an instance of the ObjectPoolInstanceProvider.  
        instanceProvider = new ObjectPoolInstanceProvider(description.ServiceType,  
        maxPoolSize, minPoolSize, creationTimeout);  
  
        // Assign our instance provider to Dispatch behavior in each   
        // endpoint.  
        foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)  
        {  
             ChannelDispatcher cd = cdb as ChannelDispatcher;  
             if (cd != null)  
             {  
                 foreach (EndpointDispatcher ed in cd.Endpoints)  
                 {  
                        ed.DispatchRuntime.InstanceProvider = instanceProvider;  
                 }  
             }  
         }  
     }  
}   
```  
  
 <span data-ttu-id="355bc-161">Neben einer <xref:System.ServiceModel.Description.IServiceBehavior>-Implementierung verfügt die `ObjectPoolingAttribute`-Klasse über mehrere Member zum Anpassen des Objektpools mithilfe der Attributargumente.</span><span class="sxs-lookup"><span data-stu-id="355bc-161">In addition to an <xref:System.ServiceModel.Description.IServiceBehavior> implementation the `ObjectPoolingAttribute` class has several members to customize the object pool using the attribute arguments.</span></span> <span data-ttu-id="355bc-162">Diese Member umfassen `MaxSize`, `MinSize`, `Enabled` und `CreationTimeout` für die Übereinstimmung mit dem von .NET Enterprise Services bereitgestellten Objektpooling-Featuresatz.</span><span class="sxs-lookup"><span data-stu-id="355bc-162">These members include `MaxSize`, `MinSize`, `Enabled` and `CreationTimeout`, to match the object pooling feature set provided by .NET Enterprise Services.</span></span>  
  
 <span data-ttu-id="355bc-163">Objektpooling Verhalten kann jetzt an einen WCF-Dienst hinzugefügt werden, durch das Hinzufügen der dienstimplementierung mit dem neu erstellten, benutzerdefinierten `ObjectPooling` Attribut.</span><span class="sxs-lookup"><span data-stu-id="355bc-163">The object pooling behavior can now be added to a WCF service by annotating the service implementation with the newly created custom `ObjectPooling` attribute.</span></span>  
  
```  
[ObjectPooling(MaxSize=1024, MinSize=10, CreationTimeout=30000]      
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="hooking-activation-and-deactivation"></a><span data-ttu-id="355bc-164">Aktivieren und Deaktivieren von Verknüpfungen</span><span class="sxs-lookup"><span data-stu-id="355bc-164">Hooking Activation and Deactivation</span></span>  
 <span data-ttu-id="355bc-165">Das primäre Ziel des Objektpoolings ist das Optimieren von Objekten mit kurzer Lebensdauer und relativ aufwändiger Erstellung und Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="355bc-165">The primary objective of object pooling is to optimize short-lived objects with relatively expensive creation and initialization.</span></span> <span data-ttu-id="355bc-166">Bei der richtigen Verwendung kann daher eine erhebliche Leistungssteigerung erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="355bc-166">Therefore it can give a dramatic performance boost to an application if properly used.</span></span> <span data-ttu-id="355bc-167">Da das Objekt aus dem Pool zurückgegeben wird, wird der Konstruktor nur einmal aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="355bc-167">Because the object is returned from the pool, the constructor is called only once.</span></span> <span data-ttu-id="355bc-168">Bei einigen Anwendungen ist jedoch eine gewisse Kontrolle erforderlich, damit sie die in einem einzigen Kontext verwendeten Ressourcen initialisieren und bereinigen können.</span><span class="sxs-lookup"><span data-stu-id="355bc-168">However, some applications require some level of control so that they can initialize and clean-up the resources used during a single context.</span></span> <span data-ttu-id="355bc-169">Ein Objekt, das beispielsweise für eine Gruppe von Berechnungen verwendet wird, kann die privaten Felder zurücksetzen, bevor die nächste Berechnung verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="355bc-169">For example, an object being used for a set of calculations can reset its private fields before processing the next calculation.</span></span> <span data-ttu-id="355bc-170">In Enterprise Services wurde diese Art der kontextspezifischen Initialisierung ermöglicht, indem der Objektentwickler die `Activate`-Methode und die `Deactivate`-Methode in der <xref:System.EnterpriseServices.ServicedComponent>-Basisklasse überschreiben konnte.</span><span class="sxs-lookup"><span data-stu-id="355bc-170">Enterprise Services enabled this kind of context-specific initialization by letting the object developer override `Activate` and `Deactivate` methods from the <xref:System.EnterpriseServices.ServicedComponent> base class.</span></span>  
  
 <span data-ttu-id="355bc-171">Der Objektpool ruft die `Activate`-Methode unmittelbar vor dem Zurückgeben des Objekts aus dem Pool auf.</span><span class="sxs-lookup"><span data-stu-id="355bc-171">The object pool calls the `Activate` method just before returning the object from the pool.</span></span> <span data-ttu-id="355bc-172">`Deactivate` wird aufgerufen, wenn das Objekt an den Pool zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="355bc-172">`Deactivate` is called when the object returns back to the pool.</span></span> <span data-ttu-id="355bc-173">Die <xref:System.EnterpriseServices.ServicedComponent>-Basisklasse verfügt außerdem über die `boolean`-Eigenschaft mit der Bezeichnung `CanBePooled`, mit der der Pool darüber benachrichtigt werden kann, ob das Objekt weiter gepoolt werden kann.</span><span class="sxs-lookup"><span data-stu-id="355bc-173">The <xref:System.EnterpriseServices.ServicedComponent> base class also has a `boolean` property called `CanBePooled`, which can be used to notify the pool whether the object can be pooled further.</span></span>  
  
 <span data-ttu-id="355bc-174">Im Beispiel wird eine öffentliche Schnittstelle (`IObjectControl`) deklariert, die über die oben genannten Member verfügt, um diese Funktionalität zu imitieren.</span><span class="sxs-lookup"><span data-stu-id="355bc-174">To mimic this functionality, the sample declares a public interface (`IObjectControl`) that has the aforementioned members.</span></span> <span data-ttu-id="355bc-175">Diese Schnittstelle wird dann von Dienstklassen implementiert, die die kontextspezifische Initialisierung bereitstellen sollen.</span><span class="sxs-lookup"><span data-stu-id="355bc-175">This interface is then implemented by service classes intended to provide context specific initialization.</span></span> <span data-ttu-id="355bc-176">Die <xref:System.ServiceModel.Dispatcher.IInstanceProvider>-Implementierung muss geändert werden, um diese Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="355bc-176">The <xref:System.ServiceModel.Dispatcher.IInstanceProvider> implementation must be modified to meet these requirements.</span></span> <span data-ttu-id="355bc-177">Jetzt, jedes Mal Sie Abrufen eines Objekts durch Aufrufen der `GetInstance` -Methode, müssen Sie überprüfen, ob das Objekt implementiert `IObjectControl.` Wenn dies der Fall ist, müssen Sie Aufrufen der `Activate` Methode entsprechend.</span><span class="sxs-lookup"><span data-stu-id="355bc-177">Now, each time you get an object by calling the `GetInstance` method, you must check whether the object implements `IObjectControl.` If it does, you must call the `Activate` method appropriately.</span></span>  
  
```  
if (obj is IObjectControl)  
{  
    ((IObjectControl)obj).Activate();  
}  
```  
  
 <span data-ttu-id="355bc-178">Beim Zurückgeben eines Objekts an den Pool ist eine Überprüfung für die `CanBePooled`-Eigenschaft erforderlich, bevor das Objekt erneut dem Pool hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="355bc-178">When returning an object to the pool, a check is required for the `CanBePooled` property before adding the object back to the pool.</span></span>  
  
```  
if (instance is IObjectControl)  
{  
    IObjectControl objectControl = (IObjectControl)instance;  
    objectControl.Deactivate();  
    if (objectControl.CanBePooled)  
    {  
       pool.Push(instance);  
    }  
}  
```  
  
 <span data-ttu-id="355bc-179">Da der Dienstentwickler entscheiden kann, ob ein Objekt gepoolt werden kann, kann die Objektanzahl im Pool zu einem bestimmten Zeitpunkt unter dem Mindestwert liegen.</span><span class="sxs-lookup"><span data-stu-id="355bc-179">Because the service developer can decide whether an object can be pooled, the object count in the pool at a given time can go below the minimum size.</span></span> <span data-ttu-id="355bc-180">Sie müssen daher überprüfen, ob die Objektanzahl unter dem Mindestwert liegt, und die erforderliche Initialisierung in der Bereinigungsprozedur ausführen.</span><span class="sxs-lookup"><span data-stu-id="355bc-180">Therefore you must check whether the object count has gone below the minimum level and perform the necessary initialization in the clean-up procedure.</span></span>  
  
```  
// Remove the surplus objects.  
if (pool.Count > minPoolSize)  
{  
  // Clean the surplus objects.  
}                      
else if (pool.Count < minPoolSize)  
{  
  // Reinitialize the missing objects.  
  while(pool.Count != minPoolSize)  
  {  
    pool.Push(CreateNewPoolObject());  
  }  
}  
```  
  
 <span data-ttu-id="355bc-181">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="355bc-181">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="355bc-182">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="355bc-182">Press Enter in each console window to shut down the service and client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="355bc-183">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="355bc-183">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="355bc-184">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="355bc-184">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="355bc-185">Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="355bc-185">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="355bc-186">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="355bc-186">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="355bc-187">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="355bc-187">The samples may already be installed on your machine.</span></span> <span data-ttu-id="355bc-188">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="355bc-188">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="355bc-189">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="355bc-189">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="355bc-190">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="355bc-190">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Initialization`  
  
## <a name="see-also"></a><span data-ttu-id="355bc-191">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="355bc-191">See Also</span></span>
