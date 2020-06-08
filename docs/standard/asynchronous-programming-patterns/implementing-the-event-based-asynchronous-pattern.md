---
title: Implementieren des ereignisbasierten asynchronen Entwurfsmusters
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 484050b45b5da72386e9ac29805d7faf0ca9cbd6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289381"
---
# <a name="implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="4c6a9-102">Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="4c6a9-102">Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="4c6a9-103">Wenn Sie eine Klasse mit Vorgängen schreiben, die nennenswerte Verzögerungen verursachen können, sollten Sie die Klasse mit einer asynchronen Funktionalität ausstatten, indem Sie das ereignisbasierte asynchrone Muster implementieren. Informationen zu diesem Muster finden Sie unter [Übersicht über ereignisbasierte asynchrone Muster](event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4c6a9-103">If you are writing a class with some operations that may incur noticeable delays, consider giving it asynchronous functionality by implementing [Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md).</span></span>

<span data-ttu-id="4c6a9-104">Das ereignisbasierte asynchrone Muster bietet eine standardisierte Möglichkeit zum Verpacken einer Klasse, die asynchrone Features hat.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-104">The Event-based Asynchronous Pattern provides a standardized way to package a class that has asynchronous features.</span></span> <span data-ttu-id="4c6a9-105">Ist eine Klasse mit Hilfsklassen wie <xref:System.ComponentModel.AsyncOperationManager> implementiert, funktioniert sie unter jedem beliebigen Anwendungsmodell korrekt, einschließlich ASP.NET, Konsolenanwendungen und Windows Forms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-105">If implemented with helper classes like <xref:System.ComponentModel.AsyncOperationManager>, your class will work correctly under any application model, including ASP.NET, Console applications, and Windows Forms applications.</span></span>

