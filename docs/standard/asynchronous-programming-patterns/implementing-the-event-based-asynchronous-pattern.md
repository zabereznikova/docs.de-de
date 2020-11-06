---
title: Implementieren des ereignisbasierten asynchronen Entwurfsmusters
description: Erfahren Sie, wie Sie das ereignisbasierte asynchrone Muster in .NET implementieren. Das ereignisbasierte asynchrone Muster ist ein Standardverfahren zum Packen einer Klasse mit asynchronen Features.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET], asynchronous features
- components [.NET], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 43402d19-8d30-426d-8785-1a4478233bfa
ms.openlocfilehash: ca4b1b3ff1fb7180250de7436db9a4d642e8118c
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888788"
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="50522-104">Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="50522-104">Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="50522-105">Wenn Sie eine Klasse mit einigen Vorgängen erstellen, die möglicherweise nennenswerte Verzögerungen verursachen, sollten Sie in Betracht ziehen, diese Klasse mit einer asynchronen Funktionalität auszustatten, indem Sie das [ereignisbasierte asynchrone Muster](event-based-asynchronous-pattern-overview.md) implementieren.</span><span class="sxs-lookup"><span data-stu-id="50522-105">If you are writing a class with some operations that may incur noticeable delays, consider giving it asynchronous functionality by implementing the [Event-based Asynchronous Pattern](event-based-asynchronous-pattern-overview.md).</span></span>

<span data-ttu-id="50522-106">Das ereignisbasierte asynchrone Muster bietet eine standardisierte Möglichkeit zum Verpacken einer Klasse, die asynchrone Features hat.</span><span class="sxs-lookup"><span data-stu-id="50522-106">The Event-based Asynchronous Pattern provides a standardized way to package a class that has asynchronous features.</span></span> <span data-ttu-id="50522-107">Ist eine Klasse mit Hilfsklassen wie <xref:System.ComponentModel.AsyncOperationManager> implementiert, funktioniert sie unter jedem beliebigen Anwendungsmodell korrekt, einschließlich ASP.NET, Konsolenanwendungen und Windows Forms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="50522-107">If implemented with helper classes like <xref:System.ComponentModel.AsyncOperationManager>, your class will work correctly under any application model, including ASP.NET, Console applications, and Windows Forms applications.</span></span>

