---
title: Benutzerdefinierte Lebensdauer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2538a9c483b949dfef1c60bd2225f5daf4e01117
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="custom-lifetime"></a><span data-ttu-id="8bacb-102">Benutzerdefinierte Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="8bacb-102">Custom Lifetime</span></span>
<span data-ttu-id="8bacb-103">In diesem Beispiel wird veranschaulicht, wie eine [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Erweiterung geschrieben wird, die benutzerdefinierte Lebensdauerdienste für freigegebene [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstinstanzen bereitstellen soll.</span><span class="sxs-lookup"><span data-stu-id="8bacb-103">This sample demonstrates how to write a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] extension to provide custom lifetime services for shared [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bacb-104">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="8bacb-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="shared-instancing"></a><span data-ttu-id="8bacb-105">Freigegebene Instanziierung</span><span class="sxs-lookup"><span data-stu-id="8bacb-105">Shared Instancing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8bacb-106"> stellt mehrere Instanziierungsmodi für die Dienstinstanzen bereit.</span><span class="sxs-lookup"><span data-stu-id="8bacb-106"> offers several instancing modes for your service instances.</span></span> <span data-ttu-id="8bacb-107">Der freigegebene Instanziierungsmodus, der in diesem Thema behandelt wird, bietet eine Möglichkeit, eine Dienstinstanz zwischen mehreren Kanälen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="8bacb-107">The Shared Instancing mode covered in this topic provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="8bacb-108">Clients können entweder die Endpunktadresse der Instanz lokal auflösen oder eine Factorymethode im Dienst kontaktieren, um die Endpunktadresse einer ausgeführten Instanz abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-108">Clients can either resolve the instance’s endpoint address locally or contact a factory method in the service to obtain the endpoint address of a running instance.</span></span> <span data-ttu-id="8bacb-109">Sobald die Endpunktadresse vorliegt, kann ein neuer Kanal erstellt und die Kommunikation gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="8bacb-109">Once it has the endpoint address, it can create a new channel and start communication.</span></span> <span data-ttu-id="8bacb-110">Im folgenden Codeausschnitt wird gezeigt, wie eine Clientanwendung einen neuen Kanal zu einer vorhandenen Dienstinstanz erstellt.</span><span class="sxs-lookup"><span data-stu-id="8bacb-110">The following code snippet shows how a client application creates a new channel to an existing service instance.</span></span>  
  
```  
// Create the first channel.  
IEchoService proxy = channelFactory.CreateChannel();  
  
// Resolve the instance.  
EndpointAddress epa = ((IClientChannel)proxy).ResolveInstance();  
  
// Create new channel factory with the endpoint address resolved by   
// previous statement.  
ChannelFactory<IEchoService> channelFactory2 =  
                new ChannelFactory<IEchoService>("echoservice",  
                epa);  
  
// Create the second channel to the same instance.  
IEchoService proxy2 = channelFactory2.CreateChannel();  
```  
  
 <span data-ttu-id="8bacb-111">Der freigegebene Instanziierungsmodus unterscheidet sich von anderen Instanziierungsmodi in seiner einzigartigen Methode zum Freigeben von Dienstinstanzen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-111">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="8bacb-112">Wenn alle Kanäle für eine Instanz geschlossen sind, startet die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Laufzeit des Diensts einen Zeitgeber.</span><span class="sxs-lookup"><span data-stu-id="8bacb-112">When all the channels are closed for an instance, the service [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime starts a timer.</span></span> <span data-ttu-id="8bacb-113">Wenn vor Ablauf des Timeouts keine Verbindung hergestellt wird, gibt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Instanz frei und erhebt Anspruch auf die Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-113">If nobody makes a connection before the timeout expires, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] releases the instance and claims the resources.</span></span> <span data-ttu-id="8bacb-114">Im Rahmen der Beendigungsprozedur ruft [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode aller <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>-Implementierungen auf, bevor die Instanz freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8bacb-114">As a part of the teardown procedure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of all <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementations before releasing the instance.</span></span> <span data-ttu-id="8bacb-115">Wenn alle Implementierungen `true` zurückgeben, wird die Instanz freigegeben.</span><span class="sxs-lookup"><span data-stu-id="8bacb-115">If all of them return `true` the instance is released.</span></span> <span data-ttu-id="8bacb-116">Andernfalls ist die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>-Implementierung dafür zuständig, den `Dispatcher` unter Verwendung einer Rückrufmethode von dem Leerlaufzustand zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-116">Otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span>  
  
 <span data-ttu-id="8bacb-117">Standardmäßig beträgt der Leerlauftimeoutwert von <xref:System.ServiceModel.InstanceContext> eine Minute.</span><span class="sxs-lookup"><span data-stu-id="8bacb-117">By default, the idle timeout value of <xref:System.ServiceModel.InstanceContext> is one minute.</span></span> <span data-ttu-id="8bacb-118">In diesem Beispiel wird jedoch gezeigt, wie Sie diesen Wert erweitern können, indem Sie die benutzerdefinierte Erweiterung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8bacb-118">However this sample demonstrates how you can extend this using a custom extension.</span></span>  
  
## <a name="extending-the-instancecontext"></a><span data-ttu-id="8bacb-119">Erweitern von InstanceContext</span><span class="sxs-lookup"><span data-stu-id="8bacb-119">Extending the InstanceContext</span></span>  
 <span data-ttu-id="8bacb-120">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist <xref:System.ServiceModel.InstanceContext> die Verknüpfung zwischen der Dienstinstanz und `Dispatcher`.</span><span class="sxs-lookup"><span data-stu-id="8bacb-120">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="8bacb-121">Sie können diese Laufzeitkomponente in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erweitern, indem Sie mithilfe des erweiterbaren Objektmusters einen neuen Zustand oder ein neues Verhalten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-121">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="8bacb-122">Das erweiterbare Objektmuster wird in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet, um vorhandene Laufzeitklassen um neue Funktionen zu erweitern oder um neue Zustandsfunktionen zu einem Objekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-122">The extensible object pattern is used in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="8bacb-123">Es gibt drei Schnittstellen im erweiterbaren Objektmuster: `IExtensibleObject<T>`, `IExtension<T>` und `IExtensionCollection<T>`.</span><span class="sxs-lookup"><span data-stu-id="8bacb-123">There are three interfaces in the extensible object pattern: `IExtensibleObject<T>`, `IExtension<T>`, and `IExtensionCollection<T>`.</span></span>  
  
 <span data-ttu-id="8bacb-124">Die `IExtensibleObject<T>`-Schnittstelle wird von Objekten implementiert, um Erweiterungen zuzulassen, die ihre Funktionalität anpassen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-124">The `IExtensibleObject<T>` interface is implemented by objects to allow extensions which customize their functionality.</span></span>  
  
 <span data-ttu-id="8bacb-125">Die `IExtension<T>`-Schnittstelle wird von Objekten implementiert, die Erweiterungen von Klassen des Typs `T` sein können.</span><span class="sxs-lookup"><span data-stu-id="8bacb-125">The `IExtension<T>` interface is implemented by objects that can be extensions of classes of type `T`.</span></span>  
  
 <span data-ttu-id="8bacb-126">Die `IExtensionCollection<T>`-Schnittstelle ist eine Auflistung von `IExtensions`, die das Abrufen von `IExtensions` nach Typ zulässt.</span><span class="sxs-lookup"><span data-stu-id="8bacb-126">And finally, the `IExtensionCollection<T>` interface is a collection of `IExtensions` that allows for retrieving `IExtensions` by their type.</span></span>  
  
 <span data-ttu-id="8bacb-127">Aus diesem Grund müssen Sie die <xref:System.ServiceModel.InstanceContext>-Schnittstelle implementieren, um den `IExtension` zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="8bacb-127">Therefore in order to extend the <xref:System.ServiceModel.InstanceContext> you must implement the `IExtension` interface.</span></span> <span data-ttu-id="8bacb-128">In diesem Beispielprojekt enthält die `CustomLeaseExtension`-Klasse diese Implementierung.</span><span class="sxs-lookup"><span data-stu-id="8bacb-128">In this sample project the `CustomLeaseExtension` class contains this implementation.</span></span>  
  
```  
class CustomLeaseExtension : IExtension<InstanceContext>  
{  
}  
```  
  
 <span data-ttu-id="8bacb-129">Die `IExtension`-Schnittstelle verfügt über zwei Methoden: `Attach` und `Detach`.</span><span class="sxs-lookup"><span data-stu-id="8bacb-129">The `IExtension` interface has two methods `Attach` and `Detach`.</span></span> <span data-ttu-id="8bacb-130">Wie ihre Namen vermuten lassen, werden diese beiden Methoden aufgerufen, wenn die Laufzeit die Erweiterung an eine Instanz der <xref:System.ServiceModel.InstanceContext>-Klasse anfügt oder von der Instanz löst.</span><span class="sxs-lookup"><span data-stu-id="8bacb-130">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="8bacb-131">In diesem Beispiel wird die `Attach`-Methode für die Nachverfolgung des <xref:System.ServiceModel.InstanceContext>-Objekts verwendet, das zur aktuellen Instanz der Erweiterung gehört.</span><span class="sxs-lookup"><span data-stu-id="8bacb-131">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>  
  
```  
InstanceContext owner;  
  
public void Attach(InstanceContext owner)  
{  
  this.owner = owner;   
}  
```  
  
 <span data-ttu-id="8bacb-132">Darüber hinaus müssen Sie zur Bereitstellung der erweiterten Lebensdauerunterstützung die erforderliche Implementierung zur Erweiterung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-132">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="8bacb-133">Deswegen wird die `ICustomLease`-Schnittstelle mit den gewünschten Methoden deklariert und in der `CustomLeaseExtension`-Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="8bacb-133">Therefore the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>  
  
```  
interface ICustomLease  
{  
    bool IsIdle { get; }          
    InstanceContextIdleCallback Callback { get; set; }  
}  
  
class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease  
{  
}  
```  
  
 <span data-ttu-id="8bacb-134">Wenn in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode in der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>-Implementierung aufgerufen wird, wird dieser Aufruf an die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode der `CustomLeaseExtension` weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="8bacb-134">When [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="8bacb-135">Dann überprüft die `CustomLeaseExtension` den privaten Zustand, um festzustellen, ob sich der <xref:System.ServiceModel.InstanceContext> im Leerlauf befindet.</span><span class="sxs-lookup"><span data-stu-id="8bacb-135">Then the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="8bacb-136">Wenn er sich in Leerlauf befindet, wird `true` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8bacb-136">If it is idle it returns `true`.</span></span> <span data-ttu-id="8bacb-137">Andernfalls wird ein Zeitgeber für eine bestimmte erweiterte Lebensdauerperiode gestartet.</span><span class="sxs-lookup"><span data-stu-id="8bacb-137">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>  
  
```  
public bool IsIdle  
{  
  get  
  {  
    lock (thisLock)  
    {  
      if (isIdle)  
      {  
        return true;  
      }  
      else  
      {  
        StartTimer();  
        return false;  
      }  
    }  
  }  
}  
```  
  
 <span data-ttu-id="8bacb-138">Im `Elapsed`-Ereignis des Zeitgebers wird die Rückruffunktion im Verteiler aufgerufen, um einen weiteren Bereinigungszyklus zu starten.</span><span class="sxs-lookup"><span data-stu-id="8bacb-138">In the timer’s `Elapsed` event the callback function in the Dispatcher is called in order to start another clean up cycle.</span></span>  
  
```  
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)  
{  
    idleTimer.Stop();  
    isIdle = true;    
    callback(owner);  
}  
```  
  
 <span data-ttu-id="8bacb-139">Der ausgeführte Zeitgeber kann nicht erneuert werden, wenn eine neue Nachricht für die Instanz eingeht, die in den Leerlaufzustand verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="8bacb-139">There is no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>  
  
 <span data-ttu-id="8bacb-140">Im Beispiel wird <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementiert, um die Aufrufe der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode abzufangen und diese zur `CustomLeaseExtension` weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="8bacb-140">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="8bacb-141">Die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>-Implementierung ist in der `CustomLifetimeLease`-Klasse enthalten.</span><span class="sxs-lookup"><span data-stu-id="8bacb-141">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="8bacb-142">Die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode wird aufgerufen, wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] im Begriff ist, die Dienstinstanz freizugeben.</span><span class="sxs-lookup"><span data-stu-id="8bacb-142">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is about to release the service instance.</span></span> <span data-ttu-id="8bacb-143">Es gibt jedoch nur eine Instanz einer bestimmten `ISharedSessionInstance`-Implementierung in der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>-Auflistung von ServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="8bacb-143">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="8bacb-144">Das bedeutet, dass nicht vorhergesagt werden kann, ob <xref:System.ServiceModel.InstanceContext> geschlossen ist, wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode überprüft.</span><span class="sxs-lookup"><span data-stu-id="8bacb-144">This means there is no way of knowing the <xref:System.ServiceModel.InstanceContext> being closed at the time [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="8bacb-145">Aus diesem Grund werden Anforderungen der <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>-Methode in diesem Beispiel mit der Threadsperre serialisiert.</span><span class="sxs-lookup"><span data-stu-id="8bacb-145">Therefore this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8bacb-146">Die Verwendung der Threadsperre wird nicht empfohlen, da die Leistung der Anwendung durch die Serialisierung deutlich beeinträchtigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8bacb-146">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>  
  
 <span data-ttu-id="8bacb-147">Eine private Membervariable wird in der `CustomLeaseExtension`-Klasse verwendet, um den `IsIdle`-Wert nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-147">A private member variable is used in the `CustomLeaseExtension` class to track the `IsIdle` value.</span></span> <span data-ttu-id="8bacb-148">Jedes Mal, wenn der Wert von <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> abgerufen wird, wird der private `IsIdle`-Member zurückgegeben und auf `false` zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="8bacb-148">Each time the value of <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is retrieved the `IsIdle` private member is returned and reset to `false`.</span></span> <span data-ttu-id="8bacb-149">Dieser Wert muss auf `false` festgelegt werden, um sicherzustellen, dass der Verteiler die <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="8bacb-149">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>  
  
```  
public bool IsIdle  
{  
    get   
    {  
       lock (thisLock)  
       {  
           bool idleCopy = isIdle;  
           isIdle = false;  
           return idleCopy;  
       }  
    }  
}  
```  
  
 <span data-ttu-id="8bacb-150">Wenn die `ISharedSessionLifetime.IsIdle`-Eigenschaft `false` zurückgibt, registriert der Verteiler mithilfe der `NotifyIdle`-Methode eine Rückruffunktion.</span><span class="sxs-lookup"><span data-stu-id="8bacb-150">If the `ISharedSessionLifetime.IsIdle` property returns `false` the Dispatcher registers a callback function by using the `NotifyIdle` method.</span></span> <span data-ttu-id="8bacb-151">Diese Methode empfängt einen Verweis darauf, dass <xref:System.ServiceModel.InstanceContext> freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8bacb-151">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="8bacb-152">Daher kann der Beispielcode die Erweiterung des Typs `ICustomLease` abfragen und die `ICustomLease.IsIdle`-Eigenschaft im erweiterten Zustand überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-152">Therefore the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>  
  
```  
public void NotifyIdle(InstanceContextIdleCallback callback,   
            InstanceContext instanceContext)  
{  
    lock (thisLock)  
    {  
       ICustomLease customLease =  
           instanceContext.Extensions.Find<ICustomLease>();  
       customLease.Callback = callback;   
       isIdle = customLease.IsIdle;  
       if (isIdle)  
       {  
             callback(instanceContext);  
       }  
    }   
}  
```  
  
 <span data-ttu-id="8bacb-153">Bevor die `ICustomLease.IsIdle`-Eigenschaft überprüft wird, muss die Rückrufeigenschaft festgelegt werden, damit die `CustomLeaseExtension` den Verteiler benachrichtigen kann, sobald sie in den Leerlauf wechselt.</span><span class="sxs-lookup"><span data-stu-id="8bacb-153">Before the `ICustomLease.IsIdle` property is checked the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="8bacb-154">Wenn `ICustomLease.IsIdle` `true` zurückgibt, wird der private `isIdle`-Member einfach in `CustomLifetimeLease` auf `true` festgelegt, und die Rückrufmethode wird vom Member aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-154">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="8bacb-155">Da im Code eine Sperre enthalten ist, können andere Threads den Wert dieses privaten Members nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="8bacb-155">Because the code holds a lock, other threads cannot change the value of this private member.</span></span> <span data-ttu-id="8bacb-156">Wenn der Verteiler das nächste Mal die `ISharedSessionLifetime.IsIdle`-Eigenschaft überprüft, gibt sie `true` zurück, und der Verteiler kann die Instanz freigeben.</span><span class="sxs-lookup"><span data-stu-id="8bacb-156">And the next time Dispatcher checks the `ISharedSessionLifetime.IsIdle`, it returns `true` and lets Dispatcher release the instance.</span></span>  
  
 <span data-ttu-id="8bacb-157">Jetzt da die Vorarbeit für die benutzerdefinierte Erweiterung abgeschlossen ist, muss sie in das Dienstmodell eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="8bacb-157">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="8bacb-158">Um die `CustomLeaseExtension`-Implementierung in den <xref:System.ServiceModel.InstanceContext> einzubinden, stellt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer>-Schnittstelle bereit, um das Bootstrapping von <xref:System.ServiceModel.InstanceContext> auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-158">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="8bacb-159">In diesem Beispiel implementiert die `CustomLeaseInitializer`-Klasse diese Schnittstelle und fügt eine `CustomLeaseExtension`-Instanz zur <xref:System.ServiceModel.InstanceContext.Extensions%2A>-Auflistung aus der einzigen Methodeninitialisierung hinzu.</span><span class="sxs-lookup"><span data-stu-id="8bacb-159">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="8bacb-160">Diese Methode wird vom Verteiler aufgerufen, während <xref:System.ServiceModel.InstanceContext> initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="8bacb-160">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>  
  
```  
public void Initialize(InstanceContext instanceContext, Message message)  
{  
  IExtension<InstanceContext> customLeaseExtension =  
    new CustomLeaseExtension(timeout);  
  instanceContext.Extensions.Add(customLeaseExtension);  
}  
```  
  
 <span data-ttu-id="8bacb-161">Schließlich die `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` und <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> Implementierungen sind ist hakenförmigen bis zu das Dienstmodell mithilfe der <xref:System.ServiceModel.Description.IServiceBehavior> Implementierung.</span><span class="sxs-lookup"><span data-stu-id="8bacb-161">Finally the `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` and <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> implementations are is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="8bacb-162">Diese Implementierung wird in der `CustomLeaseTimeAttribute`-Klasse eingefügt, und sie wird außerdem von der `Attribute`-Basisklasse abgeleitet, um dieses Verhalten als Attribut verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-162">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the `Attribute` base class to expose this behavior as an attribute.</span></span> <span data-ttu-id="8bacb-163">In der `IServiceBehavior.ApplyBehavior`-Methode werden Instanzen von der <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer>-Implementierung und der `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime`-Implementierung zu der `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes`-Auflistung bzw. der <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A>-Auflistung von <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8bacb-163">In the `IServiceBehavior.ApplyBehavior` method, instances of <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> and `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` implementations are added to the `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes` and <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> collections of the <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> respectively.</span></span>  
  
```  
public void ApplyBehavior(ServiceDescription description,   
           ServiceHostBase serviceHostBase,   
           Collection<DispatchBehavior> behaviors,  
           Collection<BindingParameterCollection> parameters)  
{  
    CustomLifetimeLease customLease = new CustomLifetimeLease();  
    CustomLeaseInitializer initializer =   
                new CustomLeaseInitializer(timeout);  
  
    foreach (DispatchBehavior dispatchBehavior in behaviors)  
    {  
        dispatchBehavior.InstanceContextLifetimes.Add(customLease);  
        dispatchBehavior.InstanceContextInitializers.Add(initializer);  
    }  
}  
```  
  
 <span data-ttu-id="8bacb-164">Dieses Verhalten kann einer Beispieldienstklasse hinzugefügt werden, indem es mit dem `CustomLeaseTime`-Attribut kommentiert wird.</span><span class="sxs-lookup"><span data-stu-id="8bacb-164">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Shareable)]  
[CustomLeaseTime(Timeout = 20000)]  
public class EchoService : IEchoService  
{  
  //…  
}  
```  
  
 <span data-ttu-id="8bacb-165">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8bacb-165">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="8bacb-166">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-166">Press ENTER in each console window to shut down the service and client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8bacb-167">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="8bacb-167">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8bacb-168">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8bacb-168">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8bacb-169">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-169">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8bacb-170">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8bacb-170">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8bacb-171">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="8bacb-171">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8bacb-172">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="8bacb-172">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8bacb-173">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="8bacb-173">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8bacb-174">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8bacb-174">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`  
  
## <a name="see-also"></a><span data-ttu-id="8bacb-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bacb-175">See Also</span></span>
