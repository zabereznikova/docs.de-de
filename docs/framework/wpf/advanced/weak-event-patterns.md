---
title: Schwache Ereignismuster
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 61e7f6d29cf9275004238ca776d5af9bf027004f
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859918"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="3b60d-102">Schwache Ereignismuster</span><span class="sxs-lookup"><span data-stu-id="3b60d-102">Weak Event Patterns</span></span>
<span data-ttu-id="3b60d-103">Bei Anwendungen ist es möglich, dass der Handler, die Ereignisquellen angefügt sind, nicht in Koordination mit dem Listenerobjekt zerstört werden, die die Quelle der Handler zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="3b60d-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="3b60d-104">Diese Situation kann zu Arbeitsspeicherverlusten führen.</span><span class="sxs-lookup"><span data-stu-id="3b60d-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="3b60d-105">führt ein Entwurfsmuster, die verwendet werden kann, um dieses Problem zu beheben, indem Sie eine dedizierte Manager-Klasse für bestimmte Ereignisse bereitstellen und Implementieren einer Schnittstelle zum Listener für das betreffende Ereignis.</span><span class="sxs-lookup"><span data-stu-id="3b60d-105">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="3b60d-106">Dieses Entwurfsmuster wird als bezeichnet die *Muster für schwache Ereignisse*.</span><span class="sxs-lookup"><span data-stu-id="3b60d-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="3b60d-107">Gründe für das Implementieren der schwache Ereignismuster</span><span class="sxs-lookup"><span data-stu-id="3b60d-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="3b60d-108">Überwachen von Ereignissen kann zu Arbeitsspeicherverlusten führen.</span><span class="sxs-lookup"><span data-stu-id="3b60d-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="3b60d-109">Die normale Technik für die Überwachung auf ein Ereignis ist, die sprachspezifische Syntax zu verwenden, die einen Handler an ein Ereignis für eine Datenquelle angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3b60d-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="3b60d-110">Z. B. in C#, dass die Syntax lautet: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span><span class="sxs-lookup"><span data-stu-id="3b60d-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="3b60d-111">Diese Methode erstellt einen starken Verweis aus der Ereignisquelle in den Ereignislistener.</span><span class="sxs-lookup"><span data-stu-id="3b60d-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="3b60d-112">Normalerweise wird das Anhängen eines ereignishandlers für einen Listener die Überwachung für die eine Lebensdauer haben, die von der Quelle der Objektlebensdauer beeinflusst ist (es sei denn, der Ereignishandler explizit entfernt wird).</span><span class="sxs-lookup"><span data-stu-id="3b60d-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="3b60d-113">Unter bestimmten Umständen Sie sollten jedoch die Objektlebensdauer des Listeners, der durch andere Faktoren gesteuert werden, wie z. B., ob er zurzeit an der visuellen Struktur der Anwendung und nicht von der Lebensdauer der Quelle gehört.</span><span class="sxs-lookup"><span data-stu-id="3b60d-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="3b60d-114">Wenn die Lebensdauer der Energiequelle Objekt die Objektlebensdauer des Listeners, der erweitert wird, wird das normale Ereignismuster zu einem Speicherverlust führt: der Listener ist länger als vorgesehen aktiv bleiben.</span><span class="sxs-lookup"><span data-stu-id="3b60d-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="3b60d-115">Das Muster für schwache Ereignisse soll dieses Memory Leak Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="3b60d-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="3b60d-116">Das Muster für schwache Ereignisse kann verwendet werden, wenn ein Listener für ein Ereignis registrieren muss, aber der Listener ist nicht explizit bekannt beim Aufheben der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="3b60d-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="3b60d-117">Das Muster für schwache Ereignisse kann auch verwendet werden, wenn die Objektlebensdauer der Quelle des Listeners nützlich Objektlebensdauer überschreitet.</span><span class="sxs-lookup"><span data-stu-id="3b60d-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="3b60d-118">(In diesem Fall *nützlich* wird bestimmt, indem Sie Sie.) Das Muster für schwache Ereignisse ermöglicht den Listener, um sich anzumelden und das Ereignis empfangen, ohne Auswirkungen auf die Objekteigenschaften für die Lebensdauer des Listeners in keiner Weise.</span><span class="sxs-lookup"><span data-stu-id="3b60d-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="3b60d-119">Aktiviert ist, wird der implizite Verweis aus der Quelle nicht ermittelt werden, ob der Listener für die Garbagecollection ist.</span><span class="sxs-lookup"><span data-stu-id="3b60d-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="3b60d-120">Der Verweis ist daher die Benennung von am schwachen Ereignismuster und den zugehörigen APIs einen schwachen Verweis.</span><span class="sxs-lookup"><span data-stu-id="3b60d-120">The reference is a weak reference, thus the naming of the weak event pattern and the related APIs.</span></span> <span data-ttu-id="3b60d-121">Der Listener kann Garbage gesammelt, oder andernfalls zerstört, und die Quelle kann weiterhin ohne Beibehaltung Handlerverweise auf ein jetzt zerstörte-Objekt.</span><span class="sxs-lookup"><span data-stu-id="3b60d-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="3b60d-122">Wer sollte das Muster für schwache Ereignisse implementieren?</span><span class="sxs-lookup"><span data-stu-id="3b60d-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="3b60d-123">Implementieren der Muster für schwache Ereignisse ist in erster Linie für Autoren von Steuerelementen interessant.</span><span class="sxs-lookup"><span data-stu-id="3b60d-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="3b60d-124">Als Autor eines Steuerelements sind Sie größtenteils verantwortlich für das Verhalten und die Kapselung der das Steuerelement und die Auswirkungen, die sie für Anwendungen in der er eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3b60d-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="3b60d-125">Dies schließt-Verhalten des Steuerelements Lebensdauer, insbesondere die Behandlung des Problems beschrieben Memory Leak.</span><span class="sxs-lookup"><span data-stu-id="3b60d-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="3b60d-126">Bestimmte Szenarien eignen sich grundsätzlich zur Anwendung des am schwachen Ereignismuster.</span><span class="sxs-lookup"><span data-stu-id="3b60d-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="3b60d-127">Ein solches Szenario ist die Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="3b60d-127">One such scenario is data binding.</span></span> <span data-ttu-id="3b60d-128">Bei der Datenbindung ist es üblich, dass das Quellobjekt ein Ziel einer Bindung ist vollkommen unabhängig von der kommunikationslistener-Objekt werden.</span><span class="sxs-lookup"><span data-stu-id="3b60d-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="3b60d-129">Viele Aspekte der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Datenbindung bereits am schwachen Ereignismuster in zur Implementierung von den Ereignissen angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="3b60d-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="3b60d-130">Gewusst wie: Implementieren der schwache Ereignismuster</span><span class="sxs-lookup"><span data-stu-id="3b60d-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="3b60d-131">Es gibt drei Möglichkeiten zum Implementieren der Muster für schwache Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="3b60d-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="3b60d-132">In der folgende Tabelle sind die drei Ansätze sowie hilfreiche Informationen zur beim verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3b60d-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="3b60d-133">Ansatz</span><span class="sxs-lookup"><span data-stu-id="3b60d-133">Approach</span></span>|<span data-ttu-id="3b60d-134">Für implementieren</span><span class="sxs-lookup"><span data-stu-id="3b60d-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="3b60d-135">Verwenden Sie eine vorhandene schwache Ereignis-Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="3b60d-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="3b60d-136">Wenn das Ereignis, das Sie abonnieren möchten ein entsprechendes hat <xref:System.Windows.WeakEventManager>, verwenden Sie den vorhandenen schwache Ereignis-Manager.</span><span class="sxs-lookup"><span data-stu-id="3b60d-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="3b60d-137">Eine Liste von Managern für schwache Ereignisse, die mit WPF enthalten sind, finden Sie in der Vererbungshierarchie in den <xref:System.Windows.WeakEventManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="3b60d-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="3b60d-138">Da die enthalten schwache Ereignis-Manager beschränkt sind, müssen Sie wahrscheinlich eine der anderen Ansätze auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3b60d-138">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="3b60d-139">Verwenden Sie eine generische schwache Ereignis-Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="3b60d-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="3b60d-140">Ein generisches <xref:System.Windows.WeakEventManager%602> bei einem vorhandenen <xref:System.Windows.WeakEventManager> ist nicht verfügbar ist, Sie möchten eine einfache Möglichkeit zum Implementieren und Sie sind nicht überlegen zu Effizienz.</span><span class="sxs-lookup"><span data-stu-id="3b60d-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="3b60d-141">Die generische <xref:System.Windows.WeakEventManager%602> ist weniger effizient als eine vorhandene oder benutzerdefinierte WeakEvent-Manager.</span><span class="sxs-lookup"><span data-stu-id="3b60d-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="3b60d-142">Beispielsweise ist die generische Klasse weitere Reflektion, um das Ereignis, erhält der Name eines Ereignisses zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="3b60d-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="3b60d-143">Außerdem wird im Code, der das Ereignis zu registrieren, indem Sie mithilfe der allgemeinen <xref:System.Windows.WeakEventManager%602> ist mehr ausführlicher als die Verwendung einer vorhandenen oder benutzerdefinierten <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="3b60d-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="3b60d-144">Erstellen Sie eine benutzerdefinierte schwache Ereignis-Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="3b60d-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="3b60d-145">Erstellen eines benutzerdefinierten <xref:System.Windows.WeakEventManager> bei einem vorhandenen <xref:System.Windows.WeakEventManager> ist nicht verfügbar und soll die Optimierung der Effizienz.</span><span class="sxs-lookup"><span data-stu-id="3b60d-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="3b60d-146">Mithilfe einer benutzerdefinierten <xref:System.Windows.WeakEventManager> zum Abonnieren ein Ereignisses wird effizienter sein, aber Sie fallen die Kosten für das Schreiben von weiteren Code am Anfang.</span><span class="sxs-lookup"><span data-stu-id="3b60d-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="3b60d-147">Verwenden Sie einen Drittanbieter-schwache Ereignis-manager</span><span class="sxs-lookup"><span data-stu-id="3b60d-147">Use a third-party weak event manager</span></span>|<span data-ttu-id="3b60d-148">NuGet kann [mehrere schwache Ereignis-Manager](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) und Frameworks für viele WPF unterstützen auch das Muster (z. B. finden Sie unter [von Prism-Dokumentation auf lose gekoppelte Ereignisabonnement](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span><span class="sxs-lookup"><span data-stu-id="3b60d-148">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="3b60d-149">In den folgenden Abschnitten wird beschrieben, wie das Muster für schwache Ereignisse zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="3b60d-149">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="3b60d-150">Für den Rahmen dieser Erläuterung weist folgende Merkmale auf das Ereignis abonnieren.</span><span class="sxs-lookup"><span data-stu-id="3b60d-150">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
- <span data-ttu-id="3b60d-151">Der Ereignisname wird `SomeEvent`.</span><span class="sxs-lookup"><span data-stu-id="3b60d-151">The event name is `SomeEvent`.</span></span>  
  