<span data-ttu-id="4c6a9-106">Ein Beispiel, in dem das ereignisbasierte asynchrone Muster implementiert ist, finden Sie unter [Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt](component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="4c6a9-106">For an example that implements the Event-based Asynchronous Pattern, see [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="4c6a9-107">Für einfache asynchrone Vorgänge ist möglicherweise die Komponente <xref:System.ComponentModel.BackgroundWorker> gut geeignet.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-107">For simple asynchronous operations, you may find the <xref:System.ComponentModel.BackgroundWorker> component suitable.</span></span> <span data-ttu-id="4c6a9-108">Weitere Informationen zu <xref:System.ComponentModel.BackgroundWorker> finden Sie unter [Gewusst wie: Ausführen eines Vorgangs im Hintergrund](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="4c6a9-108">For more information about <xref:System.ComponentModel.BackgroundWorker>, see [How to: Run an Operation in the Background](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md).</span></span>

<span data-ttu-id="4c6a9-109">In der folgenden Liste sind die Features des ereignisbasierten asynchronen Musters aufgeführt, die in diesem Thema beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-109">The following list describes the features of the Event-based Asynchronous Pattern discussed in this topic.</span></span>

- <span data-ttu-id="4c6a9-110">Gelegenheiten für Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="4c6a9-110">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

- <span data-ttu-id="4c6a9-111">Benennen von asynchronen Methoden</span><span class="sxs-lookup"><span data-stu-id="4c6a9-111">Naming Asynchronous Methods</span></span>

- <span data-ttu-id="4c6a9-112">Optionales Unterstützen von Abbruch</span><span class="sxs-lookup"><span data-stu-id="4c6a9-112">Optionally Support Cancellation</span></span>

- <span data-ttu-id="4c6a9-113">Optionales Unterstützen der „IsBusy“-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4c6a9-113">Optionally Support the IsBusy Property</span></span>

- <span data-ttu-id="4c6a9-114">Optionales Unterstützen von Statusberichterstellung</span><span class="sxs-lookup"><span data-stu-id="4c6a9-114">Optionally Provide Support for Progress Reporting</span></span>

- <span data-ttu-id="4c6a9-115">Optionales Unterstützen der Rückgabe von inkrementellen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="4c6a9-115">Optionally Provide Support for Returning Incremental Results</span></span>

- <span data-ttu-id="4c6a9-116">Verarbeiten von „out“- und „ref“-Parametern in Methoden</span><span class="sxs-lookup"><span data-stu-id="4c6a9-116">Handling Out and Ref Parameters in Methods</span></span>

## <a name="opportunities-for-implementing-the-event-based-asynchronous-pattern"></a><span data-ttu-id="4c6a9-117">Gelegenheiten für Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="4c6a9-117">Opportunities for Implementing the Event-based Asynchronous Pattern</span></span>

<span data-ttu-id="4c6a9-118">Implementieren des ereignisbasierten asynchronen Entwurfsmusters bietet sich an, wenn Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-118">Consider implementing the Event-based Asynchronous Pattern when:</span></span>

- <span data-ttu-id="4c6a9-119">Clients einer Klasse benötigen keine <xref:System.Threading.WaitHandle>- und <xref:System.IAsyncResult>-Objekte, die für asynchrone Vorgänge verfügbar sind, d.h. Abfragen und <xref:System.Threading.WaitHandle.WaitAll%2A> oder <xref:System.Threading.WaitHandle.WaitAny%2A> müssen vom Client erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-119">Clients of your class do not need <xref:System.Threading.WaitHandle> and <xref:System.IAsyncResult> objects available for asynchronous operations, meaning that polling and <xref:System.Threading.WaitHandle.WaitAll%2A> or <xref:System.Threading.WaitHandle.WaitAny%2A> will need to be built up by the client.</span></span>

- <span data-ttu-id="4c6a9-120">Asynchrone Vorgänge sollen vom Client mit dem vertrauten Ereignis/Delegat-Modell verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-120">You want asynchronous operations to be managed by the client with the familiar event/delegate model.</span></span>

<span data-ttu-id="4c6a9-121">Jeder Vorgang ist ein Kandidat für eine asynchrone Implementierung, aber ein Vorgang, für den Sie lange Wartezeiten erwarten, sollte auf alle Fälle berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-121">Any operation is a candidate for an asynchronous implementation, but those you expect to incur long latencies should be considered.</span></span> <span data-ttu-id="4c6a9-122">Besonders geeignet sind Vorgänge, in denen Clients eine Methode aufrufen und bei Abschluss benachrichtigt werden, ohne dass weiteres Eingreifen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-122">Especially appropriate are operations in which clients call a method and are notified on completion, with no further intervention required.</span></span> <span data-ttu-id="4c6a9-123">Geeignet sind außerdem Vorgänge, die durchgängig ausgeführt werden und dabei Clients regelmäßig über Fortschritte, inkrementelle Ergebnisse oder Zustandsänderungen benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-123">Also appropriate are operations which run continuously, periodically notifying clients of progress, incremental results, or state changes.</span></span>

<span data-ttu-id="4c6a9-124">Weitere Informationen dazu, wie entschieden werden soll, ob das ereignisbasierte asynchrone Muster unterstützt werden sollte, finden Sie unter [Gründe für das Implementieren des ereignisbasierten asynchronen Musters](deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="4c6a9-124">For more information on deciding when to support the Event-based Asynchronous Pattern, see [Deciding When to Implement the Event-based Asynchronous Pattern](deciding-when-to-implement-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="naming-asynchronous-methods"></a><span data-ttu-id="4c6a9-125">Benennen von asynchronen Methoden</span><span class="sxs-lookup"><span data-stu-id="4c6a9-125">Naming Asynchronous Methods</span></span>

<span data-ttu-id="4c6a9-126">Definieren Sie für jede synchrone Methode *MethodName*, für die Sie ein asynchrones Gegenstück bereitstellen möchten, Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-126">For each synchronous method *MethodName* for which you want to provide an asynchronous counterpart:</span></span>

<span data-ttu-id="4c6a9-127">Definieren Sie eine _MethodName_**Async**-Methode, für die Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-127">Define a _MethodName_**Async** method that:</span></span>

- <span data-ttu-id="4c6a9-128">Gibt `void`zurück.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-128">Returns `void`.</span></span>

- <span data-ttu-id="4c6a9-129">Dieselben Parameter hat wie die *MethodName*-Methode.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-129">Takes the same parameters as the *MethodName* method.</span></span>

- <span data-ttu-id="4c6a9-130">Mehrere Aufrufe akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-130">Accepts multiple invocations.</span></span>

<span data-ttu-id="4c6a9-131">Definieren Sie optional eine _MethodName_**Async**-Überladung, die mit _MethodName_**Async** identisch ist, aber einen zusätzlichen Objektparameter namens `userState` hat.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-131">Optionally define a _MethodName_**Async** overload, identical to _MethodName_**Async**, but with an additional object-valued parameter called `userState`.</span></span> <span data-ttu-id="4c6a9-132">Dies sollten Sie tun, wenn Sie mehrere gleichzeitige Aufrufe der Methode verwalten möchten. In diesem Fall wird der `userState`-Wert an alle Ereignishandler zurückgegeben, um die Aufrufe der Methode zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-132">Do this if you're prepared to manage multiple concurrent invocations of your method, in which case the `userState` value will be delivered back to all event handlers to distinguish invocations of the method.</span></span> <span data-ttu-id="4c6a9-133">Diese Vorgehensweise bietet sich auch an, wenn Sie einfach einen Platz haben möchten, in dem der Benutzerstatus für spätere Abrufe gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-133">You may also choose to do this simply as a place to store user state for later retrieval.</span></span>

<span data-ttu-id="4c6a9-134">Definieren Sie für jede einzelne _MethodName_**Async**-Methodensignatur:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-134">For each separate _MethodName_**Async** method signature:</span></span>

1. <span data-ttu-id="4c6a9-135">Das folgende Ereignis in derselben Klasse wie die Methode:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-135">Define the following event in the same class as the method:</span></span>

    ```vb
    Public Event MethodNameCompleted As MethodNameCompletedEventHandler
    ```

    ```csharp
    public event MethodNameCompletedEventHandler MethodNameCompleted;
    ```

2. <span data-ttu-id="4c6a9-136">Den folgenden Delegaten und <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-136">Define the following delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs>.</span></span> <span data-ttu-id="4c6a9-137">Diese sind wahrscheinlich außerhalb der Klasse selbst, aber im selben Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-137">These will likely be defined outside of the class itself, but in the same namespace.</span></span>

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

    - <span data-ttu-id="4c6a9-138">Stellen Sie sicher, dass die _MethodName_**CompletedEventArgs**-Klasse ihre Elemente als schreibgeschützte Eigenschaften verfügbar macht, und nicht als Felder, weil Felder Datenbindungen verhindern.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-138">Ensure that the _MethodName_**CompletedEventArgs** class exposes its members as read-only properties, and not fields, as fields prevent data binding.</span></span>

    - <span data-ttu-id="4c6a9-139">Definieren Sie keine <xref:System.ComponentModel.AsyncCompletedEventArgs>-abgeleitete Klassen für Methoden, die keine Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-139">Do not define any <xref:System.ComponentModel.AsyncCompletedEventArgs>-derived classes for methods that do not produce results.</span></span> <span data-ttu-id="4c6a9-140">Verwenden Sie einfach eine Instanz von <xref:System.ComponentModel.AsyncCompletedEventArgs> selbst.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-140">Simply use an instance of <xref:System.ComponentModel.AsyncCompletedEventArgs> itself.</span></span>

      > [!NOTE]
      > <span data-ttu-id="4c6a9-141">Es ist durchaus akzeptabel, wenn machbar und angemessen, Delegaten und <xref:System.ComponentModel.AsyncCompletedEventArgs>-Typen wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-141">It is perfectly acceptable, when feasible and appropriate, to reuse delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> types.</span></span> <span data-ttu-id="4c6a9-142">In diesem Fall ist die Benennung nicht so konsistent wie mit dem Methodennamen, da ein bestimmter Delegat und <xref:System.ComponentModel.AsyncCompletedEventArgs> nicht an eine einzelne Methode gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-142">In this case, the naming will not be as consistent with the method name, since a given delegate and <xref:System.ComponentModel.AsyncCompletedEventArgs> won't be tied to a single method.</span></span>

## <a name="optionally-support-cancellation"></a><span data-ttu-id="4c6a9-143">Optionales Unterstützen von Abbruch</span><span class="sxs-lookup"><span data-stu-id="4c6a9-143">Optionally Support Cancellation</span></span>

<span data-ttu-id="4c6a9-144">Wenn Ihre Klasse das Abbrechen von asynchronen Vorgängen unterstützt, sollte Abbruch so für den Client verfügbar gemacht werden, wie dies weiter unten beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-144">If your class will support canceling asynchronous operations, cancellation should be exposed to the client as described below.</span></span> <span data-ttu-id="4c6a9-145">Es gibt zwei Entscheidungspunkte, die erreicht sein müssen, bevor Abbruchunterstützung definiert wird:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-145">Note that there are two decision points that need to be reached before defining your cancellation support:</span></span>

- <span data-ttu-id="4c6a9-146">Hat die Klasse, einschließlich zukünftiger zu erwartender Erweiterungen, nur einen asynchronen Vorgang, der Abbruch unterstützt?</span><span class="sxs-lookup"><span data-stu-id="4c6a9-146">Does your class, including future anticipated additions to it, have only one asynchronous operation that supports cancellation?</span></span>

- <span data-ttu-id="4c6a9-147">Können die asynchronen Vorgänge, die Abbruch unterstützen, mehrere ausstehende Vorgänge unterstützen?</span><span class="sxs-lookup"><span data-stu-id="4c6a9-147">Can the asynchronous operations that support cancellation support multiple pending operations?</span></span> <span data-ttu-id="4c6a9-148">Das heißt, hat die _MethodName_**Async**-Methode den `userState`-Parameter akzeptiert und lässt sie mehrere Aufrufe zu, bevor sie für jeden auf dessen Beendigung wartet?</span><span class="sxs-lookup"><span data-stu-id="4c6a9-148">That is, does the _MethodName_**Async** method take a `userState` parameter, and does it allow multiple invocations before waiting for any to finish?</span></span>

<span data-ttu-id="4c6a9-149">Entscheiden Sie anhand der Antworten auf die beiden Fragen in der folgenden Tabelle, welche Signatur für die Abbruchmethode zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-149">Use the answers to these two questions in the table below to determine what the signature for your cancellation method should be.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="4c6a9-150">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c6a9-150">Visual Basic</span></span>

||<span data-ttu-id="4c6a9-151">Mehrere gleichzeitige Vorgänge unterstützt</span><span class="sxs-lookup"><span data-stu-id="4c6a9-151">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="4c6a9-152">Nur immer jeweils ein Vorgang</span><span class="sxs-lookup"><span data-stu-id="4c6a9-152">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="4c6a9-153">Ein asynchroner Vorgang in der gesamten Klasse</span><span class="sxs-lookup"><span data-stu-id="4c6a9-153">One Async Operation in entire class</span></span>|`Sub MethodNameAsyncCancel(ByVal userState As Object)`|`Sub MethodNameAsyncCancel()`|
|<span data-ttu-id="4c6a9-154">Mehrere asynchrone Vorgänge in der Klasse</span><span class="sxs-lookup"><span data-stu-id="4c6a9-154">Multiple Async Operations in class</span></span>|`Sub CancelAsync(ByVal userState As Object)`|`Sub CancelAsync()`|

### <a name="c"></a><span data-ttu-id="4c6a9-155">C\#</span><span class="sxs-lookup"><span data-stu-id="4c6a9-155">C\#</span></span>

||<span data-ttu-id="4c6a9-156">Mehrere gleichzeitige Vorgänge unterstützt</span><span class="sxs-lookup"><span data-stu-id="4c6a9-156">Multiple Simultaneous Operations Supported</span></span>|<span data-ttu-id="4c6a9-157">Nur immer jeweils ein Vorgang</span><span class="sxs-lookup"><span data-stu-id="4c6a9-157">Only One Operation at a Time</span></span>|
|------|------------------------------------------------|----------------------------------|
|<span data-ttu-id="4c6a9-158">Ein asynchroner Vorgang in der gesamten Klasse</span><span class="sxs-lookup"><span data-stu-id="4c6a9-158">One Async Operation in entire class</span></span>|`void MethodNameAsyncCancel(object userState);`|`void MethodNameAsyncCancel();`|
|<span data-ttu-id="4c6a9-159">Mehrere asynchrone Vorgänge in der Klasse</span><span class="sxs-lookup"><span data-stu-id="4c6a9-159">Multiple Async Operations in class</span></span>|`void CancelAsync(object userState);`|`void CancelAsync();`|

<span data-ttu-id="4c6a9-160">Wenn Sie die `CancelAsync(object userState)`-Methode definieren, müssen Clients bei der Auswahl ihrer Statuswerte vorsichtig sein, damit sie in der Lage sind, zwischen allen für das Objekt aufgerufenen asynchronen Methoden, nicht nur zwischen allen Aufrufen einer einzigen asynchronen Methode zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-160">If you define the `CancelAsync(object userState)` method, clients must be careful when choosing their state values to make them capable of distinguishing among all asynchronous methods invoked on the object, and not just between all invocations of a single asynchronous method.</span></span>

<span data-ttu-id="4c6a9-161">Es wurde entschieden, die Version mit einzelnem asynchronen Vorgang als _MethodName_**AsyncCancel** zu benennen, um die Methode in einer Entwurfsumgebung wie Visual Studios IntelliSense einfacher erkennen zu können.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-161">The decision to name the single-async-operation version _MethodName_**AsyncCancel** is based on being able to more easily discover the method in a design environment like Visual Studio's IntelliSense.</span></span> <span data-ttu-id="4c6a9-162">Dadurch werden die zusammengehörenden Member gruppiert und lassen sich von anderen Membern unterscheiden, die nichts mit der asynchronen Funktionalität zu tun haben.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-162">This groups the related members and distinguishes them from other members that have nothing to do with asynchronous functionality.</span></span> <span data-ttu-id="4c6a9-163">Wenn Sie davon ausgehen, dass in späteren Versionen weitere asynchrone Vorgänge hinzugefügt werden, sollten Sie `CancelAsync` definieren.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-163">If you expect that there may be additional asynchronous operations added in subsequent versions, it is better to define `CancelAsync`.</span></span>

<span data-ttu-id="4c6a9-164">Definieren Sie nicht mehrere Methoden aus der obigen Tabelle in derselben Klasse.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-164">Do not define multiple methods from the table above in the same class.</span></span> <span data-ttu-id="4c6a9-165">Dies ist nicht sinnvoll oder führt dazu, dass in der Klassenschnittstelle unnötig viele Methoden bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-165">That will not make sense, or it will clutter the class interface with a proliferation of methods.</span></span>

<span data-ttu-id="4c6a9-166">Diese Methoden führen üblicherweise sofort eine Rückkehr aus, und der Vorgang wird möglicherweise tatsächlich abgebrochen (oder nicht).</span><span class="sxs-lookup"><span data-stu-id="4c6a9-166">These methods typically will return immediately, and the operation may or may not actually cancel.</span></span> <span data-ttu-id="4c6a9-167">Im Ereignishandler für das _MethodName_**Completed**-Ereignis enthält das _MethodName_**CompletedEventArgs**-Objekt ein `Cancelled`-Feld, anhand dessen Clients ermitteln können, ob der Abbruch aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-167">In the event handler for the _MethodName_**Completed** event, the _MethodName_**CompletedEventArgs** object contains a `Cancelled` field, which clients can use to determine whether the cancellation occurred.</span></span>

<span data-ttu-id="4c6a9-168">Halten Sie sich an die Abbruchsemantik, die unter [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](best-practices-for-implementing-the-event-based-asynchronous-pattern.md) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-168">Abide by the cancellation semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-support-the-isbusy-property"></a><span data-ttu-id="4c6a9-169">Optionales Unterstützen der „IsBusy“-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4c6a9-169">Optionally Support the IsBusy Property</span></span>

<span data-ttu-id="4c6a9-170">Unterstützt die Klasse nicht mehrere gleichzeitige Aufrufe, sollten Sie eine `IsBusy`-Eigenschaft verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-170">If your class does not support multiple concurrent invocations, consider exposing an `IsBusy` property.</span></span> <span data-ttu-id="4c6a9-171">Dies ermöglicht Entwicklern, zu bestimmen, ob eine _MethodName_**Async**-Methode ausgeführt wird, ohne eine Ausnahme von der _MethodName_**Async**-Methode abzufangen.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-171">This allows developers to determine whether a _MethodName_**Async** method is running without catching an exception from the _MethodName_**Async** method.</span></span>

<span data-ttu-id="4c6a9-172">Halten Sie sich an die `IsBusy`-Semantik, die unter [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](best-practices-for-implementing-the-event-based-asynchronous-pattern.md) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-172">Abide by the `IsBusy` semantics described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-progress-reporting"></a><span data-ttu-id="4c6a9-173">Optionales Unterstützen von Statusberichterstellung</span><span class="sxs-lookup"><span data-stu-id="4c6a9-173">Optionally Provide Support for Progress Reporting</span></span>

<span data-ttu-id="4c6a9-174">Es ist häufig wünschenswert, dass ein asynchroner Vorgang während seiner Ausführung den Status mitteilt.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-174">It is frequently desirable for an asynchronous operation to report progress during its operation.</span></span> <span data-ttu-id="4c6a9-175">Das ereignisbasierte asynchrone Muster stellt eine Richtlinie dafür bereit.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-175">The Event-based Asynchronous Pattern provides a guideline for doing so.</span></span>

- <span data-ttu-id="4c6a9-176">Definieren Sie optional ein Ereignis, das vom asynchronen Vorgang ausgelöst und im entsprechenden Thread aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-176">Optionally define an event to be raised by the asynchronous operation and invoked on the appropriate thread.</span></span> <span data-ttu-id="4c6a9-177">Das <xref:System.ComponentModel.ProgressChangedEventArgs>-Objekt enthält eine Statusanzeige mit Ganzzahlwert, der zwischen 0 und 100 liegt.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-177">The <xref:System.ComponentModel.ProgressChangedEventArgs> object carries an integer-valued progress indicator that is expected to be between 0 and 100.</span></span>

- <span data-ttu-id="4c6a9-178">Benennen Sie dieses Ereignis wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-178">Name this event as follows:</span></span>

  - <span data-ttu-id="4c6a9-179">`ProgressChanged`, wenn die Klasse mehrere asynchrone Vorgänge hat (oder vermutlich so erweitert wird, dass sie in zukünftigen Versionen mehrere asynchrone Vorgänge haben wird)</span><span class="sxs-lookup"><span data-stu-id="4c6a9-179">`ProgressChanged` if the class has multiple asynchronous operations (or is expected to grow to include multiple asynchronous operations in future versions);</span></span>

  - <span data-ttu-id="4c6a9-180">_MethodName_**ProgressChanged**, wenn die Klasse einen einzelnen asynchronen Vorgang hat.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-180">_MethodName_**ProgressChanged** if the class has a single asynchronous operation.</span></span>

  <span data-ttu-id="4c6a9-181">Diese Benennungskonvention entspricht derjenigen für die Abbruchmethode, wie im Abschnitt „Optionales Unterstützen von Abbruch“ beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-181">This naming choice parallels that made for the cancellation method, as described in the Optionally Support Cancellation section.</span></span>

<span data-ttu-id="4c6a9-182">Dieses Ereignis sollte die <xref:System.ComponentModel.ProgressChangedEventHandler>-Signatur des Delegaten und die <xref:System.ComponentModel.ProgressChangedEventArgs>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-182">This event should use the <xref:System.ComponentModel.ProgressChangedEventHandler> delegate signature and the <xref:System.ComponentModel.ProgressChangedEventArgs> class.</span></span> <span data-ttu-id="4c6a9-183">Für den Fall, dass eine bereichsspezifischere Statusanzeige bereitgestellt werden kann (beispielsweise gelesene Bytes und die Gesamtanzahl der Bytes für einen Downloadvorgang), sollten Sie eine abgeleitete Klasse von <xref:System.ComponentModel.ProgressChangedEventArgs> definieren.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-183">Alternatively, if a more domain-specific progress indicator can be provided (for instance, bytes read and total bytes for a download operation), then you should define a derived class of <xref:System.ComponentModel.ProgressChangedEventArgs>.</span></span>

<span data-ttu-id="4c6a9-184">Beachten Sie, dass es nur ein `ProgressChanged`- oder _MethodName_**ProgressChanged**-Ereignis für die Klasse gibt, unabhängig davon, wie viele asynchrone Methoden sie unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-184">Note that there is only one `ProgressChanged` or _MethodName_**ProgressChanged** event for the class, regardless of the number of asynchronous methods it supports.</span></span> <span data-ttu-id="4c6a9-185">Für Clients wird vorausgesetzt, dass sie das `userState`-Objekt verwenden, das an die _MethodName_**Async**-Methoden übergeben wird, um zwischen Statusupdates bei mehreren gleichzeitigen Vorgängen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-185">Clients are expected to use the `userState` object that is passed to the _MethodName_**Async** methods to distinguish among progress updates on multiple concurrent operations.</span></span>

<span data-ttu-id="4c6a9-186">Es kann Situationen geben, in denen mehrere Vorgänge einen Status unterstützen und jeder Vorgang einen anderen Indikator für den Status zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-186">There may be situations in which multiple operations support progress and each returns a different indicator for progress.</span></span> <span data-ttu-id="4c6a9-187">In diesem Fall ist ein einzelnes `ProgressChanged`-Ereignis nicht geeignet, und Sie sollten Unterstützung für mehrere `ProgressChanged`-Ereignisse erwägen.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-187">In this case, a single `ProgressChanged` event is not appropriate, and you may consider supporting multiple `ProgressChanged` events.</span></span> <span data-ttu-id="4c6a9-188">Verwenden Sie für diesen Fall das Benennungsmuster _MethodName_**ProgressChanged** für jede _MethodName_**Async**-Methode.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-188">In this case use a naming pattern of _MethodName_**ProgressChanged** for each _MethodName_**Async** method.</span></span>

<span data-ttu-id="4c6a9-189">Halten Sie sich an die Statusberichte-Semantik, die unter [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](best-practices-for-implementing-the-event-based-asynchronous-pattern.md) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-189">Abide by the progress-reporting semantics described [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="optionally-provide-support-for-returning-incremental-results"></a><span data-ttu-id="4c6a9-190">Optionales Unterstützen der Rückgabe von inkrementellen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="4c6a9-190">Optionally Provide Support for Returning Incremental Results</span></span>

<span data-ttu-id="4c6a9-191">Möglicherweise gibt ein asynchroner Vorgang vor seiner Beendigung inkrementelle Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-191">Sometimes an asynchronous operation can return incremental results prior to completion.</span></span> <span data-ttu-id="4c6a9-192">Zur Unterstützung dieses Szenarios gibt es eine Reihe von Optionen, die verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-192">There are a number of options that can be used to support this scenario.</span></span> <span data-ttu-id="4c6a9-193">Es folgen einige Beispiele.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-193">Some examples follow.</span></span>

### <a name="single-operation-class"></a><span data-ttu-id="4c6a9-194">Klasse mit einem einzigen Vorgang</span><span class="sxs-lookup"><span data-stu-id="4c6a9-194">Single-operation Class</span></span>

<span data-ttu-id="4c6a9-195">Unterstützt die Klasse nur einen einzigen asynchronen Vorgang, und kann dieser Vorgang inkrementelle Ergebnisse zurückgeben, dann gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-195">If your class only supports a single asynchronous operation, and that operation is able to return incremental results, then:</span></span>

- <span data-ttu-id="4c6a9-196">Erweitern Sie den <xref:System.ComponentModel.ProgressChangedEventArgs>-Typ, damit er die Daten eines inkrementellen Ergebnisses aufnehmen kann, und definieren Sie ein _MethodName_**ProgressChanged**-Ereignis mit diesen erweiterten Daten.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-196">Extend the <xref:System.ComponentModel.ProgressChangedEventArgs> type to carry the incremental result data, and define a _MethodName_**ProgressChanged** event with this extended data.</span></span>

- <span data-ttu-id="4c6a9-197">Lösen Sie dieses _MethodName_**ProgressChanged**-Ereignis aus, sobald ein zu berichtendes inkrementelles Ergebnis vorliegt.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-197">Raise this _MethodName_**ProgressChanged** event when there is an incremental result to report.</span></span>

<span data-ttu-id="4c6a9-198">Diese Lösung ist speziell für eine Klasse mit einzelnem asynchronen Vorgang anwendbar, weil es kein Problem damit gibt, dass dasselbe auftretende Ereignis inkrementelle Ergebnisse für „alle Vorgänge“ zurückgibt, denn das _MethodName_**ProgressChanged**-Ereignis erledigt dies.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-198">This solution applies specifically to a single-async-operation class because there is no problem with the same event occurring to return incremental results on "all operations", as the _MethodName_**ProgressChanged** event does.</span></span>

### <a name="multiple-operation-class-with-homogeneous-incremental-results"></a><span data-ttu-id="4c6a9-199">Klasse mit mehreren Vorgängen und homogenen inkrementellen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="4c6a9-199">Multiple-operation Class with Homogeneous Incremental Results</span></span>

<span data-ttu-id="4c6a9-200">In diesem Fall unterstützt die Klasse mehrere asynchrone Methoden, von denen jede inkrementelle Ergebnisse zurückgeben kann, wobei diese inkrementellen Ergebnisse alle denselben Datentyp haben.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-200">In this case, your class supports multiple asynchronous methods, each capable of returning incremental results, and these incremental results all have the same type of data.</span></span>

<span data-ttu-id="4c6a9-201">Gehen Sie entsprechend dem oben beschriebenen Modell für Klassen mit einzelnem Vorgang vor, da die gleiche <xref:System.EventArgs>-Struktur für alle inkrementellen Ergebnisse funktioniert.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-201">Follow the model described above for single-operation classes, as the same <xref:System.EventArgs> structure will work for all incremental results.</span></span> <span data-ttu-id="4c6a9-202">Definieren Sie ein `ProgressChanged`-Ereignis anstelle eines _MethodName_**ProgressChanged**-Ereignisses, weil es für mehrere asynchrone Methoden gilt.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-202">Define a `ProgressChanged` event instead of a _MethodName_**ProgressChanged** event, since it applies to multiple asynchronous methods.</span></span>

### <a name="multiple-operation-class-with-heterogeneous-incremental-results"></a><span data-ttu-id="4c6a9-203">Klasse mit mehreren Vorgängen und heterogenen inkrementellen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="4c6a9-203">Multiple-operation Class with Heterogeneous Incremental Results</span></span>

<span data-ttu-id="4c6a9-204">Wenn die Klasse mehrere asynchrone Methoden unterstützt, wobei jede Methode Daten eines anderen Typs zurückgibt, sollten Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-204">If your class supports multiple asynchronous methods, each returning a different type of data, you should:</span></span>

- <span data-ttu-id="4c6a9-205">Trennen Sie die Mitteilungen über inkrementelle Ergebnisse von den Statusmitteilungen.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-205">Separate your incremental result reporting from your progress reporting.</span></span>

- <span data-ttu-id="4c6a9-206">Definieren Sie für jede asynchrone Methode ein eigenes _MethodName_**ProgressChanged**-Ereignis mit entsprechenden <xref:System.EventArgs>, um die Daten eines inkrementellen Ergebnisses dieser Methode zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-206">Define a separate _MethodName_**ProgressChanged** event with appropriate <xref:System.EventArgs> for each asynchronous method to handle that method's incremental result data.</span></span>

<span data-ttu-id="4c6a9-207">Rufen Sie diesen Ereignishandler für den entsprechenden Thread auf, wie dies unter [Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters](best-practices-for-implementing-the-event-based-asynchronous-pattern.md) beschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-207">Invoke that event handler on the appropriate thread as described in [Best Practices for Implementing the Event-based Asynchronous Pattern](best-practices-for-implementing-the-event-based-asynchronous-pattern.md).</span></span>

## <a name="handling-out-and-ref-parameters-in-methods"></a><span data-ttu-id="4c6a9-208">Verarbeiten von „out“- und „ref“-Parametern in Methoden</span><span class="sxs-lookup"><span data-stu-id="4c6a9-208">Handling Out and Ref Parameters in Methods</span></span>

<span data-ttu-id="4c6a9-209">Grundsätzlich wird davon abgeraten, `out` und `ref` in .NET Framework zu verwenden. Sind diese aber vorhanden, sollten die folgenden Regeln beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-209">Although the use of `out` and `ref` is, in general, discouraged in the .NET Framework, here are the rules to follow when they are present:</span></span>

<span data-ttu-id="4c6a9-210">Angenommen, es gibt die synchrone Methode *MethodName*:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-210">Given a synchronous method *MethodName*:</span></span>

- <span data-ttu-id="4c6a9-211">`out`-Parameter für *MethodName* dürfen keine Bestandteile von _MethodName_**Async** sein.</span><span class="sxs-lookup"><span data-stu-id="4c6a9-211">`out` parameters to *MethodName* should not be part of _MethodName_**Async**.</span></span> <span data-ttu-id="4c6a9-212">Stattdessen müssen sie Bestandteile von _MethodName_**CompletedEventArgs** mit denselben Namen wie ihre Parametergegenstücke in *MethodName* sein (es sei denn, es gibt geeignetere Namen).</span><span class="sxs-lookup"><span data-stu-id="4c6a9-212">Instead, they should be part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

- <span data-ttu-id="4c6a9-213">`ref`-Parameter für *MethodName* müssen als Bestandteile von _MethodName_**Async** und als Bestandteile von _MethodName_**CompletedEventArgs** mit denselben Namen wie ihre Parametergegenstücke in *MethodName* vorhanden sein (es sei denn, es gibt geeignetere Namen).</span><span class="sxs-lookup"><span data-stu-id="4c6a9-213">`ref` parameters to *MethodName* should appear as part of _MethodName_**Async**, and as part of _MethodName_**CompletedEventArgs** with the same name as its parameter equivalent in *MethodName* (unless there is a more appropriate name).</span></span>

<span data-ttu-id="4c6a9-214">Angenommen, dies liegt vor:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-214">For example, given:</span></span>

```vb
Public Function MethodName(ByVal arg1 As String, ByRef arg2 As String, ByRef arg3 As String) As Integer
```

```csharp
public int MethodName(string arg1, ref string arg2, out string arg3);
```

<span data-ttu-id="4c6a9-215">Die asynchrone Methode und die zugehörige <xref:System.ComponentModel.AsyncCompletedEventArgs>-Klasse würde wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="4c6a9-215">Your asynchronous method and its <xref:System.ComponentModel.AsyncCompletedEventArgs> class would look like this:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4c6a9-216">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c6a9-216">See also</span></span>

- <xref:System.ComponentModel.ProgressChangedEventArgs>
- <xref:System.ComponentModel.AsyncCompletedEventArgs>
- [<span data-ttu-id="4c6a9-217">Gewusst wie: Implementieren einer Komponente, die das ereignisbasierte asynchrone Muster unterstützt</span><span class="sxs-lookup"><span data-stu-id="4c6a9-217">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="4c6a9-218">Gewusst wie: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="4c6a9-218">How to: Run an Operation in the Background</span></span>](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="4c6a9-219">Vorgehensweise: Implementieren eines Formulars, das eine Hintergrundoperation verwendet</span><span class="sxs-lookup"><span data-stu-id="4c6a9-219">How to: Implement a Form That Uses a Background Operation</span></span>](../../framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="4c6a9-220">Deciding When to Implement the Event-based Asynchronous Pattern (Gründe für das Implementieren des ereignisbasierten asynchronen Musters)</span><span class="sxs-lookup"><span data-stu-id="4c6a9-220">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="4c6a9-221">Bewährte Verfahrensweisen für das Implementieren des ereignisbasierten asynchronen Entwurfsmusters</span><span class="sxs-lookup"><span data-stu-id="4c6a9-221">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)
- [<span data-ttu-id="4c6a9-222">Event-based Asynchronous Pattern (EAP) (Ereignisbasiertes asynchrones Muster (EAP))</span><span class="sxs-lookup"><span data-stu-id="4c6a9-222">Event-based Asynchronous Pattern (EAP)</span></span>](event-based-asynchronous-pattern-eap.md)
