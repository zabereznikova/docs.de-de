---
title: Schwache Ereignismuster
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f96327f8eaad36f3faebf48db083125816589821
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="weak-event-patterns"></a><span data-ttu-id="6f73d-102">Schwache Ereignismuster</span><span class="sxs-lookup"><span data-stu-id="6f73d-102">Weak Event Patterns</span></span>
<span data-ttu-id="6f73d-103">Bei Anwendungen ist es möglich, dass ein Handler, die auf Ereignisquellen angefügt sind nicht in Abstimmung mit dem Listenerobjekt zerstört werden, die die Quelle den Handler angefügt.</span><span class="sxs-lookup"><span data-stu-id="6f73d-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="6f73d-104">Diese Situation kann zu Speicherverlusten führen.</span><span class="sxs-lookup"><span data-stu-id="6f73d-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="6f73d-105"> führt ein Entwurfsmuster, die verwendet werden kann, um dieses Problem zu beheben, stellen Sie eine dedizierte Managerklasse für bestimmte Ereignisse bereit, und Implementieren einer Schnittstelle zum Listener für dieses Ereignis an.</span><span class="sxs-lookup"><span data-stu-id="6f73d-105"> introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="6f73d-106">Dieses Entwurfsmusters heißt die *schwacher Ereignismuster*.</span><span class="sxs-lookup"><span data-stu-id="6f73d-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="6f73d-107">Gründe für das Implementieren der schwacher Ereignismuster</span><span class="sxs-lookup"><span data-stu-id="6f73d-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="6f73d-108">Überwachung der Ereignisse kann zu Speicherverlusten führen.</span><span class="sxs-lookup"><span data-stu-id="6f73d-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="6f73d-109">Das typische Verfahren für die Überwachung eines Ereignisses wird die sprachspezifische Syntax verwenden, die einen Handler an ein Ereignis in der Quelle angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="6f73d-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="6f73d-110">In C# geschrieben ist, dass die Syntax: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span><span class="sxs-lookup"><span data-stu-id="6f73d-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="6f73d-111">Diese Technik wird einen starken Verweis von der Ereignisquelle um der Ereignislistener erstellt.</span><span class="sxs-lookup"><span data-stu-id="6f73d-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="6f73d-112">Normalerweise führt dazu, dass einen Ereignishandler für einen Listener anfügen den Listener eine Lebensdauer eines Objekts haben, die von der Lebensdauer eines Objekts in der Quelle beeinflusst wird, (es sei denn, die der Ereignishandler explizit entfernt ist).</span><span class="sxs-lookup"><span data-stu-id="6f73d-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="6f73d-113">Allerdings in bestimmten Fällen sollten Sie die Lebensdauer eines Objekts in den Listener durch andere Faktoren gesteuert werden, z. B., ob es derzeit der visuellen Struktur der Anwendung und nicht von der Lebensdauer der Quelle gehört.</span><span class="sxs-lookup"><span data-stu-id="6f73d-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="6f73d-114">Sobald die Objektlebensdauer Quelle über die Lebensdauer des Listeners hinausgeht, führt das normale Ereignismuster zu einem Speicherverlust: der Listener wird aufrechterhalten länger als vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="6f73d-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="6f73d-115">Das schwacher Ereignismuster dient zum Lösen dieses Problems der Arbeitsspeicher von Speicherverlusten.</span><span class="sxs-lookup"><span data-stu-id="6f73d-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="6f73d-116">Das schwacher Ereignismuster kann verwendet werden, wenn ein Listener für ein Ereignis registrieren muss, der Listener ist jedoch nicht explizit bekannt beim Aufheben der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="6f73d-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="6f73d-117">Das schwacher Ereignismuster kann auch verwendet werden, wenn die Lebensdauer eines Objekts in der Quelle nützlich Objektlebensdauer des Listeners überschreitet.</span><span class="sxs-lookup"><span data-stu-id="6f73d-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="6f73d-118">(In diesem Fall *nützlich* wird von Ihnen bestimmt.) Das schwacher Ereignismuster ermöglicht dem Listener zum Registrieren für und ohne Auswirkungen auf die Merkmale des Listeners in keiner Weise Objektlebensdauer das Ereignis empfangen.</span><span class="sxs-lookup"><span data-stu-id="6f73d-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="6f73d-119">Aktiviert ist, der implizite Verweis aus der Quelle nicht bestimmt werden, ob der Listener für die Garbagecollection geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="6f73d-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="6f73d-120">Der Verweis ist, einen schwachen Verweis, und somit die Benennung von der schwacher Ereignismuster und die zugehörigen [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f73d-120">The reference is a weak reference, thus the naming of the weak event pattern and the related [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span></span> <span data-ttu-id="6f73d-121">Der Listener kann werden vom Garbage Collector erfasst, oder andernfalls zerstört und die Quelle kann weiterhin ohne Beibehaltung Handlerverweise mit einem Objekt jetzt zerstört.</span><span class="sxs-lookup"><span data-stu-id="6f73d-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="6f73d-122">Wer soll das schwacher Ereignismuster implementieren?</span><span class="sxs-lookup"><span data-stu-id="6f73d-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="6f73d-123">Implementieren des Musters schwache Ereignis ist in erster Linie für Autoren interessant.</span><span class="sxs-lookup"><span data-stu-id="6f73d-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="6f73d-124">Als Autor eines Steuerelements sind Sie größtenteils verantwortlich für das Verhalten und die Kapselung der Ihrer Kontrolle und die Auswirkungen auf Anwendungen, die ihm in der er eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="6f73d-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="6f73d-125">Dies schließt das Lebensdauer-Verhalten des Steuerelements ein, insbesondere die Behandlung des Speicherverlustproblems beschriebene Speicher.</span><span class="sxs-lookup"><span data-stu-id="6f73d-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="6f73d-126">Bestimmte Szenarien eignen sich grundsätzlich auf die Anwendung das schwacher Ereignismuster.</span><span class="sxs-lookup"><span data-stu-id="6f73d-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="6f73d-127">Ein solches Szenario ist die Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="6f73d-127">One such scenario is data binding.</span></span> <span data-ttu-id="6f73d-128">Bei einer Datenbindung wird häufig für das Quellobjekt, das als Ziel einer Bindung wird vollständig unabhängig von der Listener-Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="6f73d-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="6f73d-129">Viele Aspekte der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bereits zum Binden von Daten der schwachen-Ereignismuster in der Implementierung der Ereignisse angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="6f73d-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="6f73d-130">Gewusst wie: Implementieren der schwacher Ereignismuster</span><span class="sxs-lookup"><span data-stu-id="6f73d-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="6f73d-131">Es gibt drei Möglichkeiten zum Implementieren schwacher Ereignismuster.</span><span class="sxs-lookup"><span data-stu-id="6f73d-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="6f73d-132">In der folgenden Tabelle werden die drei Ansätze aufgeführt und enthält hilfreiche Informationen für die Verwendung jedes sollten.</span><span class="sxs-lookup"><span data-stu-id="6f73d-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="6f73d-133">Ansatz</span><span class="sxs-lookup"><span data-stu-id="6f73d-133">Approach</span></span>|<span data-ttu-id="6f73d-134">Implementieren von</span><span class="sxs-lookup"><span data-stu-id="6f73d-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="6f73d-135">Verwenden einer vorhandenen schwache Ereignis-Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="6f73d-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="6f73d-136">Wenn das Ereignis, die Sie abonnieren möchten ein entsprechendes hat <xref:System.Windows.WeakEventManager>, verwenden Sie den vorhandenen schwache Ereignis-Manager.</span><span class="sxs-lookup"><span data-stu-id="6f73d-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="6f73d-137">Eine Liste der schwache Ereignis-Manager, die in WPF enthalten sind, finden Sie in die Vererbungshierarchie der <xref:System.Windows.WeakEventManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="6f73d-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="6f73d-138">Beachten Sie jedoch, dass es relativ wenige schwache Ereignis-Manager, die mit WPF, enthalten sind gibt, so Sie wahrscheinlich eine der anderen Methoden auswählen müssen.</span><span class="sxs-lookup"><span data-stu-id="6f73d-138">Note, however, that there are relatively few weak event managers that are included with WPF, so you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="6f73d-139">Verwenden einer generischen schwachen Ereignis-Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="6f73d-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="6f73d-140">Verwenden Sie eine generische <xref:System.Windows.WeakEventManager%602> bei einem vorhandenen <xref:System.Windows.WeakEventManager> ist nicht verfügbar ist, Sie möchten eine einfache Möglichkeit zum Implementieren und Sie sind nicht besorgt Effizienz.</span><span class="sxs-lookup"><span data-stu-id="6f73d-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="6f73d-141">Die generische <xref:System.Windows.WeakEventManager%602> ist weniger effizient als eine vorhandene oder benutzerdefinierte schwache Ereignis-Manager.</span><span class="sxs-lookup"><span data-stu-id="6f73d-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="6f73d-142">Beispielsweise ist die generische Klasse mehrere Reflektion, um das Ereignis angegebenen Ereignisnamens zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="6f73d-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="6f73d-143">Außerdem wird im Code auf das Ereignis zu registrieren, indem Sie mithilfe der allgemeinen <xref:System.Windows.WeakEventManager%602> ist mehr als die Verwendung einer vorhandenen ausführliche oder benutzerdefinierte <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="6f73d-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="6f73d-144">Erstellen Sie eine benutzerdefinierte schwache Ereignis-Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="6f73d-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="6f73d-145">Erstellen eines benutzerdefinierten <xref:System.Windows.WeakEventManager> bei einem vorhandenen <xref:System.Windows.WeakEventManager> ist nicht verfügbar, und Sie möchten die optimale Effizienz.</span><span class="sxs-lookup"><span data-stu-id="6f73d-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="6f73d-146">Mithilfe einer benutzerdefinierten <xref:System.Windows.WeakEventManager> zum Abonnieren ein Ereignisses wird effizienter sein, aber führen Sie die Kosten für das Schreiben von weiteren Code am Anfang anfallen.</span><span class="sxs-lookup"><span data-stu-id="6f73d-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
  
 <span data-ttu-id="6f73d-147">In den folgenden Abschnitten wird beschrieben, wie das schwacher Ereignismuster implementieren.</span><span class="sxs-lookup"><span data-stu-id="6f73d-147">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="6f73d-148">Für den Rahmen dieser Erläuterung weist folgende Merkmale auf das Ereignis abonnieren.</span><span class="sxs-lookup"><span data-stu-id="6f73d-148">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
