---
title: Implementieren des ereignisbasierten asynchronen Entwurfsmusters
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b4df5e4df914d932c7413e9330e8663753456c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="4d653-102">Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="4d653-102">Implementing the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="4d653-103">Wenn Sie eine Klasse mit Vorgängen schreiben, die nennenswerte Verzögerungen verursachen können, sollten Sie die Klasse mit einer asynchronen Funktionalität ausstatten, indem Sie das ereignisbasierte asynchrone Muster implementieren. Informationen zu diesem Muster finden Sie unter [Übersicht über ereignisbasierte asynchrone Muster](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4d653-103">If you are writing a class with some operations that may incur noticeable delays, consider giving it asynchronous functionality by implementing [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>  
  
 <span data-ttu-id="4d653-104">Das ereignisbasierte asynchrone Muster bietet eine standardisierte Möglichkeit zum Verpacken einer Klasse, die asynchrone Features hat.</span><span class="sxs-lookup"><span data-stu-id="4d653-104">The Event-based Asynchronous Pattern provides a standardized way to package a class that has asynchronous features.</span></span> <span data-ttu-id="4d653-105">Wenn Hilfsklassen implementiert wie <xref:System.ComponentModel.AsyncOperationManager>, Ihre Klasse funktionieren ordnungsgemäß unter jedem beliebigen Anwendungsmodell einschließlich [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], konsolenanwendungen und Windows Forms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="4d653-105">If implemented with helper classes like <xref:System.ComponentModel.AsyncOperationManager>, your class will work correctly under any application model, including [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], Console applications, and Windows Forms applications.</span></span>  
  
 <span data-ttu-id="4d653-106">Ein Beispiel, in dem das ereignisbasierte asynchrone Muster implementiert ist, finden Sie unter [Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="4d653-106">For an example that implements the Event-based Asynchronous Pattern, see [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="4d653-107">Für einfache asynchrone Operationen finden Sie möglicherweise die <xref:System.ComponentModel.BackgroundWorker> Komponente geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="4d653-107">For simple asynchronous operations, you may find the <xref:System.ComponentModel.BackgroundWorker> component suitable.</span></span> <span data-ttu-id="4d653-108">Weitere Informationen zu <xref:System.ComponentModel.BackgroundWorker>, finden Sie unter [Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="4d653-108">For more information about <xref:System.ComponentModel.BackgroundWorker>, see [How to: Run an Operation in the Background](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>  
  
 <span data-ttu-id="4d653-109">In der folgenden Liste sind die Features des ereignisbasierten asynchronen Musters aufgeführt, die in diesem Thema beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="4d653-109">The following list describes the features of the Event-based Asynchronous Pattern discussed in this topic.</span></span>  
  
-   <span data-ttu-id="4d653-110">Gelegenheiten für Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="4d653-110">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>  
  
-   <span data-ttu-id="4d653-111">Benennen von asynchronen Methoden</span><span class="sxs-lookup"><span data-stu-id="4d653-111">Naming Asynchronous Methods</span></span>  
  
-   <span data-ttu-id="4d653-112">Optionales Unterstützen von Abbruch</span><span class="sxs-lookup"><span data-stu-id="4d653-112">Optionally Support Cancellation</span></span>  
  
-   <span data-ttu-id="4d653-113">Optionales Unterstützen der „IsBusy“-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4d653-113">Optionally Support the IsBusy Property</span></span>  
  
-   <span data-ttu-id="4d653-114">Optionales Unterstützen von Statusberichterstellung</span><span class="sxs-lookup"><span data-stu-id="4d653-114">Optionally Provide Support for Progress Reporting</span></span>  
  
-   <span data-ttu-id="4d653-115">Optionales Unterstützen der Rückgabe von inkrementellen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="4d653-115">Optionally Provide Support for Returning Incremental Results</span></span>  
  
-   <span data-ttu-id="4d653-116">Verarbeiten von „out“- und „ref“-Parametern in Methoden</span><span class="sxs-lookup"><span data-stu-id="4d653-116">Handling Out and Ref Parameters in Methods</span></span>  
  
## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="4d653-117">Gelegenheiten für Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="4d653-117">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>  
 <span data-ttu-id="4d653-118">Implementieren des ereignisbasierten asynchronen Entwurfsmusters bietet sich an, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="4d653-118">Consider implementing the Event-based Asynchronous Pattern when:</span></span>  
  
-   <span data-ttu-id="4d653-119">Clients einer Klasse müssen nicht <xref:System.Threading.WaitHandle> und <xref:System.IAsyncResult> für die asynchrone Operationen, d. h., die Abfrage der verfügbaren Objekte und <xref:System.Threading.WaitHandle.WaitAll%2A> oder <xref:System.Threading.WaitHandle.WaitAny%2A> müssen vom Client aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="4d653-119">Clients of your class do not need <xref:System.Threading.WaitHandle> and <xref:System.IAsyncResult> objects available for asynchronous operations, meaning that polling and <xref:System.Threading.WaitHandle.WaitAll%2A> or <xref:System.Threading.WaitHandle.WaitAny%2A> will need to be built up by the client.</span></span>  
  
-   <span data-ttu-id="4d653-120">Asynchrone Vorgänge sollen vom Client mit dem vertrauten Ereignis/Delegat-Modell verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4d653-120">You want asynchronous operations to be managed by the client with the familiar event/delegate model.</span></span>  
  
 <span data-ttu-id="4d653-121">Jeder Vorgang ist ein Kandidat für eine asynchrone Implementierung, aber ein Vorgang, für den Sie lange Wartezeiten erwarten, sollte auf alle Fälle berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="4d653-121">Any operation is a candidate for an asynchronous implementation, but those you expect to incur long latencies should be considered.</span></span> <span data-ttu-id="4d653-122">Besonders geeignet sind Vorgänge, in denen Clients eine Methode aufrufen und bei Abschluss benachrichtigt werden, ohne dass weiteres Eingreifen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4d653-122">Especially appropriate are operations in which clients call a method and are notified on completion, with no further intervention required.</span></span> <span data-ttu-id="4d653-123">Geeignet sind außerdem Vorgänge, die durchgängig ausgeführt werden und dabei Clients regelmäßig über Fortschritte, inkrementelle Ergebnisse oder Zustandsänderungen benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="4d653-123">Also appropriate are operations which run continuously, periodically notifying clients of progress, incremental results, or state changes.</span></span>  
  
 <span data-ttu-id="4d653-124">Weitere Informationen dazu, wie entschieden werden soll, ob das ereignisbasierte asynchrone Muster unterstützt werden sollte, finden Sie unter [Gründe für das Implementieren des ereignisbasierten asynchronen Musters](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="4d653-124">For more information on deciding when to support the Event-based Asynchronous Pattern, see [Deciding When to Implement the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="naming-asynchronous-methods"></a><span data-ttu-id="4d653-125">Benennen von asynchronen Methoden</span><span class="sxs-lookup"><span data-stu-id="4d653-125">Naming Asynchronous Methods</span></span>  
 <span data-ttu-id="4d653-126">Definieren Sie für jede synchrone Methode *MethodName*, für die Sie ein asynchrones Gegenstück bereitstellen möchten, Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4d653-126">For each synchronous method *MethodName* for which you want to provide an asynchronous counterpart:</span></span>  
  
 <span data-ttu-id="4d653-127">Eine *MethodName*`Async`-Methode, die:</span><span class="sxs-lookup"><span data-stu-id="4d653-127">Define a *MethodName*`Async` method that:</span></span>  
  
-   <span data-ttu-id="4d653-128">Gibt `void`zurück.</span><span class="sxs-lookup"><span data-stu-id="4d653-128">Returns `void`.</span></span>  
  
-   <span data-ttu-id="4d653-129">Dieselben Parameter hat wie die *MethodName*-Methode.</span><span class="sxs-lookup"><span data-stu-id="4d653-129">Takes the same parameters as the *MethodName* method.</span></span>  
  
-   <span data-ttu-id="4d653-130">Mehrere Aufrufe akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4d653-130">Accepts multiple invocations.</span></span>  
  
 <span data-ttu-id="4d653-131">Definieren Sie optional eine *MethodName*`Async`-Überladung, die mit *MethodName*`Async` identisch ist, aber einen zusätzlichen Objekt-Parameter namens `userState` hat.</span><span class="sxs-lookup"><span data-stu-id="4d653-131">Optionally define a *MethodName*`Async` overload, identical to *MethodName*`Async`, but with an additional object-valued parameter called `userState`.</span></span> <span data-ttu-id="4d653-132">Dies sollten Sie tun, wenn Sie mehrere gleichzeitige Aufrufe der Methode verwalten möchten. In diesem Fall wird der `userState`-Wert an alle Ereignishandler zurückgegeben, um die Aufrufe der Methode zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4d653-132">Do this if you're prepared to manage multiple concurrent invocations of your method, in which case the `userState` value will be delivered back to all event handlers to distinguish invocations of the method.</span></span> <span data-ttu-id="4d653-133">Diese Vorgehensweise bietet sich auch an, wenn Sie einfach einen Platz haben möchten, in dem der Benutzerstatus für spätere Abrufe gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d653-133">You may also choose to do this simply as a place to store user state for later retrieval.</span></span>  
  
 <span data-ttu-id="4d653-134">Definieren Sie für jede einzelne *MethodName*`Async`-Methodensignatur:</span><span class="sxs-lookup"><span data-stu-id="4d653-134">For each separate *MethodName*`Async` method signature:</span></span>  
  
1.  <span data-ttu-id="4d653-135">Das folgende Ereignis in derselben Klasse wie die Methode:</span><span class="sxs-lookup"><span data-stu-id="4d653-135">Define the following event in the same class as the method:</span></span>  
  
    ```vb  
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler  
    ```  
  
    ```csharp  
    public event MethodNameCompletedEventHandler MethodNameCompleted;  
    ```  
  
2.  <span data-ttu-id="4d653-136">Der folgende Delegat definieren und <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="4d653-136">Define the following delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span></span> <span data-ttu-id="4d653-137">Diese sind wahrscheinlich außerhalb der Klasse selbst, aber im selben Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="4d653-137">These will likely be defined outside of the class itself, but in the same namespace.</span></span>  
  
    ```vb  
    Public Delegate Sub MethodNameCompletedEventHandler( _  
        ByVal sender As Object, _  
        ByVal e As MethodNameCompletedEventArgs)  
  
    Public Class MethodNameCompletedEventArgs  
        Inherits System.ComponentModel.AsyncCompletedEventArgs  
    Public ReadOnly Property Result() As MyReturnType  
    End Property  
    ```  
  
    ```csharp  
    public delegate void MethodNameCompletedEventHandler(object sender,   
        MethodNameCompletedEventArgs e);  
  
    public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs  
    {  
        public MyReturnType Result { get; }  
    }  
    ```  
  
    -   <span data-ttu-id="4d653-138">Stellen Sie sicher, dass die *MethodName*`CompletedEventArgs`-Klasse ihre Member als schreibgeschützte Eigenschaften, nicht als Felder verfügbar macht, weil Felder Datenbindung verhindern.</span><span class="sxs-lookup"><span data-stu-id="4d653-138">Ensure that the *MethodName*`CompletedEventArgs` class exposes its members as read-only properties, and not fields, as fields prevent data binding.</span></span>  
  
    -   <span data-ttu-id="4d653-139">Definiert keine <xref:System.ComponentModel.AsyncCompletedEventArgs>-abgeleitete Klassen für Methoden, die keine Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="4d653-139">Do not define any <xref:System.ComponentModel.AsyncCompletedEventArgs>-derived classes for methods that do not produce results.</span></span> <span data-ttu-id="4d653-140">Verwenden Sie einfach eine Instanz von <xref:System.ComponentModel.AsyncCompletedEventArgs> selbst.</span><span class="sxs-lookup"><span data-stu-id="4d653-140">Simply use an instance of <xref:System.ComponentModel.AsyncCompletedEventArgs> itself.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4d653-141">Es ist durchaus akzeptabel, wenn machbar und angemessen, Delegaten wiederverwenden und <xref:System.ComponentModel.AsyncCompletedEventArgs> Typen.</span><span class="sxs-lookup"><span data-stu-id="4d653-141">It is perfectly acceptable, when feasible and appropriate, to reuse delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> types.</span></span> <span data-ttu-id="4d653-142">In diesem Fall die Benennung nicht konsistent sein werden, wie durch den Methodennamen, da ein gegebener Delegat und <xref:System.ComponentModel.AsyncCompletedEventArgs> wird nicht an eine einzelne Methode gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="4d653-142">In this case, the naming will not be as consistent with the method name, since a given delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> won't be tied to a single method.</span></span>  
  
## <a name="optionally-support-cancellation"></a><span data-ttu-id="4d653-143">Optionales Unterstützen von Abbruch</span><span class="sxs-lookup"><span data-stu-id="4d653-143">Optionally Support Cancellation</span></span>  
 <span data-ttu-id="4d653-144">Wenn Ihre Klasse das Abbrechen von asynchronen Vorgängen unterstützt, sollte Abbruch so für den Client verfügbar gemacht werden, wie dies weiter unten beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="4d653-144">If your class will support canceling asynchronous operations, cancellation should be exposed to the client as described below.</span></span> <span data-ttu-id="4d653-145">Es gibt zwei Entscheidungspunkte, die erreicht sein müssen, bevor Abbruchunterstützung definiert wird:</span><span class="sxs-lookup"><span data-stu-id="4d653-145">Note that there are two decision points that need to be reached before defining your cancellation support:</span></span>  
  
-   <span data-ttu-id="4d653-146">Hat die Klasse, einschließlich zukünftiger zu erwartender Erweiterungen, nur einen asynchronen Vorgang, der Abbruch unterstützt?</span><span class="sxs-lookup"><span data-stu-id="4d653-146">Does your class, including future anticipated additions to it, have only one asynchronous operation that supports cancellation?</span></span>  
  
-   <span data-ttu-id="4d653-147">Können die asynchronen Vorgänge, die Abbruch unterstützen, mehrere ausstehende Vorgänge unterstützen?</span><span class="sxs-lookup"><span data-stu-id="4d653-147">Can the asynchronous operations that support cancellation support multiple pending operations?</span></span> <span data-ttu-id="4d653-148">Das heißt, hat die *MethodName* `Async`-Methode den `userState`-Parameter, und lässt sie mehrere Aufrufe zu, bevor sie für jeden auf dessen Beendigung wartet?</span><span class="sxs-lookup"><span data-stu-id="4d653-148">That is, does the *MethodName*`Async` method take a `userState` parameter, and does it allow multiple invocations before waiting for any to finish?</span></span>  
  
 <span data-ttu-id="4d653-149">Entscheiden Sie anhand der Antworten auf die beiden Fragen in der folgenden Tabelle, welche Signatur für die Abbruchmethode zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="4d653-149">Use the answers to these two questions in the table below to determine what the signature for your cancellation method should be.</span></span>  
  
### <a name="visual-basic"></a><span data-ttu-id="4d653-150">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d653-150">Visual Basic</span></span>  
  
||<span data-ttu-id="4d653-151">Mehrere gleichzeitige Vorgänge unterstützt</span><span class="sxs-lookup"><span data-stu-id="4d653-151">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="4d653-152">Nur immer jeweils ein Vorgang</span><span class="sxs-lookup"><span data-stu-id="4d653-152">Only One Operation at a Time</span></span>|  
|------|------------------------------------------------|----------------------------------|  
|<span data-ttu-id="4d653-153">Ein asynchroner Vorgang in der gesamten Klasse</span><span class="sxs-lookup"><span data-stu-id="4d653-153">One Async Operation in entire class</span></span>|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|  
|<span data-ttu-id="4d653-154">Mehrere asynchrone Vorgänge in der Klasse</span><span class="sxs-lookup"><span data-stu-id="4d653-154">Multiple Async Operations in class</span></span>|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|  
  
### <a name="c"></a><span data-ttu-id="4d653-155">C#</span><span class="sxs-lookup"><span data-stu-id="4d653-155">C#</span></span>  
  
||<span data-ttu-id="4d653-156">Mehrere gleichzeitige Vorgänge unterstützt</span><span class="sxs-lookup"><span data-stu-id="4d653-156">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="4d653-157">Nur immer jeweils ein Vorgang</span><span class="sxs-lookup"><span data-stu-id="4d653-157">Only One Operation at a Time</span></span>|  
|------|------------------------------------------------|----------------------------------|  
|<span data-ttu-id="4d653-158">Ein asynchroner Vorgang in der gesamten Klasse</span><span class="sxs-lookup"><span data-stu-id="4d653-158">One Async Operation in entire class</span></span>|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|  
|<span data-ttu-id="4d653-159">Mehrere asynchrone Vorgänge in der Klasse</span><span class="sxs-lookup"><span data-stu-id="4d653-159">Multiple Async Operations in class</span></span>|`void CancelAsync(object userState);`|`void CancelAsync();`|  
  
 <span data-ttu-id="4d653-160">Wenn Sie die `CancelAsync(object userState)`-Methode definieren, müssen Clients bei der Auswahl ihrer Statuswerte vorsichtig sein, damit sie in der Lage sind, zwischen allen für das Objekt aufgerufenen asynchronen Methoden, nicht nur zwischen allen Aufrufen einer einzigen asynchronen Methode zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4d653-160">If you define the `CancelAsync(object userState)` method, clients must be careful when choosing their state values to make them capable of distinguishing among all asynchronous methods invoked on the object, and not just between all invocations of a single asynchronous method.</span></span>  
  
 <span data-ttu-id="4d653-161">Die Entscheidung, die Version mit einzelnem asynchronen Vorgang als *MethodName*`AsyncCancel` zu benennen, basiert darauf, die Möglichkeit zu haben, die Methode in einer Entwurfsumgebung wie Visual Studios IntelliSense einfacher erkennen zu können.</span><span class="sxs-lookup"><span data-stu-id="4d653-161">The decision to name the single-async-operation version *MethodName*`AsyncCancel` is based on being able to more easily discover the method in a design environment like Visual Studio's IntelliSense.</span></span> <span data-ttu-id="4d653-162">Dadurch werden die zusammengehörenden Member gruppiert und lassen sich von anderen Membern unterscheiden, die nichts mit der asynchronen Funktionalität zu tun haben.</span><span class="sxs-lookup"><span data-stu-id="4d653-162">This groups the related members and distinguishes them from other members that have nothing to do with asynchronous functionality.</span></span> <span data-ttu-id="4d653-163">Wenn Sie davon ausgehen, dass in späteren Versionen weitere asynchrone Vorgänge hinzugefügt werden, sollten Sie `CancelAsync` definieren.</span><span class="sxs-lookup"><span data-stu-id="4d653-163">If you expect that there may be additional asynchronous operations added in subsequent versions, it is better to define `CancelAsync`.</span></span>  
  
 <span data-ttu-id="4d653-164">Definieren Sie nicht mehrere Methoden aus der obigen Tabelle in derselben Klasse.</span><span class="sxs-lookup"><span data-stu-id="4d653-164">Do not define multiple methods from the table above in the same class.</span></span> <span data-ttu-id="4d653-165">Dies ist nicht sinnvoll oder führt dazu, dass in der Klassenschnittstelle unnötig viele Methoden bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4d653-165">That will not make sense, or it will clutter the class interface with a proliferation of methods.</span></span>  
  
 <span data-ttu-id="4d653-166">Diese Methoden führen üblicherweise sofort eine Rückkehr aus, und der Vorgang wird möglicherweise tatsächlich abgebrochen (oder nicht).</span><span class="sxs-lookup"><span data-stu-id="4d653-166">These methods typically will return immediately, and the operation may or may not actually cancel.</span></span> <span data-ttu-id="4d653-167">Im Ereignishandler für das *MethodName*`Completed`-Ereignis enthält das *MethodName* `CompletedEventArgs`-Objekt ein `Cancelled`-Feld, anhand dem Clients ermitteln können, ob der Abbruch aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4d653-167">In the event handler for the *MethodName*`Completed` event, the *MethodName*`CompletedEventArgs` object contains a `Cancelled` field, which clients can use to determine whether the cancellation occurred.</span></span>  
  
 <span data-ttu-id="4d653-168">Halten Sie sich an die Abbruchsemantik, die unter [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="4d653-168">Abide by the cancellation semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="optionally-support-the-isbusy-property"></a><span data-ttu-id="4d653-169">Optionales Unterstützen der „IsBusy“-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4d653-169">Optionally Support the IsBusy Property</span></span>  
 <span data-ttu-id="4d653-170">Unterstützt die Klasse nicht mehrere gleichzeitige Aufrufe, sollten Sie eine `IsBusy`-Eigenschaft verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="4d653-170">If your class does not support multiple concurrent invocations, consider exposing an `IsBusy` property.</span></span> <span data-ttu-id="4d653-171">Dies ermöglicht Entwicklern, zu bestimmen, ob eine *MethodName*`Async`-Methode ausgeführt wird, ohne eine Ausnahme von der *MethodName*`Async`-Methode abzufangen.</span><span class="sxs-lookup"><span data-stu-id="4d653-171">This allows developers to determine whether a *MethodName*`Async` method is running without catching an exception from the *MethodName*`Async` method.</span></span>  
  
 <span data-ttu-id="4d653-172">Halten Sie sich an die `IsBusy`-Semantik, die unter [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="4d653-172">Abide by the `IsBusy` semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="optionally-provide-support-for-progress-reporting"></a><span data-ttu-id="4d653-173">Optionales Unterstützen von Statusberichterstellung</span><span class="sxs-lookup"><span data-stu-id="4d653-173">Optionally Provide Support for Progress Reporting</span></span>  
 <span data-ttu-id="4d653-174">Es ist häufig wünschenswert, dass ein asynchroner Vorgang während seiner Ausführung den Status mitteilt.</span><span class="sxs-lookup"><span data-stu-id="4d653-174">It is frequently desirable for an asynchronous operation to report progress during its operation.</span></span> <span data-ttu-id="4d653-175">Das ereignisbasierte asynchrone Muster stellt eine Richtlinie dafür bereit.</span><span class="sxs-lookup"><span data-stu-id="4d653-175">The Event-based Asynchronous Pattern provides a guideline for doing so.</span></span>  
  
-   <span data-ttu-id="4d653-176">Definieren Sie optional ein Ereignis, das vom asynchronen Vorgang ausgelöst und im entsprechenden Thread aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4d653-176">Optionally define an event to be raised by the asynchronous operation and invoked on the appropriate thread.</span></span> <span data-ttu-id="4d653-177">Die <xref:System.ComponentModel.ProgressChangedEventArgs> Objekt enthält eine Ganzzahlwerttyp Statusanzeige, die zwischen 0 und 100 liegen soll.</span><span class="sxs-lookup"><span data-stu-id="4d653-177">The <xref:System.ComponentModel.ProgressChangedEventArgs> object carries an integer-valued progress indicator that is expected to be between 0 and 100.</span></span>  
  
-   <span data-ttu-id="4d653-178">Benennen Sie dieses Ereignis wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4d653-178">Name this event as follows:</span></span>  
  
    -   <span data-ttu-id="4d653-179">`ProgressChanged`, wenn die Klasse mehrere asynchrone Vorgänge hat (oder vermutlich so erweitert wird, dass sie in zukünftigen Versionen mehrere asynchrone Vorgänge haben wird)</span><span class="sxs-lookup"><span data-stu-id="4d653-179">`ProgressChanged` if the class has multiple asynchronous operations (or is expected to grow to include multiple asynchronous operations in future versions);</span></span>  
  
    -   <span data-ttu-id="4d653-180">*MethodName*`ProgressChanged`, wenn die Klasse einen einzelnen asynchronen Vorgang hat</span><span class="sxs-lookup"><span data-stu-id="4d653-180">*MethodName* `ProgressChanged` if the class has a single asynchronous operation.</span></span>  
  
     <span data-ttu-id="4d653-181">Diese Benennungskonvention entspricht derjenigen für die Abbruchmethode, wie im Abschnitt „Optionales Unterstützen von Abbruch“ beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4d653-181">This naming choice parallels that made for the cancellation method, as described in the Optionally Support Cancellation section.</span></span>  
  
 <span data-ttu-id="4d653-182">Verwenden Sie dieses Ereignis sollte die <xref:System.ComponentModel.ProgressChangedEventHandler> Signatur des Delegaten und der <xref:System.ComponentModel.ProgressChangedEventArgs> Klasse.</span><span class="sxs-lookup"><span data-stu-id="4d653-182">This event should use the <xref:System.ComponentModel.ProgressChangedEventHandler> delegate signature and the <xref:System.ComponentModel.ProgressChangedEventArgs> class.</span></span> <span data-ttu-id="4d653-183">Auch wenn eine Statusanzeige mehr domänenspezifische (für die Instanz Bytes liest und die Gesamtanzahl der Bytes für ein Download-Vorgang) bereitgestellt werden kann, Sie sollten definieren eine abgeleitete Klasse von <xref:System.ComponentModel.ProgressChangedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="4d653-183">Alternatively, if a more domain-specific progress indicator can be provided (for instance, bytes read and total bytes for a download operation), then you should define a derived class of <xref:System.ComponentModel.ProgressChangedEventArgs>.</span></span>  
  
 <span data-ttu-id="4d653-184">Beachten Sie, dass es nur ein `ProgressChanged`- oder *MethodName*`ProgressChanged`-Ereignis für die Klasse gibt, unabhängig davon, wie viele asynchrone Methoden sie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4d653-184">Note that there is only one `ProgressChanged` or *MethodName*`ProgressChanged` event for the class, regardless of the number of asynchronous methods it supports.</span></span> <span data-ttu-id="4d653-185">Für Clients wird vorausgesetzt, dass sie das `userState`-Objekt, das an die *MethodName*`Async`-Methoden übergeben wird, verwenden, um zwischen Statusupdates bei mehreren gleichzeitigen Vorgängen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4d653-185">Clients are expected to use the `userState` object that is passed to the *MethodName*`Async` methods to distinguish among progress updates on multiple concurrent operations.</span></span>  
  
 <span data-ttu-id="4d653-186">Es kann Situationen geben, in denen mehrere Vorgänge einen Status unterstützen und jeder Vorgang einen anderen Indikator für den Status zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4d653-186">There may be situations in which multiple operations support progress and each returns a different indicator for progress.</span></span> <span data-ttu-id="4d653-187">In diesem Fall ist ein einzelnes `ProgressChanged`-Ereignis nicht geeignet, und Sie sollten Unterstützung für mehrere `ProgressChanged`-Ereignisse erwägen.</span><span class="sxs-lookup"><span data-stu-id="4d653-187">In this case, a single `ProgressChanged` event is not appropriate, and you may consider supporting multiple `ProgressChanged` events.</span></span> <span data-ttu-id="4d653-188">Verwenden Sie für diesen Fall das Benennungsmuster *MethodName*`ProgressChanged` für jede *MethodName*`Async`-Methode.</span><span class="sxs-lookup"><span data-stu-id="4d653-188">In this case use a naming pattern of *MethodName*`ProgressChanged` for each *MethodName*`Async` method.</span></span>  
  
 <span data-ttu-id="4d653-189">Halten Sie sich an die Statusberichte-Semantik, die unter [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="4d653-189">Abide by the progress-reporting semantics described [Best Practices for Implementing the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="optionally-provide-support-for-returning-incremental-results"></a><span data-ttu-id="4d653-190">Optionales Unterstützen der Rückgabe von inkrementellen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="4d653-190">Optionally Provide Support for Returning Incremental Results</span></span>  
 <span data-ttu-id="4d653-191">Möglicherweise gibt ein asynchroner Vorgang vor seiner Beendigung inkrementelle Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="4d653-191">Sometimes an asynchronous operation can return incremental results prior to completion.</span></span> <span data-ttu-id="4d653-192">Zur Unterstützung dieses Szenarios gibt es eine Reihe von Optionen, die verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4d653-192">There are a number of options that can be used to support this scenario.</span></span> <span data-ttu-id="4d653-193">Es folgen einige Beispiele.</span><span class="sxs-lookup"><span data-stu-id="4d653-193">Some examples follow.</span></span>  
  
### <a name="single-operation-class"></a><span data-ttu-id="4d653-194">Klasse mit einem einzigen Vorgang</span><span class="sxs-lookup"><span data-stu-id="4d653-194">Single-operation Class</span></span>  
 <span data-ttu-id="4d653-195">Unterstützt die Klasse nur einen einzigen asynchronen Vorgang, und kann dieser Vorgang inkrementelle Ergebnisse zurückgeben, dann gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="4d653-195">If your class only supports a single asynchronous operation, and that operation is able to return incremental results, then:</span></span>  
  
-   <span data-ttu-id="4d653-196">Erweitern der <xref:System.ComponentModel.ProgressChangedEventArgs> um inkrementelle Ergebnisdaten durchzuführen, und definieren einen *MethodName* `ProgressChanged` Ereignis mit dieser erweiterten Daten.</span><span class="sxs-lookup"><span data-stu-id="4d653-196">Extend the <xref:System.ComponentModel.ProgressChangedEventArgs> type to carry the incremental result data, and define a *MethodName*`ProgressChanged` event with this extended data.</span></span>  
  
-   <span data-ttu-id="4d653-197">Lösen Sie dieses *MethodName*`ProgressChanged`-Ereignis aus, sobald ein zu berichtendes inkrementelles Ergebnis vorliegt.</span><span class="sxs-lookup"><span data-stu-id="4d653-197">Raise this *MethodName*`ProgressChanged` event when there is an incremental result to report.</span></span>  
  
 <span data-ttu-id="4d653-198">Diese Lösung ist speziell für eine Klasse mit einzelnem asynchronen Vorgang anwendbar, weil es kein Problem damit gibt, dass dasselbe auftretende Ereignis inkrementelle Ergebnisse für „alle Vorgänge“ zurückgibt, denn das *MethodName*`ProgressChanged`-Ereignis erledigt dies.</span><span class="sxs-lookup"><span data-stu-id="4d653-198">This solution applies specifically to a single-async-operation class because there is no problem with the same event occurring to return incremental results on "all operations", as the *MethodName*`ProgressChanged` event does.</span></span>  
  
### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a><span data-ttu-id="4d653-199">Klasse mit mehreren Vorgängen und homogenen inkrementellen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="4d653-199">Multiple-operation Class with Homogeneous Incremental Results</span></span>  
 <span data-ttu-id="4d653-200">In diesem Fall unterstützt die Klasse mehrere asynchrone Methoden, von denen jede inkrementelle Ergebnisse zurückgeben kann, wobei diese inkrementellen Ergebnisse alle denselben Datentyp haben.</span><span class="sxs-lookup"><span data-stu-id="4d653-200">In this case, your class supports multiple asynchronous methods, each capable of returning incremental results, and these incremental results all have the same type of data.</span></span>  
  
 <span data-ttu-id="4d653-201">Führen Sie das Modell, die einzelnen Operation-Klassen wie dem oben beschriebenen <xref:System.EventArgs> Struktur funktioniert für alle inkrementellen Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="4d653-201">Follow the model described above for single-operation classes, as the same <xref:System.EventArgs> structure will work for all incremental results.</span></span> <span data-ttu-id="4d653-202">Definieren Sie ein `ProgressChanged`-Ereignis anstelle eines *MethodName*`ProgressChanged`-Ereignisses, weil es für mehrere asynchrone Methoden gilt.</span><span class="sxs-lookup"><span data-stu-id="4d653-202">Define a `ProgressChanged` event instead of a *MethodName*`ProgressChanged` event, since it applies to multiple asynchronous methods.</span></span>  
  
### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a><span data-ttu-id="4d653-203">Klasse mit mehreren Vorgängen und heterogenen inkrementellen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="4d653-203">Multiple-operation Class with Heterogeneous Incremental Results</span></span>  
 <span data-ttu-id="4d653-204">Wenn die Klasse mehrere asynchrone Methoden unterstützt, wobei jede Methode Daten eines anderen Typs zurückgibt, sollten Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="4d653-204">If your class supports multiple asynchronous methods, each returning a different type of data, you should:</span></span>  
  
-   <span data-ttu-id="4d653-205">Trennen Sie die Mitteilungen über inkrementelle Ergebnisse von den Statusmitteilungen.</span><span class="sxs-lookup"><span data-stu-id="4d653-205">Separate your incremental result reporting from your progress reporting.</span></span>  
  
-   <span data-ttu-id="4d653-206">Definieren Sie eine Separate *MethodName* `ProgressChanged` Ereignis mit der entsprechenden <xref:System.EventArgs> für jede asynchrone Methode, inkrementelle Ergebnisdaten dieser Methode zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="4d653-206">Define a separate *MethodName*`ProgressChanged` event with appropriate <xref:System.EventArgs> for each asynchronous method to handle that method's incremental result data.</span></span>  
  
 <span data-ttu-id="4d653-207">Rufen Sie diesen Ereignishandler für den entsprechenden Thread auf, wie dies unter [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="4d653-207">Invoke that event handler on the appropriate thread as described in [Best Practices for Implementing the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="handling-out-and-ref-parameters-in-methods"></a><span data-ttu-id="4d653-208">Verarbeiten von „out“- und „ref“-Parametern in Methoden</span><span class="sxs-lookup"><span data-stu-id="4d653-208">Handling Out and Ref Parameters in Methods</span></span>  
 <span data-ttu-id="4d653-209">Grundsätzlich wird davon abgeraten, `out` und `ref` in .NET Framework zu verwenden. Sind diese aber vorhanden, sollten die folgenden Regeln beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="4d653-209">Although the use of `out` and `ref` is, in general, discouraged in the .NET Framework, here are the rules to follow when they are present:</span></span>  
  
 <span data-ttu-id="4d653-210">Angenommen, es gibt die synchrone Methode *MethodName*:</span><span class="sxs-lookup"><span data-stu-id="4d653-210">Given a synchronous method *MethodName*:</span></span>  
  
-   <span data-ttu-id="4d653-211">`out`-Parameter für *MethodName* dürfen keine Bestandteile von *MethodName*`Async` sein.</span><span class="sxs-lookup"><span data-stu-id="4d653-211">`out` parameters to *MethodName* should not be part of *MethodName*`Async`.</span></span> <span data-ttu-id="4d653-212">Stattdessen müssen sie Bestandteile von *MethodName*`CompletedEventArgs` mit denselben Namen wie ihre Parametergegenstücke in *MethodName* sein (es sei denn, es gibt geeignetere Namen).</span><span class="sxs-lookup"><span data-stu-id="4d653-212">Instead, they should be part of *MethodName*`CompletedEventArgs` with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>  
  
-   <span data-ttu-id="4d653-213">`ref`-Parameter für *MethodName* müssen als Bestandteile von *MethodName*`Async` und als Bestandteile von *MethodName*`CompletedEventArgs` mit denselben Namen wie ihre Parametergegenstücke in *MethodName* vorhanden sein (es sei denn, es gibt geeignetere Namen).</span><span class="sxs-lookup"><span data-stu-id="4d653-213">`ref` parameters to *MethodName* should appear as part of *MethodName*`Async`, and as part of *MethodName*`CompletedEventArgs` with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>  
  
 <span data-ttu-id="4d653-214">Angenommen, dies liegt vor:</span><span class="sxs-lookup"><span data-stu-id="4d653-214">For example, given:</span></span>  
  
```vb  
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer  
```  
  
```csharp  
public int MethodName(string arg1, ref string arg2, out string arg3);  
```  
  
 <span data-ttu-id="4d653-215">Die asynchrone Methode und die zugehörige <xref:System.ComponentModel.AsyncCompletedEventArgs> Klasse würde wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="4d653-215">Your asynchronous method and its <xref:System.ComponentModel.AsyncCompletedEventArgs> class would look like this:</span></span>  
  
```vb  
Public Sub MethodNameAsync(ByVal arg1 As String, ByVal arg2 As String)  
  
Public Class MethodNameCompletedEventArgs  
    Inherits System.ComponentModel.AsyncCompletedEventArgs  
    Public ReadOnly Property Result() As Integer   
    End Property  
    Public ReadOnly Property Arg2() As String   
    End Property  
    Public ReadOnly Property Arg3() As String   
    End Property  
End Class  
```  
  
```csharp  
public void MethodNameAsync(string arg1, string arg2);  
  
public class MethodNameCompletedEventArgs : System.ComponentModel.AsyncCompletedEventArgs  
{  
    public int Result { get; };  
    public string Arg2 { get; };  
    public string Arg3 { get; };  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d653-216">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d653-216">See Also</span></span>  
 <xref:System.ComponentModel.ProgressChangedEventArgs>  
 <xref:System.ComponentModel.AsyncCompletedEventArgs>  
 [<span data-ttu-id="4d653-217">Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt</span><span class="sxs-lookup"><span data-stu-id="4d653-217">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="4d653-218">Gewusst wie: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="4d653-218">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [<span data-ttu-id="4d653-219">Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="4d653-219">How to: Implement a Form That Uses a Background Operation</span></span>](../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [<span data-ttu-id="4d653-220">Deciding When to Implement the Event-based Asynchronous Pattern (Gründe für das Implementieren des ereignisbasierten asynchronen Musters)</span><span class="sxs-lookup"><span data-stu-id="4d653-220">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="4d653-221">Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster</span><span class="sxs-lookup"><span data-stu-id="4d653-221">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="4d653-222">Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="4d653-222">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
