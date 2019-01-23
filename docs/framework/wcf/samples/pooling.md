---
title: Pooling
ms.date: 03/30/2017
ms.assetid: 688dfb30-b79a-4cad-a687-8302f8a9ad6a
ms.openlocfilehash: 655ef32c039014f446850376e0fe021e79c577c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536324"
---
# <a name="pooling"></a><span data-ttu-id="98362-102">Pooling</span><span class="sxs-lookup"><span data-stu-id="98362-102">Pooling</span></span>
<span data-ttu-id="98362-103">In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF) zur Unterstützung von Objektpooling erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="98362-103">This sample demonstrates how to extend Windows Communication Foundation (WCF) to support object pooling.</span></span> <span data-ttu-id="98362-104">Das Beispiel veranschaulicht die Erstellung eines Attributs, das syntaktisch und semantisch ähnlich zur `ObjectPoolingAttribute`-Attributfunktionalität von Enterprise Services ist.</span><span class="sxs-lookup"><span data-stu-id="98362-104">The sample demonstrates how to create an attribute that is syntactically and semantically similar to the `ObjectPoolingAttribute` attribute functionality of Enterprise Services.</span></span> <span data-ttu-id="98362-105">Durch Objektpooling lässt sich die Leistung einer Anwendung u.&#160;U. drastisch steigern.</span><span class="sxs-lookup"><span data-stu-id="98362-105">Object pooling can provide a dramatic boost to an application's performance.</span></span> <span data-ttu-id="98362-106">Es kann jedoch auch einen gegenteiligen Effekt haben, wenn es nicht ordnungsgemäß verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="98362-106">However, it can have the opposite effect if it is not used properly.</span></span> <span data-ttu-id="98362-107">Objektpooling hilft dabei, den Mehraufwand zu reduzieren, der durch die Neuerstellung häufig verwendeter Objekte, die eine umfangreiche Initialisierung erfordern, entsteht.</span><span class="sxs-lookup"><span data-stu-id="98362-107">Object pooling helps reduce the overhead of recreating frequently used objects that require extensive initialization.</span></span> <span data-ttu-id="98362-108">Wenn das Aufrufen einer Methode in einem gepoolten Objekt jedoch sehr lange dauert, werden durch das Objektpooling zusätzliche Anforderungen in einer Warteschlange platziert, sobald die maximale Poolgröße erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="98362-108">However, if a call to a method on a pooled object takes a considerable amount of time to complete, object pooling queues additional requests as soon as the maximum pool size is reached.</span></span> <span data-ttu-id="98362-109">Daher werden u.&#160;U. einige Anforderungen zur Objekterstellung nicht erfüllt, indem eine Timeoutausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="98362-109">Thus it may fail to serve some object creation requests by throwing a timeout exception.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98362-110">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="98362-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="98362-111">Der erste Schritt beim Erstellen einer WCF-Erweiterung ist die zu verwendenden Erweiterungspunkt entscheiden.</span><span class="sxs-lookup"><span data-stu-id="98362-111">The first step in creating a WCF extension is to decide the extensibility point to use.</span></span>  
  
 <span data-ttu-id="98362-112">In WCF den Begriff *Dispatcher* bezieht sich auf eine Laufzeitkomponente verantwortlich, konvertieren eingehende Nachrichten in Methodenaufrufe für den Dienst des Benutzers konvertiert und Rückgabewerte von dieser Methode zu einer ausgehenden Nachricht.</span><span class="sxs-lookup"><span data-stu-id="98362-112">In WCF the term *dispatcher* refers to a run-time component responsible for converting incoming messages into method invocations on the user’s service and for converting return values from that method to an outgoing message.</span></span> <span data-ttu-id="98362-113">Ein WCF-Dienst erstellt einen Dispatcher für jeden Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="98362-113">A WCF service creates a dispatcher for each endpoint.</span></span> <span data-ttu-id="98362-114">Wenn der diesem Client zugeordnete Vertrag ein Duplexvertrag ist, muss ein WCF-Client einen Verteiler verwenden.</span><span class="sxs-lookup"><span data-stu-id="98362-114">A WCF client must use a dispatcher if the contract associated with that client is a duplex contract.</span></span>  
  
 <span data-ttu-id="98362-115">Der Kanal- und der Endpunktverteiler bieten eine kanal- und vertragsweite Erweiterbarkeit, indem sie verschiedene Eigenschaften, die das Verhalten des Verteilers steuern, verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="98362-115">The channel and endpoint dispatchers offer channel-and contract-wide extensibility by exposing various properties that control the behavior of the dispatcher.</span></span> <span data-ttu-id="98362-116">Die <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.DispatchRuntime%2A>-Eigenschaft ermöglicht es Ihnen außerdem, den Verteilungsprozess zu überprüfen, zu ändern oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="98362-116">The <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.DispatchRuntime%2A> property also enables you to inspect, modify, or customize the dispatching process.</span></span> <span data-ttu-id="98362-117">In diesem Beispiel wird in erster Linie die <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>-Eigenschaft behandelt, die auf das Objekt zeigt, das die Instanzen der Dienstklasse bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="98362-117">This sample focuses on the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property that points to the object that provides the instances of the service class.</span></span>  
  