- <span data-ttu-id="3b60d-152">Das Ereignis wird ausgelöst, durch die `EventSource` Klasse.</span><span class="sxs-lookup"><span data-stu-id="3b60d-152">The event is raised by the `EventSource` class.</span></span>  
  
- <span data-ttu-id="3b60d-153">Der Ereignishandler verfügt über Typ: `SomeEventEventHandler` (oder `EventHandler<SomeEventEventArgs>`).</span><span class="sxs-lookup"><span data-stu-id="3b60d-153">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
- <span data-ttu-id="3b60d-154">Das Ereignis übergibt einen Parameter vom Typ `SomeEventEventArgs` an die Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="3b60d-154">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="3b60d-155">Verwenden einer vorhandenen schwache Ereignis-Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="3b60d-155">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="3b60d-156">Suchen Sie ein vorhandenes schwache Ereignis Manager.</span><span class="sxs-lookup"><span data-stu-id="3b60d-156">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="3b60d-157">Eine Liste von Managern für schwache Ereignisse, die mit WPF enthalten sind, finden Sie in der Vererbungshierarchie in den <xref:System.Windows.WeakEventManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="3b60d-157">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="3b60d-158">Verwenden Sie den neuen schwache Ereignis-Manager anstelle der normalen ereigniseinbindung an.</span><span class="sxs-lookup"><span data-stu-id="3b60d-158">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="3b60d-159">Angenommen, Ihr Code im folgenden Format verwendet, um ein Ereignis abonnieren:</span><span class="sxs-lookup"><span data-stu-id="3b60d-159">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="3b60d-160">Ändern Sie ihn an, in dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="3b60d-160">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="3b60d-161">Auf ähnliche Weise, wenn im Code das folgende Muster verwendet, um ein Ereignisabonnement zu kündigen:</span><span class="sxs-lookup"><span data-stu-id="3b60d-161">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="3b60d-162">Ändern Sie ihn an, in dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="3b60d-162">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="3b60d-163">Mithilfe der generischen schwache Ereignis-Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="3b60d-163">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="3b60d-164">Die generische <xref:System.Windows.WeakEventManager%602> -Klasse anstelle der normalen ereigniseinbindung.</span><span class="sxs-lookup"><span data-stu-id="3b60d-164">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="3b60d-165">Bei Verwendung von <xref:System.Windows.WeakEventManager%602> um Ereignislistener zu registrieren, geben Sie die Ereignisquelle und <xref:System.EventArgs> Typ wie die Typparameter von der Klasse und rufen <xref:System.Windows.WeakEventManager%602.AddHandler%2A> wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="3b60d-165">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="3b60d-166">Erstellen eine benutzerdefinierte schwache Ereignis-Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="3b60d-166">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="3b60d-167">Kopieren Sie die folgende Klassenvorlage in Ihr Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="3b60d-167">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="3b60d-168">Diese Klasse erbt von der <xref:System.Windows.WeakEventManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="3b60d-168">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="3b60d-169">Ersetzen Sie die `SomeEventWeakEventManager` durch den Namen Ihres eigenen Namen.</span><span class="sxs-lookup"><span data-stu-id="3b60d-169">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="3b60d-170">Ersetzen Sie die drei Namen, die zuvor mit den entsprechenden Namen für das Ereignis beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3b60d-170">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="3b60d-171">(`SomeEvent`, `EventSource`, und `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="3b60d-171">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="3b60d-172">Legen Sie die Sichtbarkeit der WeakEvent-Manager-Klasse (öffentliche / private / interne), auf die gleiche Sichtbarkeit wie Ereignis, das er verwaltet.</span><span class="sxs-lookup"><span data-stu-id="3b60d-172">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="3b60d-173">Verwenden Sie den neuen schwache Ereignis-Manager anstelle der normalen ereigniseinbindung an.</span><span class="sxs-lookup"><span data-stu-id="3b60d-173">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="3b60d-174">Angenommen, Ihr Code im folgenden Format verwendet, um ein Ereignis abonnieren:</span><span class="sxs-lookup"><span data-stu-id="3b60d-174">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="3b60d-175">Ändern Sie ihn an, in dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="3b60d-175">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="3b60d-176">Auf ähnliche Weise, wenn der Code das folgende Muster verwendet, um ein Ereignis kündigen:</span><span class="sxs-lookup"><span data-stu-id="3b60d-176">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="3b60d-177">Ändern Sie ihn an, in dem folgenden Muster:</span><span class="sxs-lookup"><span data-stu-id="3b60d-177">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3b60d-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b60d-178">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="3b60d-179">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="3b60d-179">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="3b60d-180">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="3b60d-180">Data Binding Overview</span></span>](../data/data-binding-overview.md)