-   <span data-ttu-id="6f73d-149">Der Ereignisname wird `SomeEvent`.</span><span class="sxs-lookup"><span data-stu-id="6f73d-149">The event name is `SomeEvent`.</span></span>  
  
-   <span data-ttu-id="6f73d-150">Das Ereignis wird ausgelöst, durch die `EventSource` Klasse.</span><span class="sxs-lookup"><span data-stu-id="6f73d-150">The event is raised by the `EventSource` class.</span></span>  
  
-   <span data-ttu-id="6f73d-151">Der Ereignishandler weist den Typ: `SomeEventEventHandler` (oder `EventHandler<SomeEventEventArgs>`).</span><span class="sxs-lookup"><span data-stu-id="6f73d-151">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
-   <span data-ttu-id="6f73d-152">Das Ereignis übergibt einen Parameter vom Typ `SomeEventEventArgs` an die Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="6f73d-152">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="6f73d-153">Verwenden einer vorhandenen schwache Ereignis-Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="6f73d-153">Using an Existing Weak Event Manager Class</span></span>  
  
1.  <span data-ttu-id="6f73d-154">Suchen Sie nach einer vorhandenen schwache Ereignis Manager.</span><span class="sxs-lookup"><span data-stu-id="6f73d-154">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="6f73d-155">Eine Liste der schwache Ereignis-Manager, die in WPF enthalten sind, finden Sie in die Vererbungshierarchie der <xref:System.Windows.WeakEventManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="6f73d-155">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2.  <span data-ttu-id="6f73d-156">Verwenden Sie den neuen schwache Ereignis-Manager anstelle der normalen ereigniseinbindung an.</span><span class="sxs-lookup"><span data-stu-id="6f73d-156">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="6f73d-157">Angenommen, Ihr Code das folgenden Muster zum Abonnieren eines Ereignisses verwendet:</span><span class="sxs-lookup"><span data-stu-id="6f73d-157">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="6f73d-158">Ändern Sie sie an, in dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="6f73d-158">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="6f73d-159">Auf ähnliche Weise, wenn im Code des folgenden Musters verwendet, um ein Ereignis zu kündigen:</span><span class="sxs-lookup"><span data-stu-id="6f73d-159">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="6f73d-160">Ändern Sie sie an, in dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="6f73d-160">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="6f73d-161">Mithilfe der generischen schwachen Ereignis-Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="6f73d-161">Using the Generic Weak Event Manager Class</span></span>  
  