## <a name="the-iinstanceprovider"></a><span data-ttu-id="98362-118">Der IInstanceProvider</span><span class="sxs-lookup"><span data-stu-id="98362-118">The IInstanceProvider</span></span>  
 <span data-ttu-id="98362-119">In WCF, erstellt der Verteiler die Instanzen der Klasse für den Dienst mithilfe einer <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>, implementiert die <xref:System.ServiceModel.Dispatcher.IInstanceProvider> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="98362-119">In WCF, the dispatcher creates instances of the service class using a <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>, which implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface.</span></span> <span data-ttu-id="98362-120">Diese Schnittstelle verfügt über drei Methoden:</span><span class="sxs-lookup"><span data-stu-id="98362-120">This interface has three methods:</span></span>  
  
-   <span data-ttu-id="98362-121"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>: Wenn eine Nachricht eingeht ruft der Verteiler die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> Methode zum Erstellen einer Instanz der Dienstklasse zum Verarbeiten der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="98362-121"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>: When a message arrives the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> method to create an instance of the service class to process the message.</span></span> <span data-ttu-id="98362-122">Die Häufigkeit der Aufrufe dieser Methode wird von der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft bestimmt.</span><span class="sxs-lookup"><span data-stu-id="98362-122">The frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span> <span data-ttu-id="98362-123">Wenn die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft beispielsweise auf <xref:System.ServiceModel.InstanceContextMode.PerCall> festgelegt ist, wird eine neue Instanz der Dienstklasse erstellt, um alle eingehenden Nachrichten zu verarbeiten. Daher wird <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> immer dann aufgerufen, wenn eine Nachricht eingeht.</span><span class="sxs-lookup"><span data-stu-id="98362-123">For example, if the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property is set to <xref:System.ServiceModel.InstanceContextMode.PerCall> a new instance of service class is created to process each message that arrives, so <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> is called whenever a message arrives.</span></span>  
  
-   <span data-ttu-id="98362-124"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%29>: Dies ist identisch mit der vorherigen Methode, mit der Ausnahme aufgerufen wird, wenn keine Nachrichtenargument vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="98362-124"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%29>: This is identical to the previous method, except this is invoked when there is no Message argument.</span></span>  
  
-   <span data-ttu-id="98362-125"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29>: Wenn die Lebensdauer von einer Dienstinstanz verstrichen ist, ruft der Verteiler die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29> Methode.</span><span class="sxs-lookup"><span data-stu-id="98362-125"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29>: When a service instance's lifetime has elapsed, the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29> method.</span></span> <span data-ttu-id="98362-126">Wie bei der <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>-Methode wird die Häufigkeit der Aufrufe dieser Methode von der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft bestimmt.</span><span class="sxs-lookup"><span data-stu-id="98362-126">Just like for the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> method, the frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span>  
  