<span data-ttu-id="50522-108">Ein Beispiel, in dem das ereignisbasiertes asynchrone Muster implementiert wird, finden Sie unter [Vorgehensweise: Übersicht über ereignisbasierte asynchrone Muster](component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="50522-108">For an example that implements the Event-based Asynchronous Pattern, see [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="50522-109">Für einfache asynchrone Vorgänge ist möglicherweise die Komponente <xref:System.ComponentModel.BackgroundWorker> gut geeignet.</span><span class="sxs-lookup"><span data-stu-id="50522-109">For simple asynchronous operations, you may find the <xref:System.ComponentModel.BackgroundWorker> component suitable.</span></span> <span data-ttu-id="50522-110">Weitere Informationen zum Verwenden von <xref:System.ComponentModel.BackgroundWorker> finden Sie unter [Vorgehensweise: Ausführen eines Vorgangs im Hintergrund](/dotnet/desktop/winforms/controls/how-to-run-an-operation-in-the-background).</span><span class="sxs-lookup"><span data-stu-id="50522-110">For more information about <xref:System.ComponentModel.BackgroundWorker>, see [How to: Run an Operation in the Background](/dotnet/desktop/winforms/controls/how-to-run-an-operation-in-the-background).</span></span>

<span data-ttu-id="50522-111">In der folgenden Liste sind die Features des ereignisbasierten asynchronen Musters aufgeführt, die in diesem Thema beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="50522-111">The following list describes the features of the Event-based Asynchronous Pattern discussed in this topic.</span></span>

- <span data-ttu-id="50522-112">Gelegenheiten für Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="50522-112">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

- <span data-ttu-id="50522-113">Benennen von asynchronen Methoden</span><span class="sxs-lookup"><span data-stu-id="50522-113">Naming Asynchronous Methods</span></span>

- <span data-ttu-id="50522-114">Optionales Unterstützen von Abbruch</span><span class="sxs-lookup"><span data-stu-id="50522-114">Optionally Support Cancellation</span></span>

- <span data-ttu-id="50522-115">Optionales Unterstützen der „IsBusy“-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="50522-115">Optionally Support the IsBusy Property</span></span>

- <span data-ttu-id="50522-116">Optionales Unterstützen von Statusberichterstellung</span><span class="sxs-lookup"><span data-stu-id="50522-116">Optionally Provide Support for Progress Reporting</span></span>

- <span data-ttu-id="50522-117">Optionales Unterstützen der Rückgabe von inkrementellen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="50522-117">Optionally Provide Support for Returning Incremental Results</span></span>

- <span data-ttu-id="50522-118">Verarbeiten von „out“- und „ref“-Parametern in Methoden</span><span class="sxs-lookup"><span data-stu-id="50522-118">Handling Out and Ref Parameters in Methods</span></span>

## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="50522-119">Gelegenheiten für Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="50522-119">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="50522-120">Implementieren des ereignisbasierten asynchronen Entwurfsmusters bietet sich an, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="50522-120">Consider implementing the Event-based Asynchronous Pattern when:</span></span>

- <span data-ttu-id="50522-121">Clients einer Klasse benötigen keine <xref:System.Threading.WaitHandle>- und <xref:System.IAsyncResult>-Objekte, die für asynchrone Vorgänge verfügbar sind, d.h. Abfragen und <xref:System.Threading.WaitHandle.WaitAll%2A> oder <xref:System.Threading.WaitHandle.WaitAny%2A> müssen vom Client erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="50522-121">Clients of your class do not need <xref:System.Threading.WaitHandle> and <xref:System.IAsyncResult> objects available for asynchronous operations, meaning that polling and <xref:System.Threading.WaitHandle.WaitAll%2A> or <xref:System.Threading.WaitHandle.WaitAny%2A> will need to be built up by the client.</span></span>

- <span data-ttu-id="50522-122">Asynchrone Vorgänge sollen vom Client mit dem vertrauten Ereignis/Delegat-Modell verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="50522-122">You want asynchronous operations to be managed by the client with the familiar event/delegate model.</span></span>

<span data-ttu-id="50522-123">Jeder Vorgang ist ein Kandidat für eine asynchrone Implementierung, aber ein Vorgang, für den Sie lange Wartezeiten erwarten, sollte auf alle Fälle berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="50522-123">Any operation is a candidate for an asynchronous implementation, but those you expect to incur long latencies should be considered.</span></span> <span data-ttu-id="50522-124">Besonders geeignet sind Vorgänge, in denen Clients eine Methode aufrufen und bei Abschluss benachrichtigt werden, ohne dass weiteres Eingreifen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="50522-124">Especially appropriate are operations in which clients call a method and are notified on completion, with no further intervention required.</span></span> <span data-ttu-id="50522-125">Geeignet sind außerdem Vorgänge, die durchgängig ausgeführt werden und dabei Clients regelmäßig über Fortschritte, inkrementelle Ergebnisse oder Zustandsänderungen benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="50522-125">Also appropriate are operations which run continuously, periodically notifying clients of progress, incremental results, or state changes.</span></span>

<span data-ttu-id="50522-126">Weitere Informationen dazu, wie entschieden werden soll, ob das ereignisbasierte asynchrone Muster unterstützt werden sollte, finden Sie unter [Gründe für das Implementieren des ereignisbasierten asynchronen Musters](deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="50522-126">For more information on deciding when to support the Event-based Asynchronous Pattern, see [Deciding When to Implement the Event-based Asynchronous Pattern](deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="naming-asynchronous-methods"></a><span data-ttu-id="50522-127">Benennen von asynchronen Methoden</span><span class="sxs-lookup"><span data-stu-id="50522-127">Naming Asynchronous Methods</span></span>

<span data-ttu-id="50522-128">Definieren Sie für jede synchrone Methode *MethodName* , für die Sie ein asynchrones Gegenstück bereitstellen möchten, Folgendes:</span><span class="sxs-lookup"><span data-stu-id="50522-128">For each synchronous method *MethodName* for which you want to provide an asynchronous counterpart:</span></span>

<span data-ttu-id="50522-129">Definieren Sie eine _MethodName_**Async** -Methode, für die Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="50522-129">Define a _MethodName_**Async** method that:</span></span>

- <span data-ttu-id="50522-130">Gibt `void`zurück.</span><span class="sxs-lookup"><span data-stu-id="50522-130">Returns `void`.</span></span>

- <span data-ttu-id="50522-131">Dieselben Parameter hat wie die *MethodName* -Methode.</span><span class="sxs-lookup"><span data-stu-id="50522-131">Takes the same parameters as the *MethodName* method.</span></span>

- <span data-ttu-id="50522-132">Mehrere Aufrufe akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="50522-132">Accepts multiple invocations.</span></span>

<span data-ttu-id="50522-133">Definieren Sie optional eine _MethodName_**Async** -Überladung, die mit _MethodName_**Async** identisch ist, aber einen zusätzlichen Objektparameter namens `userState` hat.</span><span class="sxs-lookup"><span data-stu-id="50522-133">Optionally define a _MethodName_**Async** overload, identical to _MethodName_**Async** , but with an additional object-valued parameter called `userState`.</span></span> <span data-ttu-id="50522-134">Dies sollten Sie tun, wenn Sie mehrere gleichzeitige Aufrufe der Methode verwalten möchten. In diesem Fall wird der `userState`-Wert an alle Ereignishandler zurückgegeben, um die Aufrufe der Methode zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="50522-134">Do this if you're prepared to manage multiple concurrent invocations of your method, in which case the `userState` value will be delivered back to all event handlers to distinguish invocations of the method.</span></span> <span data-ttu-id="50522-135">Diese Vorgehensweise bietet sich auch an, wenn Sie einfach einen Platz haben möchten, in dem der Benutzerstatus für spätere Abrufe gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="50522-135">You may also choose to do this simply as a place to store user state for later retrieval.</span></span>

<span data-ttu-id="50522-136">Definieren Sie für jede einzelne _MethodName_**Async** -Methodensignatur:</span><span class="sxs-lookup"><span data-stu-id="50522-136">For each separate _MethodName_**Async** method signature:</span></span>

1. <span data-ttu-id="50522-137">Das folgende Ereignis in derselben Klasse wie die Methode:</span><span class="sxs-lookup"><span data-stu-id="50522-137">Define the following event in the same class as the method:</span></span>

    ```vb
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler
    ```

    ```csharp
    public event MethodNameCompletedEventHandler MethodNameCompleted;
    ```

2. <span data-ttu-id="50522-138">Den folgenden Delegaten und <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="50522-138">Define the following delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span></span> <span data-ttu-id="50522-139">Diese sind wahrscheinlich außerhalb der Klasse selbst, aber im selben Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="50522-139">These will likely be defined outside of the class itself, but in the same namespace.</span></span>

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

    - <span data-ttu-id="50522-140">Stellen Sie sicher, dass die _MethodName_**CompletedEventArgs** -Klasse ihre Elemente als schreibgeschützte Eigenschaften verfügbar macht, und nicht als Felder, weil Felder Datenbindungen verhindern.</span><span class="sxs-lookup"><span data-stu-id="50522-140">Ensure that the _MethodName_**CompletedEventArgs** class exposes its members as read-only properties, and not fields, as fields prevent data binding.</span></span>

    - <span data-ttu-id="50522-141">Definieren Sie keine <xref:System.ComponentModel.AsyncCompletedEventArgs>-abgeleitete Klassen für Methoden, die keine Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="50522-141">Do not define any <xref:System.ComponentModel.AsyncCompletedEventArgs>-derived classes for methods that do not produce results.</span></span> <span data-ttu-id="50522-142">Verwenden Sie einfach eine Instanz von <xref:System.ComponentModel.AsyncCompletedEventArgs> selbst.</span><span class="sxs-lookup"><span data-stu-id="50522-142">Simply use an instance of <xref:System.ComponentModel.AsyncCompletedEventArgs> itself.</span></span>

      > [!NOTE]
      > <span data-ttu-id="50522-143">Es ist durchaus akzeptabel, wenn machbar und angemessen, Delegaten und <xref:System.ComponentModel.AsyncCompletedEventArgs>-Typen wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="50522-143">It is perfectly acceptable, when feasible and appropriate, to reuse delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> types.</span></span> <span data-ttu-id="50522-144">In diesem Fall ist die Benennung nicht so konsistent wie mit dem Methodennamen, da ein bestimmter Delegat und <xref:System.ComponentModel.AsyncCompletedEventArgs> nicht an eine einzelne Methode gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="50522-144">In this case, the naming will not be as consistent with the method name, since a given delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> won't be tied to a single method.</span></span>

## <a name="optionally-support-cancellation"></a><span data-ttu-id="50522-145">Optionales Unterstützen von Abbruch</span><span class="sxs-lookup"><span data-stu-id="50522-145">Optionally Support Cancellation</span></span>

<span data-ttu-id="50522-146">Wenn Ihre Klasse das Abbrechen von asynchronen Vorgängen unterstützt, sollte Abbruch so für den Client verfügbar gemacht werden, wie dies weiter unten beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="50522-146">If your class will support canceling asynchronous operations, cancellation should be exposed to the client as described below.</span></span> <span data-ttu-id="50522-147">Es gibt zwei Entscheidungspunkte, die erreicht sein müssen, bevor Abbruchunterstützung definiert wird:</span><span class="sxs-lookup"><span data-stu-id="50522-147">Note that there are two decision points that need to be reached before defining your cancellation support:</span></span>

- <span data-ttu-id="50522-148">Hat die Klasse, einschließlich zukünftiger zu erwartender Erweiterungen, nur einen asynchronen Vorgang, der Abbruch unterstützt?</span><span class="sxs-lookup"><span data-stu-id="50522-148">Does your class, including future anticipated additions to it, have only one asynchronous operation that supports cancellation?</span></span>

- <span data-ttu-id="50522-149">Können die asynchronen Vorgänge, die Abbruch unterstützen, mehrere ausstehende Vorgänge unterstützen?</span><span class="sxs-lookup"><span data-stu-id="50522-149">Can the asynchronous operations that support cancellation support multiple pending operations?</span></span> <span data-ttu-id="50522-150">Das heißt, hat die _MethodName_**Async** -Methode den `userState`-Parameter akzeptiert und lässt sie mehrere Aufrufe zu, bevor sie für jeden auf dessen Beendigung wartet?</span><span class="sxs-lookup"><span data-stu-id="50522-150">That is, does the _MethodName_**Async** method take a `userState` parameter, and does it allow multiple invocations before waiting for any to finish?</span></span>

<span data-ttu-id="50522-151">Entscheiden Sie anhand der Antworten auf die beiden Fragen in der folgenden Tabelle, welche Signatur für die Abbruchmethode zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="50522-151">Use the answers to these two questions in the table below to determine what the signature for your cancellation method should be.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="50522-152">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50522-152">Visual Basic</span></span>

||<span data-ttu-id="50522-153">Mehrere gleichzeitige Vorgänge unterstützt</span><span class="sxs-lookup"><span data-stu-id="50522-153">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="50522-154">Nur immer jeweils ein Vorgang</span><span class="sxs-lookup"><span data-stu-id="50522-154">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="50522-155">Ein asynchroner Vorgang in der gesamten Klasse</span><span class="sxs-lookup"><span data-stu-id="50522-155">One Async Operation in entire class</span></span>|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|
|<span data-ttu-id="50522-156">Mehrere asynchrone Vorgänge in der Klasse</span><span class="sxs-lookup"><span data-stu-id="50522-156">Multiple Async Operations in class</span></span>|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|

### <a name="c"></a><span data-ttu-id="50522-157">C\#</span><span class="sxs-lookup"><span data-stu-id="50522-157">C\#</span></span>

||<span data-ttu-id="50522-158">Mehrere gleichzeitige Vorgänge unterstützt</span><span class="sxs-lookup"><span data-stu-id="50522-158">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="50522-159">Nur immer jeweils ein Vorgang</span><span class="sxs-lookup"><span data-stu-id="50522-159">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="50522-160">Ein asynchroner Vorgang in der gesamten Klasse</span><span class="sxs-lookup"><span data-stu-id="50522-160">One Async Operation in entire class</span></span>|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|
|<span data-ttu-id="50522-161">Mehrere asynchrone Vorgänge in der Klasse</span><span class="sxs-lookup"><span data-stu-id="50522-161">Multiple Async Operations in class</span></span>|`void CancelAsync(object userState);`|`void CancelAsync();`|

<span data-ttu-id="50522-162">Wenn Sie die `CancelAsync(object userState)`-Methode definieren, müssen Clients bei der Auswahl ihrer Statuswerte vorsichtig sein, damit sie in der Lage sind, zwischen allen für das Objekt aufgerufenen asynchronen Methoden, nicht nur zwischen allen Aufrufen einer einzigen asynchronen Methode zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="50522-162">If you define the `CancelAsync(object userState)` method, clients must be careful when choosing their state values to make them capable of distinguishing among all asynchronous methods invoked on the object, and not just between all invocations of a single asynchronous method.</span></span>

<span data-ttu-id="50522-163">Es wurde entschieden, die Version mit einzelnem asynchronen Vorgang als _MethodName_**AsyncCancel** zu benennen, um die Methode in einer Entwurfsumgebung wie Visual Studios IntelliSense einfacher erkennen zu können.</span><span class="sxs-lookup"><span data-stu-id="50522-163">The decision to name the single-async-operation version _MethodName_**AsyncCancel** is based on being able to more easily discover the method in a design environment like Visual Studio's IntelliSense.</span></span> <span data-ttu-id="50522-164">Dadurch werden die zusammengehörenden Member gruppiert und lassen sich von anderen Membern unterscheiden, die nichts mit der asynchronen Funktionalität zu tun haben.</span><span class="sxs-lookup"><span data-stu-id="50522-164">This groups the related members and distinguishes them from other members that have nothing to do with asynchronous functionality.</span></span> <span data-ttu-id="50522-165">Wenn Sie davon ausgehen, dass in späteren Versionen weitere asynchrone Vorgänge hinzugefügt werden, sollten Sie `CancelAsync` definieren.</span><span class="sxs-lookup"><span data-stu-id="50522-165">If you expect that there may be additional asynchronous operations added in subsequent versions, it is better to define `CancelAsync`.</span></span>

<span data-ttu-id="50522-166">Definieren Sie nicht mehrere Methoden aus der obigen Tabelle in derselben Klasse.</span><span class="sxs-lookup"><span data-stu-id="50522-166">Do not define multiple methods from the table above in the same class.</span></span> <span data-ttu-id="50522-167">Dies ist nicht sinnvoll oder führt dazu, dass in der Klassenschnittstelle unnötig viele Methoden bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="50522-167">That will not make sense, or it will clutter the class interface with a proliferation of methods.</span></span>

<span data-ttu-id="50522-168">Diese Methoden führen üblicherweise sofort eine Rückkehr aus, und der Vorgang wird möglicherweise tatsächlich abgebrochen (oder nicht).</span><span class="sxs-lookup"><span data-stu-id="50522-168">These methods typically will return immediately, and the operation may or may not actually cancel.</span></span> <span data-ttu-id="50522-169">Im Ereignishandler für das _MethodName_**Completed** -Ereignis enthält das _MethodName_**CompletedEventArgs** -Objekt ein `Cancelled`-Feld, anhand dessen Clients ermitteln können, ob der Abbruch aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="50522-169">In the event handler for the _MethodName_**Completed** event, the _MethodName_**CompletedEventArgs** object contains a `Cancelled` field, which clients can use to determine whether the cancellation occurred.</span></span>

<span data-ttu-id="50522-170">Halten Sie sich an die Abbruchsemantik, die unter [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](best-practices-for-implementing-the-event-based-asynchronous-pattern.md) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="50522-170">Abide by the cancellation semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-support-the-isbusy-property"></a><span data-ttu-id="50522-171">Optionales Unterstützen der „IsBusy“-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="50522-171">Optionally Support the IsBusy Property</span></span>

<span data-ttu-id="50522-172">Unterstützt die Klasse nicht mehrere gleichzeitige Aufrufe, sollten Sie eine `IsBusy`-Eigenschaft verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="50522-172">If your class does not support multiple concurrent invocations, consider exposing an `IsBusy` property.</span></span> <span data-ttu-id="50522-173">Dies ermöglicht Entwicklern, zu bestimmen, ob eine _MethodName_**Async** -Methode ausgeführt wird, ohne eine Ausnahme von der _MethodName_**Async** -Methode abzufangen.</span><span class="sxs-lookup"><span data-stu-id="50522-173">This allows developers to determine whether a _MethodName_**Async** method is running without catching an exception from the _MethodName_**Async** method.</span></span>

<span data-ttu-id="50522-174">Halten Sie sich an die `IsBusy`-Semantik, die unter [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](best-practices-for-implementing-the-event-based-asynchronous-pattern.md) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="50522-174">Abide by the `IsBusy` semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-progress-reporting"></a><span data-ttu-id="50522-175">Optionales Unterstützen von Statusberichterstellung</span><span class="sxs-lookup"><span data-stu-id="50522-175">Optionally Provide Support for Progress Reporting</span></span>

<span data-ttu-id="50522-176">Es ist häufig wünschenswert, dass ein asynchroner Vorgang während seiner Ausführung den Status mitteilt.</span><span class="sxs-lookup"><span data-stu-id="50522-176">It is frequently desirable for an asynchronous operation to report progress during its operation.</span></span> <span data-ttu-id="50522-177">Das ereignisbasierte asynchrone Muster stellt eine Richtlinie dafür bereit.</span><span class="sxs-lookup"><span data-stu-id="50522-177">The Event-based Asynchronous Pattern provides a guideline for doing so.</span></span>

- <span data-ttu-id="50522-178">Definieren Sie optional ein Ereignis, das vom asynchronen Vorgang ausgelöst und im entsprechenden Thread aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="50522-178">Optionally define an event to be raised by the asynchronous operation and invoked on the appropriate thread.</span></span> <span data-ttu-id="50522-179">Das <xref:System.ComponentModel.ProgressChangedEventArgs>-Objekt enthält eine Statusanzeige mit Ganzzahlwert, der zwischen 0 und 100 liegt.</span><span class="sxs-lookup"><span data-stu-id="50522-179">The <xref:System.ComponentModel.ProgressChangedEventArgs> object carries an integer-valued progress indicator that is expected to be between 0 and 100.</span></span>

- <span data-ttu-id="50522-180">Benennen Sie dieses Ereignis wie folgt:</span><span class="sxs-lookup"><span data-stu-id="50522-180">Name this event as follows:</span></span>

  - <span data-ttu-id="50522-181">`ProgressChanged`, wenn die Klasse mehrere asynchrone Vorgänge hat (oder vermutlich so erweitert wird, dass sie in zukünftigen Versionen mehrere asynchrone Vorgänge haben wird)</span><span class="sxs-lookup"><span data-stu-id="50522-181">`ProgressChanged` if the class has multiple asynchronous operations (or is expected to grow to include multiple asynchronous operations in future versions);</span></span>

  - <span data-ttu-id="50522-182">_MethodName_**ProgressChanged** , wenn die Klasse einen einzelnen asynchronen Vorgang hat.</span><span class="sxs-lookup"><span data-stu-id="50522-182">_MethodName_**ProgressChanged** if the class has a single asynchronous operation.</span></span>

  <span data-ttu-id="50522-183">Diese Benennungskonvention entspricht derjenigen für die Abbruchmethode, wie im Abschnitt „Optionales Unterstützen von Abbruch“ beschrieben.</span><span class="sxs-lookup"><span data-stu-id="50522-183">This naming choice parallels that made for the cancellation method, as described in the Optionally Support Cancellation section.</span></span>

<span data-ttu-id="50522-184">Dieses Ereignis sollte die <xref:System.ComponentModel.ProgressChangedEventHandler>-Signatur des Delegaten und die <xref:System.ComponentModel.ProgressChangedEventArgs>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="50522-184">This event should use the <xref:System.ComponentModel.ProgressChangedEventHandler> delegate signature and the <xref:System.ComponentModel.ProgressChangedEventArgs> class.</span></span> <span data-ttu-id="50522-185">Für den Fall, dass eine bereichsspezifischere Statusanzeige bereitgestellt werden kann (beispielsweise gelesene Bytes und die Gesamtanzahl der Bytes für einen Downloadvorgang), sollten Sie eine abgeleitete Klasse von <xref:System.ComponentModel.ProgressChangedEventArgs> definieren.</span><span class="sxs-lookup"><span data-stu-id="50522-185">Alternatively, if a more domain-specific progress indicator can be provided (for instance, bytes read and total bytes for a download operation), then you should define a derived class of <xref:System.ComponentModel.ProgressChangedEventArgs>.</span></span>

<span data-ttu-id="50522-186">Beachten Sie, dass es nur ein `ProgressChanged`- oder _MethodName_**ProgressChanged** -Ereignis für die Klasse gibt, unabhängig davon, wie viele asynchrone Methoden sie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="50522-186">Note that there is only one `ProgressChanged` or _MethodName_**ProgressChanged** event for the class, regardless of the number of asynchronous methods it supports.</span></span> <span data-ttu-id="50522-187">Für Clients wird vorausgesetzt, dass sie das `userState`-Objekt verwenden, das an die _MethodName_**Async** -Methoden übergeben wird, um zwischen Statusupdates bei mehreren gleichzeitigen Vorgängen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="50522-187">Clients are expected to use the `userState` object that is passed to the _MethodName_**Async** methods to distinguish among progress updates on multiple concurrent operations.</span></span>

<span data-ttu-id="50522-188">Es kann Situationen geben, in denen mehrere Vorgänge einen Status unterstützen und jeder Vorgang einen anderen Indikator für den Status zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="50522-188">There may be situations in which multiple operations support progress and each returns a different indicator for progress.</span></span> <span data-ttu-id="50522-189">In diesem Fall ist ein einzelnes `ProgressChanged`-Ereignis nicht geeignet, und Sie sollten Unterstützung für mehrere `ProgressChanged`-Ereignisse erwägen.</span><span class="sxs-lookup"><span data-stu-id="50522-189">In this case, a single `ProgressChanged` event is not appropriate, and you may consider supporting multiple `ProgressChanged` events.</span></span> <span data-ttu-id="50522-190">Verwenden Sie für diesen Fall das Benennungsmuster _MethodName_**ProgressChanged** für jede _MethodName_**Async** -Methode.</span><span class="sxs-lookup"><span data-stu-id="50522-190">In this case use a naming pattern of _MethodName_**ProgressChanged** for each _MethodName_**Async** method.</span></span>

<span data-ttu-id="50522-191">Halten Sie sich an die Statusberichte-Semantik, die unter [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](best-practices-for-implementing-the-event-based-asynchronous-pattern.md) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="50522-191">Abide by the progress-reporting semantics described [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-returning-incremental-results"></a><span data-ttu-id="50522-192">Optionales Unterstützen der Rückgabe von inkrementellen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="50522-192">Optionally Provide Support for Returning Incremental Results</span></span>

<span data-ttu-id="50522-193">Möglicherweise gibt ein asynchroner Vorgang vor seiner Beendigung inkrementelle Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="50522-193">Sometimes an asynchronous operation can return incremental results prior to completion.</span></span> <span data-ttu-id="50522-194">Zur Unterstützung dieses Szenarios gibt es eine Reihe von Optionen, die verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="50522-194">There are a number of options that can be used to support this scenario.</span></span> <span data-ttu-id="50522-195">Es folgen einige Beispiele.</span><span class="sxs-lookup"><span data-stu-id="50522-195">Some examples follow.</span></span>

### <a name="single-operation-class"></a><span data-ttu-id="50522-196">Klasse mit einem einzigen Vorgang</span><span class="sxs-lookup"><span data-stu-id="50522-196">Single-operation Class</span></span>

<span data-ttu-id="50522-197">Unterstützt die Klasse nur einen einzigen asynchronen Vorgang, und kann dieser Vorgang inkrementelle Ergebnisse zurückgeben, dann gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="50522-197">If your class only supports a single asynchronous operation, and that operation is able to return incremental results, then:</span></span>

- <span data-ttu-id="50522-198">Erweitern Sie den <xref:System.ComponentModel.ProgressChangedEventArgs>-Typ, damit er die Daten eines inkrementellen Ergebnisses aufnehmen kann, und definieren Sie ein _MethodName_**ProgressChanged** -Ereignis mit diesen erweiterten Daten.</span><span class="sxs-lookup"><span data-stu-id="50522-198">Extend the <xref:System.ComponentModel.ProgressChangedEventArgs> type to carry the incremental result data, and define a _MethodName_**ProgressChanged** event with this extended data.</span></span>

- <span data-ttu-id="50522-199">Lösen Sie dieses _MethodName_**ProgressChanged** -Ereignis aus, sobald ein zu berichtendes inkrementelles Ergebnis vorliegt.</span><span class="sxs-lookup"><span data-stu-id="50522-199">Raise this _MethodName_**ProgressChanged** event when there is an incremental result to report.</span></span>

<span data-ttu-id="50522-200">Diese Lösung ist speziell für eine Klasse mit einzelnem asynchronen Vorgang anwendbar, weil es kein Problem damit gibt, dass dasselbe auftretende Ereignis inkrementelle Ergebnisse für „alle Vorgänge“ zurückgibt, denn das _MethodName_**ProgressChanged** -Ereignis erledigt dies.</span><span class="sxs-lookup"><span data-stu-id="50522-200">This solution applies specifically to a single-async-operation class because there is no problem with the same event occurring to return incremental results on "all operations", as the _MethodName_**ProgressChanged** event does.</span></span>

### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a><span data-ttu-id="50522-201">Klasse mit mehreren Vorgängen und homogenen inkrementellen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="50522-201">Multiple-operation Class with Homogeneous Incremental Results</span></span>

<span data-ttu-id="50522-202">In diesem Fall unterstützt die Klasse mehrere asynchrone Methoden, von denen jede inkrementelle Ergebnisse zurückgeben kann, wobei diese inkrementellen Ergebnisse alle denselben Datentyp haben.</span><span class="sxs-lookup"><span data-stu-id="50522-202">In this case, your class supports multiple asynchronous methods, each capable of returning incremental results, and these incremental results all have the same type of data.</span></span>

<span data-ttu-id="50522-203">Gehen Sie entsprechend dem oben beschriebenen Modell für Klassen mit einzelnem Vorgang vor, da die gleiche <xref:System.EventArgs>-Struktur für alle inkrementellen Ergebnisse funktioniert.</span><span class="sxs-lookup"><span data-stu-id="50522-203">Follow the model described above for single-operation classes, as the same <xref:System.EventArgs> structure will work for all incremental results.</span></span> <span data-ttu-id="50522-204">Definieren Sie ein `ProgressChanged`-Ereignis anstelle eines _MethodName_**ProgressChanged** -Ereignisses, weil es für mehrere asynchrone Methoden gilt.</span><span class="sxs-lookup"><span data-stu-id="50522-204">Define a `ProgressChanged` event instead of a _MethodName_**ProgressChanged** event, since it applies to multiple asynchronous methods.</span></span>

### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a><span data-ttu-id="50522-205">Klasse mit mehreren Vorgängen und heterogenen inkrementellen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="50522-205">Multiple-operation Class with Heterogeneous Incremental Results</span></span>

<span data-ttu-id="50522-206">Wenn die Klasse mehrere asynchrone Methoden unterstützt, wobei jede Methode Daten eines anderen Typs zurückgibt, sollten Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="50522-206">If your class supports multiple asynchronous methods, each returning a different type of data, you should:</span></span>

- <span data-ttu-id="50522-207">Trennen Sie die Mitteilungen über inkrementelle Ergebnisse von den Statusmitteilungen.</span><span class="sxs-lookup"><span data-stu-id="50522-207">Separate your incremental result reporting from your progress reporting.</span></span>

- <span data-ttu-id="50522-208">Definieren Sie für jede asynchrone Methode ein eigenes _MethodName_**ProgressChanged** -Ereignis mit entsprechenden <xref:System.EventArgs>, um die Daten eines inkrementellen Ergebnisses dieser Methode zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="50522-208">Define a separate _MethodName_**ProgressChanged** event with appropriate <xref:System.EventArgs> for each asynchronous method to handle that method's incremental result data.</span></span>

<span data-ttu-id="50522-209">Rufen Sie diesen Ereignishandler für den entsprechenden Thread auf, wie dies unter [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](best-practices-for-implementing-the-event-based-asynchronous-pattern.md) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="50522-209">Invoke that event handler on the appropriate thread as described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="handling-out-and-ref-parameters-in-methods"></a><span data-ttu-id="50522-210">Verarbeiten von „out“- und „ref“-Parametern in Methoden</span><span class="sxs-lookup"><span data-stu-id="50522-210">Handling Out and Ref Parameters in Methods</span></span>

<span data-ttu-id="50522-211">Grundsätzlich wird in .NET von `out` und `ref` abgeraten. Sind diese aber vorhanden, sollten die folgenden Regeln beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="50522-211">Although the use of `out` and `ref` is, in general, discouraged in .NET, here are the rules to follow when they are present:</span></span>

<span data-ttu-id="50522-212">Angenommen, es gibt die synchrone Methode *MethodName* :</span><span class="sxs-lookup"><span data-stu-id="50522-212">Given a synchronous method *MethodName* :</span></span>

- <span data-ttu-id="50522-213">`out`-Parameter für *MethodName* dürfen keine Bestandteile von _MethodName_**Async** sein.</span><span class="sxs-lookup"><span data-stu-id="50522-213">`out` parameters to *MethodName* should not be part of _MethodName_**Async**.</span></span> <span data-ttu-id="50522-214">Stattdessen müssen sie Bestandteile von _MethodName_**CompletedEventArgs** mit denselben Namen wie ihre Parametergegenstücke in *MethodName* sein (es sei denn, es gibt geeignetere Namen).</span><span class="sxs-lookup"><span data-stu-id="50522-214">Instead, they should be part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

- <span data-ttu-id="50522-215">`ref`-Parameter für *MethodName* müssen als Bestandteile von _MethodName_**Async** und als Bestandteile von _MethodName_**CompletedEventArgs** mit denselben Namen wie ihre Parametergegenstücke in *MethodName* vorhanden sein (es sei denn, es gibt geeignetere Namen).</span><span class="sxs-lookup"><span data-stu-id="50522-215">`ref` parameters to *MethodName* should appear as part of _MethodName_**Async** , and as part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

<span data-ttu-id="50522-216">Angenommen, dies liegt vor:</span><span class="sxs-lookup"><span data-stu-id="50522-216">For example, given:</span></span>

```vb
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer
```

```csharp
public int MethodName(string arg1, ref string arg2, out string arg3);
```

<span data-ttu-id="50522-217">Die asynchrone Methode und die zugehörige <xref:System.ComponentModel.AsyncCompletedEventArgs>-Klasse würde wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="50522-217">Your asynchronous method and its <xref:System.ComponentModel.AsyncCompletedEventArgs> class would look like this:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="50522-218">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50522-218">See also</span></span>

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [<span data-ttu-id="50522-219">How to: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen</span><span class="sxs-lookup"><span data-stu-id="50522-219">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="50522-220">How to: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="50522-220">How to: Run an Operation in the Background</span></span>](/dotnet/desktop/winforms/controls/how-to-run-an-operation-in-the-background)
- [<span data-ttu-id="50522-221">How to: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="50522-221">How to: Implement a Form That Uses a Background Operation</span></span>](/dotnet/desktop/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation)
- [<span data-ttu-id="50522-222">Deciding When to Implement the Event-based Asynchronous Pattern (Gründe für das Implementieren des ereignisbasierten asynchronen Musters)</span><span class="sxs-lookup"><span data-stu-id="50522-222">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="50522-223">Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="50522-223">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="50522-224">Ereignisbasiertes asynchrones Muster (EAP)</span><span class="sxs-lookup"><span data-stu-id="50522-224">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
