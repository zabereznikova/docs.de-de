---
title: Schwache Ereignismuster
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 9f61a5a60b2ba1305158d1ab570079fe6aac19ac
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870739"
---
# <a name="weak-event-patterns"></a><span data-ttu-id="f112e-102">Schwache Ereignismuster</span><span class="sxs-lookup"><span data-stu-id="f112e-102">Weak Event Patterns</span></span>
<span data-ttu-id="f112e-103">In-Anwendungen ist es möglich, dass an Ereignis Quellen angefügte Handler nicht in Abstimmung mit dem Listenerobjekt zerstört werden, das den Handler an die Quelle angefügt hat.</span><span class="sxs-lookup"><span data-stu-id="f112e-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="f112e-104">Diese Situation kann zu Speicher Verlusten führen.</span><span class="sxs-lookup"><span data-stu-id="f112e-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="f112e-105">führt ein Entwurfsmuster ein, das verwendet werden kann, um dieses Problem zu beheben, indem es eine dedizierte Manager-Klasse für bestimmte Ereignisse bereitstellt und eine Schnittstelle für Listener für dieses Ereignis implementiert.</span><span class="sxs-lookup"><span data-stu-id="f112e-105">introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="f112e-106">Dieses Entwurfsmuster wird als *schwaches Ereignis Muster*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f112e-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="f112e-107">Gründe für die Implementierung des schwachen Ereignis Musters</span><span class="sxs-lookup"><span data-stu-id="f112e-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="f112e-108">Das Lauschen auf Ereignisse kann zu Speicher Verlusten führen.</span><span class="sxs-lookup"><span data-stu-id="f112e-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="f112e-109">Die typische Vorgehensweise zum lauschen auf ein Ereignis besteht darin, die sprachspezifische Syntax zu verwenden, die einen Handler an ein Ereignis in einer Quelle anfügt.</span><span class="sxs-lookup"><span data-stu-id="f112e-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="f112e-110">In C#lautet die Syntax beispielsweise: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span><span class="sxs-lookup"><span data-stu-id="f112e-110">For example, in C#, that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="f112e-111">Diese Technik erstellt einen starken Verweis von der Ereignis Quelle auf den Ereignislistener.</span><span class="sxs-lookup"><span data-stu-id="f112e-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="f112e-112">Normalerweise bewirkt das Anfügen eines Ereignis Handlers für einen Listener, dass der Listener eine Objekt Lebensdauer hat, die von der Objekt Lebensdauer der Quelle beeinflusst wird (es sei denn, der Ereignishandler wird explizit entfernt).</span><span class="sxs-lookup"><span data-stu-id="f112e-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="f112e-113">Unter bestimmten Umständen möchten Sie jedoch möglicherweise, dass die Objekt Lebensdauer des Listener von anderen Faktoren gesteuert wird, z. b. ob er derzeit zur visuellen Struktur der Anwendung gehört, und nicht nach der Lebensdauer der Quelle.</span><span class="sxs-lookup"><span data-stu-id="f112e-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="f112e-114">Wenn die Lebensdauer des Quell Objekts über die Objekt Lebensdauer des Listener hinausgeht, führt das normale Ereignis Muster zu einem Speicherleck: der Listener bleibt länger als beabsichtigt.</span><span class="sxs-lookup"><span data-stu-id="f112e-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="f112e-115">Das schwache Ereignis Muster ist so konzipiert, dass dieses Speicherlecks-Problem gelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f112e-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="f112e-116">Das schwache Ereignis Muster kann immer dann verwendet werden, wenn ein Listener für ein Ereignis registriert werden muss, aber der Listener weiß nicht explizit, wann die Registrierung aufgehoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="f112e-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="f112e-117">Das schwache Ereignis Muster kann auch verwendet werden, wenn die Objekt Lebensdauer der Quelle die nützliche Objekt Lebensdauer des Listener überschreitet.</span><span class="sxs-lookup"><span data-stu-id="f112e-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="f112e-118">(In diesem Fall wird *nützlich* von Ihnen bestimmt.) Das schwache Ereignis Muster ermöglicht dem Listener, sich für das Ereignis zu registrieren und das Ereignis zu empfangen, ohne die Eigenschaften der Objekt Lebensdauer in irgendeiner Weise zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="f112e-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="f112e-119">Tatsächlich bestimmt der implizierte Verweis aus der Quelle nicht, ob der Listener für Garbage Collection geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="f112e-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="f112e-120">Der Verweis ist eine schwache Referenz und somit die Benennung des schwachen Ereignis Musters und der zugehörigen APIs.</span><span class="sxs-lookup"><span data-stu-id="f112e-120">The reference is a weak reference, thus the naming of the weak event pattern and the related APIs.</span></span> <span data-ttu-id="f112e-121">Der Listener kann auf eine Garbage Collection oder anderweitig zerstört werden, und die Quelle kann fortgesetzt werden, ohne dass nicht entladbare Handlerverweise auf ein jetzt zerstörtes Objekt beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="f112e-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="f112e-122">Wer sollte das schwache Ereignis Muster implementieren?</span><span class="sxs-lookup"><span data-stu-id="f112e-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="f112e-123">Die Implementierung des schwachen Ereignis Musters ist hauptsächlich für Autoren von Steuerelementen interessant.</span><span class="sxs-lookup"><span data-stu-id="f112e-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="f112e-124">Als Autor eines Steuer Elements sind Sie größtenteils verantwortlich für das Verhalten und die Kapselung Ihres Steuer Elements und die Auswirkungen, die es auf Anwendungen hat, in die es eingefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="f112e-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="f112e-125">Dies schließt das Verhalten der Steuerungsobjekt Lebensdauer ein, insbesondere die Behandlung des beschriebenen Speicherlecks Problems.</span><span class="sxs-lookup"><span data-stu-id="f112e-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="f112e-126">Bestimmte Szenarien sind von Natur aus für die Anwendung des schwachen Ereignis Musters geeignet.</span><span class="sxs-lookup"><span data-stu-id="f112e-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="f112e-127">Ein solches Szenario ist die Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="f112e-127">One such scenario is data binding.</span></span> <span data-ttu-id="f112e-128">Bei der Datenbindung ist es üblich, dass das Quell Objekt vollständig unabhängig vom Listenerobjekt ist, das das Ziel einer Bindung ist.</span><span class="sxs-lookup"><span data-stu-id="f112e-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="f112e-129">Viele Aspekte der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Datenbindung verfügen bereits über das schwache Ereignis Muster, das in der Implementierung der Ereignisse angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f112e-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="f112e-130">So implementieren Sie das schwache Ereignis Muster</span><span class="sxs-lookup"><span data-stu-id="f112e-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="f112e-131">Es gibt drei Möglichkeiten, ein schwaches Ereignis Muster zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="f112e-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="f112e-132">In der folgenden Tabelle werden die drei Ansätze aufgelistet und eine Anleitung für die Verwendung der einzelnen Methoden bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f112e-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="f112e-133">Ansatz</span><span class="sxs-lookup"><span data-stu-id="f112e-133">Approach</span></span>|<span data-ttu-id="f112e-134">Zeitpunkt der Implementierung</span><span class="sxs-lookup"><span data-stu-id="f112e-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="f112e-135">Vorhandene schwache Ereignis-Manager-Klasse verwenden</span><span class="sxs-lookup"><span data-stu-id="f112e-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="f112e-136">Wenn das Ereignis, das Sie abonnieren möchten, über ein entsprechendes <xref:System.Windows.WeakEventManager>verfügt, verwenden Sie den vorhandenen schwachen Ereignis-Manager.</span><span class="sxs-lookup"><span data-stu-id="f112e-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="f112e-137">Eine Liste der in WPF enthaltenen schwachen Ereignis-Manager finden Sie in der Vererbungs Hierarchie in der <xref:System.Windows.WeakEventManager>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f112e-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="f112e-138">Da die enthaltenen schwachen Ereignis-Manager eingeschränkt sind, müssen Sie wahrscheinlich einen der anderen Ansätze auswählen.</span><span class="sxs-lookup"><span data-stu-id="f112e-138">Because the included weak event managers are limited, you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="f112e-139">Verwenden einer generischen Weak EventManager-Klasse</span><span class="sxs-lookup"><span data-stu-id="f112e-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="f112e-140">Verwenden Sie einen generischen <xref:System.Windows.WeakEventManager%602>, wenn ein vorhandener <xref:System.Windows.WeakEventManager> nicht verfügbar ist, Sie möchten eine einfache Implementierung durchführen und sich keine Gedanken um die Effizienz machen.</span><span class="sxs-lookup"><span data-stu-id="f112e-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="f112e-141">Der generische <xref:System.Windows.WeakEventManager%602> ist weniger effizient als ein vorhandener oder benutzerdefinierter schwacher Ereignis-Manager.</span><span class="sxs-lookup"><span data-stu-id="f112e-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="f112e-142">Die generische Klasse führt z. b. mehr Reflektion aus, um das Ereignis anhand des Ereignis namens zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="f112e-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="f112e-143">Außerdem ist der Code zum Registrieren des Ereignisses mit dem generischen <xref:System.Windows.WeakEventManager%602> ausführlicher als die Verwendung eines vorhandenen oder benutzerdefinierten <xref:System.Windows.WeakEventManager>.</span><span class="sxs-lookup"><span data-stu-id="f112e-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="f112e-144">Erstellen einer benutzerdefinierten Weak EventManager-Klasse</span><span class="sxs-lookup"><span data-stu-id="f112e-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="f112e-145">Erstellen Sie eine benutzerdefinierte <xref:System.Windows.WeakEventManager>, wenn eine vorhandene <xref:System.Windows.WeakEventManager> nicht verfügbar ist und Sie die beste Effizienz erzielen möchten.</span><span class="sxs-lookup"><span data-stu-id="f112e-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="f112e-146">Die Verwendung eines benutzerdefinierten <xref:System.Windows.WeakEventManager> zum Abonnieren eines Ereignisses ist effizienter, aber Sie verursachen die Kosten für das Schreiben von mehr Code am Anfang.</span><span class="sxs-lookup"><span data-stu-id="f112e-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
|<span data-ttu-id="f112e-147">Verwenden eines schwachen Ereignis-Managers von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="f112e-147">Use a third-party weak event manager</span></span>|<span data-ttu-id="f112e-148">Nuget verfügt über [mehrere schwache Ereignis-Manager](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) , und viele WPF-Frameworks unterstützen auch das-Muster (z.b. [in der Prism-Dokumentation zu locker verknüpften Ereignis Abonnements](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).</span><span class="sxs-lookup"><span data-stu-id="f112e-148">NuGet has [several weak event managers](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) and many WPF frameworks also support the pattern (for instance, see [Prism's documentation on loosely coupled event subscription](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/legacy/Communication.md#subscribing-to-events)).</span></span>|

 <span data-ttu-id="f112e-149">In den folgenden Abschnitten wird beschrieben, wie das schwache Ereignis Muster implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="f112e-149">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="f112e-150">Im Rahmen dieser Erläuterung weist das Ereignis, das abonniert werden soll, die folgenden Eigenschaften auf.</span><span class="sxs-lookup"><span data-stu-id="f112e-150">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
- <span data-ttu-id="f112e-151">Der Ereignis Name ist `SomeEvent`.</span><span class="sxs-lookup"><span data-stu-id="f112e-151">The event name is `SomeEvent`.</span></span>  
  
- <span data-ttu-id="f112e-152">Das-Ereignis wird von der `EventSource`-Klasse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f112e-152">The event is raised by the `EventSource` class.</span></span>  
  
- <span data-ttu-id="f112e-153">Der Ereignishandler hat den Typ: `SomeEventEventHandler` (oder `EventHandler<SomeEventEventArgs>`).</span><span class="sxs-lookup"><span data-stu-id="f112e-153">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
- <span data-ttu-id="f112e-154">Das-Ereignis übergibt einen Parameter vom Typ `SomeEventEventArgs` an die Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="f112e-154">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="f112e-155">Verwenden einer vorhandenen Weak Event Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="f112e-155">Using an Existing Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="f112e-156">Suchen Sie einen vorhandenen schwachen Ereignis-Manager.</span><span class="sxs-lookup"><span data-stu-id="f112e-156">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="f112e-157">Eine Liste der in WPF enthaltenen schwachen Ereignis-Manager finden Sie in der Vererbungs Hierarchie in der <xref:System.Windows.WeakEventManager>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f112e-157">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2. <span data-ttu-id="f112e-158">Verwenden Sie den neuen schwachen Ereignis-Manager anstelle der normalen Ereignis Einbindung.</span><span class="sxs-lookup"><span data-stu-id="f112e-158">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="f112e-159">Wenn Ihr Code z. b. das folgende Muster verwendet, um ein Ereignis zu abonnieren:</span><span class="sxs-lookup"><span data-stu-id="f112e-159">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="f112e-160">Ändern Sie den Wert in das folgende Muster:</span><span class="sxs-lookup"><span data-stu-id="f112e-160">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="f112e-161">Ebenso, wenn Ihr Code das folgende Muster verwendet, um ein Ereignis abzubestellen:</span><span class="sxs-lookup"><span data-stu-id="f112e-161">Similarly, if your code uses the following pattern to unsubscribe from an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="f112e-162">Ändern Sie den Wert in das folgende Muster:</span><span class="sxs-lookup"><span data-stu-id="f112e-162">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="f112e-163">Verwenden der generischen Weak Event Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="f112e-163">Using the Generic Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="f112e-164">Verwenden Sie die generische <xref:System.Windows.WeakEventManager%602>-Klasse anstelle der normalen Ereignis Einbindung.</span><span class="sxs-lookup"><span data-stu-id="f112e-164">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="f112e-165">Wenn Sie <xref:System.Windows.WeakEventManager%602> zum Registrieren von Ereignislistenern verwenden, geben Sie die Ereignis Quelle und <xref:System.EventArgs> Typ als Typparameter für die Klasse an, und wenden Sie <xref:System.Windows.WeakEventManager%602.AddHandler%2A> an, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f112e-165">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```csharp  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="f112e-166">Erstellen einer benutzerdefinierten Weak Event Manager-Klasse</span><span class="sxs-lookup"><span data-stu-id="f112e-166">Creating a Custom Weak Event Manager Class</span></span>  
  
1. <span data-ttu-id="f112e-167">Kopieren Sie die folgende Klassen Vorlage in Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="f112e-167">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="f112e-168">Diese Klasse erbt von der <xref:System.Windows.WeakEventManager>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f112e-168">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2. <span data-ttu-id="f112e-169">Ersetzen Sie den `SomeEventWeakEventManager` Namen durch ihren eigenen Namen.</span><span class="sxs-lookup"><span data-stu-id="f112e-169">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3. <span data-ttu-id="f112e-170">Ersetzen Sie die drei zuvor beschriebenen Namen durch die entsprechenden Namen für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="f112e-170">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="f112e-171">(`SomeEvent`, `EventSource`und `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="f112e-171">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4. <span data-ttu-id="f112e-172">Legen Sie die Sichtbarkeit (Public/Internal/private) der Weak EventManager-Klasse auf die gleiche Sichtbarkeit wie das Ereignis fest, das Sie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f112e-172">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5. <span data-ttu-id="f112e-173">Verwenden Sie den neuen schwachen Ereignis-Manager anstelle der normalen Ereignis Einbindung.</span><span class="sxs-lookup"><span data-stu-id="f112e-173">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="f112e-174">Wenn Ihr Code z. b. das folgende Muster verwendet, um ein Ereignis zu abonnieren:</span><span class="sxs-lookup"><span data-stu-id="f112e-174">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="f112e-175">Ändern Sie den Wert in das folgende Muster:</span><span class="sxs-lookup"><span data-stu-id="f112e-175">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="f112e-176">Ebenso, wenn Ihr Code das folgende Muster verwendet, um ein Ereignis abzubestellen:</span><span class="sxs-lookup"><span data-stu-id="f112e-176">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```csharp  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="f112e-177">Ändern Sie den Wert in das folgende Muster:</span><span class="sxs-lookup"><span data-stu-id="f112e-177">Change it to the following pattern:</span></span>  
  
    ```csharp  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f112e-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f112e-178">See also</span></span>

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [<span data-ttu-id="f112e-179">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="f112e-179">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="f112e-180">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="f112e-180">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