## <a name="the-object-pool"></a><span data-ttu-id="98362-127">Der Objektpool</span><span class="sxs-lookup"><span data-stu-id="98362-127">The Object Pool</span></span>  
 <span data-ttu-id="98362-128">Eine benutzerdefinierte <xref:System.ServiceModel.Dispatcher.IInstanceProvider>-Implementierung stellt die erforderliche Objektpoolingsemantik für einen Dienst bereit.</span><span class="sxs-lookup"><span data-stu-id="98362-128">A custom <xref:System.ServiceModel.Dispatcher.IInstanceProvider> implementation provides the required object pooling semantics for a service.</span></span> <span data-ttu-id="98362-129">Deshalb verfügt dieses Beispiel über einen `ObjectPoolingInstanceProvider`-Typ, der eine benutzerdefinierte Implementierung von <xref:System.ServiceModel.Dispatcher.IInstanceProvider> für das Pooling bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="98362-129">Therefore, this sample has an `ObjectPoolingInstanceProvider` type that provides custom implementation of <xref:System.ServiceModel.Dispatcher.IInstanceProvider> for pooling.</span></span> <span data-ttu-id="98362-130">Wenn der `Dispatcher` die <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>-Methode aufruft, erstellt die benutzerdefinierte Implementierung keine neue Instanz, sondern sucht ein vorhandenes Objekt in einem Speicherpool.</span><span class="sxs-lookup"><span data-stu-id="98362-130">When the `Dispatcher` calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> method, instead of creating a new instance, the custom implementation looks for an existing object in an in-memory pool.</span></span> <span data-ttu-id="98362-131">Wenn eines verfügbar ist, wird es zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="98362-131">If one is available, it is returned.</span></span> <span data-ttu-id="98362-132">Andernfalls wird ein neues Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="98362-132">Otherwise, a new object is created.</span></span> <span data-ttu-id="98362-133">Die Implementierung für `GetInstance` wird im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="98362-133">The implementation for `GetInstance` is shown in the following sample code.</span></span>  
  
```  
object IInstanceProvider.GetInstance(InstanceContext instanceContext, Message message)  
{  
    object obj = null;  
  
    lock (poolLock)  
    {  
        if (pool.Count > 0)  
        {  
            obj = pool.Pop();  
        }  
        else  
        {  
            obj = CreateNewPoolObject();  
        }  
        activeObjectsCount++;  
    }  
  
    WritePoolMessage(ResourceHelper.GetString("MsgNewObject"));  
  
    idleTimer.Stop();  
  
    return obj;            
}  
```  
  
 <span data-ttu-id="98362-134">Die benutzerdefinierte `ReleaseInstance`-Implementierung fügt die freigegebene Instanz dem Pool erneut hinzu und dekrementiert den `ActiveObjectsCount`-Wert.</span><span class="sxs-lookup"><span data-stu-id="98362-134">The custom `ReleaseInstance` implementation adds the released instance back to the pool and decrements the `ActiveObjectsCount` value.</span></span> <span data-ttu-id="98362-135">Der `Dispatcher` kann diese Methoden von unterschiedlichen Threads aus aufrufen. Daher ist ein synchronisierter Zugriff auf die Member der Klassenebene in der `ObjectPoolingInstanceProvider`-Klasse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98362-135">The `Dispatcher` can call these methods from different threads, and therefore synchronized access to the class level members in the `ObjectPoolingInstanceProvider` class is required.</span></span>  
  
```  
void IInstanceProvider.ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        pool.Push(instance);  
        activeObjectsCount--;  
  
        WritePoolMessage(  
        ResourceHelper.GetString("MsgObjectPooled"));  
  
        // When the service goes completely idle (no requests   
        // are being processed), the idle timer is started  
        if (activeObjectsCount == 0)  
            idleTimer.Start();                       
    }  
}  
```  
  
 <span data-ttu-id="98362-136">Die `ReleaseInstance` Methode verfügt über eine Funktion "bereinigungsinitialisierung".</span><span class="sxs-lookup"><span data-stu-id="98362-136">The `ReleaseInstance` method provides a "clean up initialization" feature.</span></span> <span data-ttu-id="98362-137">Normalerweise wird im Pool eine Mindestanzahl von Objekten für die Lebensdauer des Pools beibehalten.</span><span class="sxs-lookup"><span data-stu-id="98362-137">Normally the pool maintains a minimum number of objects for the lifetime of the pool.</span></span> <span data-ttu-id="98362-138">Es kann jedoch Zeiten mit übermäßiger Auslastung geben, für die im Pool zusätzliche Objekte erstellt werden müssen, um die in der Konfiguration festgelegte Höchstgrenze zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="98362-138">However, there can be periods of excessive usage that require creating additional objects in the pool to reach the maximum limit specified in the configuration.</span></span> <span data-ttu-id="98362-139">Wenn der Pool weniger aktiv ist, stellen diese überzähligen Objekte einen zusätzlichen Aufwand dar.</span><span class="sxs-lookup"><span data-stu-id="98362-139">Eventually, when the pool becomes less active, those surplus objects can become an extra overhead.</span></span> <span data-ttu-id="98362-140">Wenn `activeObjectsCount` daher 0 (null) erreicht, wird ein Leerlaufzeitgeber gestartet, der einen Bereinigungszyklus auslöst und ausführt.</span><span class="sxs-lookup"><span data-stu-id="98362-140">Therefore, when the `activeObjectsCount` reaches zero, an idle timer is started that triggers and performs a clean-up cycle.</span></span>  
  