1.  <span data-ttu-id="6f73d-162">Die generische <xref:System.Windows.WeakEventManager%602> Klasse anstelle der normalen ereigniseinbindung.</span><span class="sxs-lookup"><span data-stu-id="6f73d-162">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="6f73d-163">Bei Verwendung von <xref:System.Windows.WeakEventManager%602> um Ereignislistener zu registrieren, geben Sie die Ereignisquelle und <xref:System.EventArgs> Typ wie der Typparameter der Klasse und der Aufruf <xref:System.Windows.WeakEventManager%602.AddHandler%2A> wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6f73d-163">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="6f73d-164">Erstellen einer benutzerdefinierten schwache Ereignis-Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="6f73d-164">Creating a Custom Weak Event Manager Class</span></span>  
  
1.  <span data-ttu-id="6f73d-165">Kopieren Sie die folgenden Klassenvorlage in Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="6f73d-165">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="6f73d-166">Diese Klasse erbt von der <xref:System.Windows.WeakEventManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="6f73d-166">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  <span data-ttu-id="6f73d-167">Ersetzen Sie die `SomeEventWeakEventManager` durch den Namen Ihres eigenen Namen.</span><span class="sxs-lookup"><span data-stu-id="6f73d-167">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3.  <span data-ttu-id="6f73d-168">Ersetzen Sie die drei Namen, die zuvor beschriebenen mit den entsprechenden Namen für Ihr Ereignis.</span><span class="sxs-lookup"><span data-stu-id="6f73d-168">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="6f73d-169">(`SomeEvent`, `EventSource`, und `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="6f73d-169">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4.  <span data-ttu-id="6f73d-170">Legen Sie die Sichtbarkeit (öffentlich / privaten / internen) der schwachen Ereignisklasse Manager, um die gleiche Sichtbarkeit wie die von ihm verwalteten Ereignis.</span><span class="sxs-lookup"><span data-stu-id="6f73d-170">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5.  <span data-ttu-id="6f73d-171">Verwenden Sie den neuen schwache Ereignis-Manager anstelle der normalen ereigniseinbindung an.</span><span class="sxs-lookup"><span data-stu-id="6f73d-171">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="6f73d-172">Angenommen, Ihr Code das folgenden Muster zum Abonnieren eines Ereignisses verwendet:</span><span class="sxs-lookup"><span data-stu-id="6f73d-172">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="6f73d-173">Ändern Sie sie an, in dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="6f73d-173">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="6f73d-174">Auf ähnliche Weise, wenn im Code des folgenden Musters verwendet, um ein Ereignis zu kündigen:</span><span class="sxs-lookup"><span data-stu-id="6f73d-174">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="6f73d-175">Ändern Sie sie an, in dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="6f73d-175">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6f73d-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f73d-176">See Also</span></span>  
 <xref:System.Windows.WeakEventManager>  
 <xref:System.Windows.IWeakEventListener>  
 [<span data-ttu-id="6f73d-177">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="6f73d-177">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="6f73d-178">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="6f73d-178">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