## <a name="adding-the-behavior"></a><span data-ttu-id="98362-141">Hinzufügen des Verhaltens</span><span class="sxs-lookup"><span data-stu-id="98362-141">Adding the Behavior</span></span>  
 <span data-ttu-id="98362-142">Verteilerschicht-Erweiterungen werden mithilfe der folgenden Verhaltensweisen verknüpft:</span><span class="sxs-lookup"><span data-stu-id="98362-142">Dispatcher-layer extensions are hooked up using the following behaviors:</span></span>  
  
-   <span data-ttu-id="98362-143">Dienstverhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="98362-143">Service Behaviors.</span></span> <span data-ttu-id="98362-144">Diese ermöglichen die Anpassung der gesamten Dienstlaufzeit.</span><span class="sxs-lookup"><span data-stu-id="98362-144">These allow for the customization of the entire service runtime.</span></span>  
  
-   <span data-ttu-id="98362-145">Endpunktverhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="98362-145">Endpoint Behaviors.</span></span> <span data-ttu-id="98362-146">Diese ermöglichen die Anpassung von Dienstendpunkten, insbesondere eines Kanal- und Endpunktverteilers.</span><span class="sxs-lookup"><span data-stu-id="98362-146">These allow for the customization of service endpoints, specifically a Channel and Endpoint Dispatcher.</span></span>  
  
-   <span data-ttu-id="98362-147">Vertragsverhaltensweisen.</span><span class="sxs-lookup"><span data-stu-id="98362-147">Contract Behaviors.</span></span> <span data-ttu-id="98362-148">Diese ermöglichen die Anpassung sowohl der <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Klasse als auch der <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Klasse im Client bzw. Dienst.</span><span class="sxs-lookup"><span data-stu-id="98362-148">These allow for the customization of both <xref:System.ServiceModel.Dispatcher.ClientRuntime> and <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes on the client and the service respectively.</span></span>  
  
 <span data-ttu-id="98362-149">Für den Zweck einer Objektpoolingerweiterung muss ein Dienstverhalten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="98362-149">For the purpose of an object pooling extension a service behavior must be created.</span></span> <span data-ttu-id="98362-150">Dienstverhaltensweisen werden durch Implementieren der <xref:System.ServiceModel.Description.IServiceBehavior>-Schnittstelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="98362-150">Service behaviors are created by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface.</span></span> <span data-ttu-id="98362-151">Es gibt mehrere Möglichkeiten, das Dienstmodell auf die benutzerdefinierten Verhaltensweisen hinzuweisen:</span><span class="sxs-lookup"><span data-stu-id="98362-151">There are several ways to make the service model aware of the custom behaviors:</span></span>  
  
-   <span data-ttu-id="98362-152">Verwenden eines benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="98362-152">Using a custom attribute.</span></span>  
  
-   <span data-ttu-id="98362-153">Imperatives Hinzufügen zur Verhaltensauflistung der Dienstbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="98362-153">Imperatively adding it to the service description’s behaviors collection.</span></span>  
  
-   <span data-ttu-id="98362-154">Erweitern der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="98362-154">Extending the configuration file.</span></span>  
  
 <span data-ttu-id="98362-155">In diesem Beispiel wird ein benutzerdefiniertes Attribut verwendet.</span><span class="sxs-lookup"><span data-stu-id="98362-155">This sample uses a custom attribute.</span></span> <span data-ttu-id="98362-156">Beim Erstellen von <xref:System.ServiceModel.ServiceHost> werden die in der Typdefinition des Diensts verwendeten Attribute untersucht, und die verfügbaren Verhaltensweisen werden der Verhaltensauflistung der Dienstbeschreibung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="98362-156">When the <xref:System.ServiceModel.ServiceHost> is constructed it examines the attributes used in the service’s type definition and adds the available behaviors to the service description’s behaviors collection.</span></span>  
  
 <span data-ttu-id="98362-157">Die Schnittstelle <xref:System.ServiceModel.Description.IServiceBehavior> verfügt über drei Methoden &#150; <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>, <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> und <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span><span class="sxs-lookup"><span data-stu-id="98362-157">The interface <xref:System.ServiceModel.Description.IServiceBehavior> has three methods in it -- <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>, <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>, and <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span></span> <span data-ttu-id="98362-158">Die <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>-Methode wird verwendet, um sicherzustellen, dass das Verhalten für den Dienst übernommen werden kann.</span><span class="sxs-lookup"><span data-stu-id="98362-158">The <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> method is used to ensure that the behavior can be applied to the service.</span></span> <span data-ttu-id="98362-159">In diesem Beispiel stellt die Implementierung sicher, dass der Dienst nicht mit <xref:System.ServiceModel.InstanceContextMode.Single> konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="98362-159">In this sample, the implementation ensures that the service is not configured with <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span> <span data-ttu-id="98362-160">Die <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>-Methode dient dazu, die Bindungen des Diensts zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="98362-160">The <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> method is used to configure the service's bindings.</span></span> <span data-ttu-id="98362-161">Sie ist für dieses Szenario nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98362-161">It is not required in this scenario.</span></span> <span data-ttu-id="98362-162"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> wird dazu verwendet, die Verteiler des Diensts zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="98362-162">The <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> is used to configure the service's dispatchers.</span></span> <span data-ttu-id="98362-163">Diese Methode wird von WCF aufgerufen wenn die <xref:System.ServiceModel.ServiceHost> initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="98362-163">This method is called by WCF when the <xref:System.ServiceModel.ServiceHost> is being initialized.</span></span> <span data-ttu-id="98362-164">Die folgenden Parameter werden an diese Methode übergeben:</span><span class="sxs-lookup"><span data-stu-id="98362-164">The following parameters are passed into this method:</span></span>  
  
-   <span data-ttu-id="98362-165">`Description`: Dieses Argument stellt die dienstbeschreibung für den gesamten Dienst bereit.</span><span class="sxs-lookup"><span data-stu-id="98362-165">`Description`: This argument provides the service description for the entire service.</span></span> <span data-ttu-id="98362-166">Dies kann dazu verwendet werden, Beschreibungsdaten über die Endpunkte, Verträge und Bindungen des Diensts und andere Daten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="98362-166">This can be used to inspect description data about the service’s endpoints, contracts, bindings, and other data.</span></span>  
  
-   <span data-ttu-id="98362-167">`ServiceHostBase`: Dieses Argument stellt die <xref:System.ServiceModel.ServiceHostBase> , die gerade initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="98362-167">`ServiceHostBase`: This argument provides the <xref:System.ServiceModel.ServiceHostBase> that is currently being initialized.</span></span>  
  
 <span data-ttu-id="98362-168">In der benutzerdefinierten <xref:System.ServiceModel.Description.IServiceBehavior>-Implementierung wird eine neue Instanz von `ObjectPoolingInstanceProvider` instanziiert und der <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>-Eigenschaft in jeder <xref:System.ServiceModel.Dispatcher.DispatchRuntime> in der ServiceHostBase zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="98362-168">In the custom <xref:System.ServiceModel.Description.IServiceBehavior> implementation a new instance of `ObjectPoolingInstanceProvider` is instantiated and assigned to the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property in each <xref:System.ServiceModel.Dispatcher.DispatchRuntime> in the ServiceHostBase.</span></span>  
  
```  
void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    // Create an instance of the ObjectPoolInstanceProvider.  
    ObjectPoolingInstanceProvider instanceProvider = new  
           ObjectPoolingInstanceProvider(description.ServiceType,   
                                                    minPoolSize);  
  
    // Forward the call if we created a ServiceThrottlingBehavior.  
    if (this.throttlingBehavior != null)  
    {  
        ((IServiceBehavior)this.throttlingBehavior).ApplyDispatchBehavior(description, serviceHostBase);  
    }  
  
    // In case there was already a ServiceThrottlingBehavior   
    // (this.throttlingBehavior==null), it should have initialized   
    // a single ServiceThrottle on all ChannelDispatchers.    
    // As we loop through the ChannelDispatchers, we verify that   
    // and modify the ServiceThrottle to guard MaxPoolSize.  
    ServiceThrottle throttle = null;  
  
    foreach (ChannelDispatcherBase cdb in   
            serviceHostBase.ChannelDispatchers)  
    {  
        ChannelDispatcher cd = cdb as ChannelDispatcher;  
        if (cd != null)  
        {  
            // Make sure there is exactly one throttle used by all   
            // endpoints. If there were others, we could not enforce   
            // MaxPoolSize.  
            if ((this.throttlingBehavior == null) &&   
                        (this.maxPoolSize != Int32.MaxValue))  
            {  
                if (throttle == null)  
                {  
                    throttle = cd.ServiceThrottle;  
                }  
                if (cd.ServiceThrottle == null)  
                {  
                    throw new   
InvalidOperationException(ResourceHelper.GetString("ExNullThrottle"));  
                }  
                if (throttle != cd.ServiceThrottle)  
                {  
                    throw new InvalidOperationException(ResourceHelper.GetString("ExDifferentThrottle"));  
                }  
             }  
  
             foreach (EndpointDispatcher ed in cd.Endpoints)  
             {  
                 // Assign it to DispatchBehavior in each endpoint.  
                 ed.DispatchRuntime.InstanceProvider =   
                                      instanceProvider;  
             }  
         }  
     }  
  
     // Set the MaxConcurrentInstances to limit the number of items   
     // that will ever be requested from the pool.  
     if ((throttle != null) && (throttle.MaxConcurrentInstances >   
                                      this.maxPoolSize))  
     {  
         throttle.MaxConcurrentInstances = this.maxPoolSize;  
     }  
}  
```  
  
 <span data-ttu-id="98362-169">Neben einer <xref:System.ServiceModel.Description.IServiceBehavior>-Implementierung verfügt die <xref:System.EnterpriseServices.ObjectPoolingAttribute>-Klasse über mehrere Member zum Anpassen des Objektpools mithilfe der Attributargumente.</span><span class="sxs-lookup"><span data-stu-id="98362-169">In addition to an <xref:System.ServiceModel.Description.IServiceBehavior> implementation the <xref:System.EnterpriseServices.ObjectPoolingAttribute> class has several members to customize the object pool using the attribute arguments.</span></span> <span data-ttu-id="98362-170">Diese Members umfassen <xref:System.EnterpriseServices.ObjectPoolingAttribute.MaxPoolSize%2A>, <xref:System.EnterpriseServices.ObjectPoolingAttribute.MinPoolSize%2A> und <xref:System.EnterpriseServices.ObjectPoolingAttribute.CreationTimeout%2A> für die Übereinstimmung mit dem von .NET Enterprise Services bereitgestellten Objektpooling-Funktionssatz.</span><span class="sxs-lookup"><span data-stu-id="98362-170">These members include <xref:System.EnterpriseServices.ObjectPoolingAttribute.MaxPoolSize%2A>, <xref:System.EnterpriseServices.ObjectPoolingAttribute.MinPoolSize%2A>, and <xref:System.EnterpriseServices.ObjectPoolingAttribute.CreationTimeout%2A>, to match the object pooling feature set provided by .NET Enterprise Services.</span></span>  
  
 <span data-ttu-id="98362-171">Das Objekt, das Verbindungspoolingverhalten kann jetzt mit einem WCF-Dienst hinzugefügt werden, durch das Hinzufügen der dienstimplementierung mit dem neu erstellten benutzerdefinierten `ObjectPooling` Attribut.</span><span class="sxs-lookup"><span data-stu-id="98362-171">The object pooling behavior can now be added to a WCF service by annotating the service implementation with the newly created custom `ObjectPooling` attribute.</span></span>  
  
```  
[ObjectPooling(MaxPoolSize=1024, MinPoolSize=10, CreationTimeout=30000)]      
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="98362-172">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="98362-172">Running the Sample</span></span>  
 <span data-ttu-id="98362-173">Das Beispiel veranschaulicht die Leistungsvorteile, die durch die Verwendung von Objektpooling in bestimmten Szenarios erzielt werden können.</span><span class="sxs-lookup"><span data-stu-id="98362-173">The sample demonstrates the performance benefits that can be gained by using object pooling in certain scenarios.</span></span>  
  
 <span data-ttu-id="98362-174">Die Dienstanwendung implementiert zwei Dienste, `WorkService` und `ObjectPooledWorkService`.</span><span class="sxs-lookup"><span data-stu-id="98362-174">The service application implements two services -- `WorkService` and `ObjectPooledWorkService`.</span></span> <span data-ttu-id="98362-175">Beide Dienste teilen dieselbe Implementierung. Sie erfordern beide eine kostenintensive Initialisierung und machen dann eine `DoWork()`-Methode verfügbar, die relativ billig ist.</span><span class="sxs-lookup"><span data-stu-id="98362-175">Both services share the same implementation -- they both require expensive initialization and then expose a `DoWork()` method that is relatively cheap.</span></span> <span data-ttu-id="98362-176">Der einzige Unterschied ist, dass für `ObjectPooledWorkService` ein Objektpooling konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="98362-176">The only difference is that the `ObjectPooledWorkService` has object pooling configured:</span></span>  
  
```  
[ObjectPooling(MinPoolSize = 0, MaxPoolSize = 5)]  
public class ObjectPooledWorkService : IDoWork  
{  
    public ObjectPooledWorkService()  
    {  
        Thread.Sleep(5000);  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService instance created.");  
    }  
  
    public void DoWork()  
    {  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService.GetData() completed.");  
    }          
}  
```  
  
 <span data-ttu-id="98362-177">Wenn Sie den Client ausführen, stoppt er die Zeit, die benötigt wird, um `WorkService` 5-mal aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="98362-177">When you run the client, it times calling the `WorkService` 5 times.</span></span> <span data-ttu-id="98362-178">Er stoppt dann die Zeit, die benötigt wird, um `ObjectPooledWorkService` 5-mal aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="98362-178">It then times calling the `ObjectPooledWorkService` 5 times.</span></span> <span data-ttu-id="98362-179">Dann wird der Zeitunterschied angezeigt:</span><span class="sxs-lookup"><span data-stu-id="98362-179">The difference in time is then displayed:</span></span>  
  
```  
Press <ENTER> to start the client.  
  
Calling WorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling WorkService took: 26722 ms.  
Calling ObjectPooledWorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling ObjectPooledWorkService took: 5323 ms.  
Press <ENTER> to exit.  
```  
  
> [!NOTE]
>  <span data-ttu-id="98362-180">Wenn der Client zum ersten Mal ausgeführt wird, scheinen beide Dienste etwa gleich viel Zeit zu benötigen.</span><span class="sxs-lookup"><span data-stu-id="98362-180">The first time the client is run both services appear to take about the same amount of time.</span></span> <span data-ttu-id="98362-181">Wenn Sie das Beispiel erneut ausführen, können Sie sehen, dass `ObjectPooledWorkService` wesentlich schneller zurückkehrt, da im Pool bereits eine Instanz dieses Objekts vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="98362-181">If you re-run the sample, you can see that the `ObjectPooledWorkService` returns much quicker because an instance of that object already exists in the pool.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="98362-182">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="98362-182">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="98362-183">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="98362-183">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="98362-184">Um die Projektmappe zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="98362-184">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="98362-185">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="98362-185">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98362-186">Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei Svcutil.exe verwenden, müssen Sie den Endpunktnamen in der Clientkonfiguration so ändern, dass er mit dem Clientcode übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="98362-186">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="98362-187">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="98362-187">The samples may already be installed on your machine.</span></span> <span data-ttu-id="98362-188">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="98362-188">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="98362-189">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="98362-189">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="98362-190">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="98362-190">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Pooling`  
  
## <a name="see-also"></a><span data-ttu-id="98362-191">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98362-191">See also</span></span>
