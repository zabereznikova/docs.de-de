---
title: BinaryFormatter-Ereignisquelle
description: Erfahren Sie, wie Sie mit der BinaryFormatter-Ereignisquelle protokollieren können, wann Serialisierung oder Deserialisierung auftritt.
ms.date: 12/03/2020
ms.author: levib
author: GrabYourPitchforks
ms.openlocfilehash: 9ae2af77b6cfc270207fb0f2969ada8c2eca1153
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740389"
---
# <a name="binaryformatter-event-source"></a><span data-ttu-id="0aa9b-103">BinaryFormatter-Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="0aa9b-103">BinaryFormatter event source</span></span>

<span data-ttu-id="0aa9b-104">Ab .NET 5.0 umfasst <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> eine integrierte <xref:System.Diagnostics.Tracing.EventSource>, die Ihnen den Einblick verschafft, wann eine Objektserialisierung oder -deserialisierung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-104">Starting with .NET 5.0, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> includes a built-in <xref:System.Diagnostics.Tracing.EventSource> that gives you visibility into when an object serialization or deserialization is occurring.</span></span> <span data-ttu-id="0aa9b-105">Apps können mit von <xref:System.Diagnostics.Tracing.EventListener> abgeleiteten Typen auf diese Benachrichtigungen lauschen und sie protokollieren.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-105">Apps can use <xref:System.Diagnostics.Tracing.EventListener>-derived types to listen for these notifications and log them.</span></span>

<span data-ttu-id="0aa9b-106">Diese Funktion ist kein Ersatz für einen <xref:System.Runtime.Serialization.SerializationBinder> oder ein <xref:System.Runtime.Serialization.ISerializationSurrogate> und kann nicht verwendet werden, um die Daten zu ändern, die serialisiert oder deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-106">This functionality is not a substitute for a <xref:System.Runtime.Serialization.SerializationBinder> or an <xref:System.Runtime.Serialization.ISerializationSurrogate> and can't be used to modify the data being serialized or deserialized.</span></span> <span data-ttu-id="0aa9b-107">Vielmehr soll dieses Ereignissystem einen Einblick in die serialisierten oder deserialisierten Typen bieten.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-107">Rather, this eventing system is intended to provide insight into the types being serialized or deserialized.</span></span> <span data-ttu-id="0aa9b-108">Damit können auch unbeabsichtigte in die `BinaryFormatter`-Infrastruktur gerichtete Aufrufe erkannt werden, z. B. Aufrufe aus einem Bibliothekscode von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-108">It can also be used to detect unintended calls into the `BinaryFormatter` infrastructure, such as calls originating from third-party library code.</span></span>

## <a name="description-of-events"></a><span data-ttu-id="0aa9b-109">Beschreibung von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="0aa9b-109">Description of events</span></span>

<span data-ttu-id="0aa9b-110">Die `BinaryFormatter`-Ereignisquelle hat den bekannten Namen `System.Runtime.Serialization.Formatters.Binary.BinaryFormatterEventSource`.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-110">The `BinaryFormatter` event source has the well-known name `System.Runtime.Serialization.Formatters.Binary.BinaryFormatterEventSource`.</span></span> <span data-ttu-id="0aa9b-111">Listener können bis zu 6 Ereignisse abonnieren.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-111">Listeners may subscribe to 6 events.</span></span>

### <a name="serializationstart-event-id--10"></a><span data-ttu-id="0aa9b-112">SerializationStart-Ereignis (ID = `10`)</span><span class="sxs-lookup"><span data-stu-id="0aa9b-112">SerializationStart event (id = `10`)</span></span>

<span data-ttu-id="0aa9b-113">Wird ausgelöst, wenn <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> aufgerufen wurde und den Serialisierungsprozess gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-113">Raised when <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> has been called and has started the serialization process.</span></span> <span data-ttu-id="0aa9b-114">Dieses Ereignis ist mit dem `SerializationEnd`-Ereignis gekoppelt.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-114">This event is paired with the `SerializationEnd` event.</span></span> <span data-ttu-id="0aa9b-115">Das `SerializationStart`-Ereignis kann rekursiv aufgerufen werden, wenn ein Objekt `BinaryFormatter.Serialize` in seiner eigenen Serialisierungsroutine aufruft.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-115">The `SerializationStart` event can be called recursively if an object calls `BinaryFormatter.Serialize` within its own serialization routine.</span></span>

<span data-ttu-id="0aa9b-116">Dieses Ereignis enthält keine Nutzdaten.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-116">This event doesn't contain a payload.</span></span>

### <a name="serializationend-event-id--11"></a><span data-ttu-id="0aa9b-117">SerializationEnd-Ereignis (ID = `11`)</span><span class="sxs-lookup"><span data-stu-id="0aa9b-117">SerializationEnd event (id = `11`)</span></span>

<span data-ttu-id="0aa9b-118">Wird ausgelöst, wenn `BinaryFormatter.Serialize` seine Arbeit abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-118">Raised when `BinaryFormatter.Serialize` has completed its work.</span></span> <span data-ttu-id="0aa9b-119">Jedes Vorkommen von `SerializationEnd` gibt den Abschluss des letzten ungekoppelten `SerializationStart`-Ereignisses an.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-119">Each occurrence of `SerializationEnd` denotes the completion of the last unpaired `SerializationStart` event.</span></span>

<span data-ttu-id="0aa9b-120">Dieses Ereignis enthält keine Nutzdaten.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-120">This event doesn't contain a payload.</span></span>

### <a name="serializingobject-event-id--12"></a><span data-ttu-id="0aa9b-121">SerializingObject-Ereignis (ID = `12`)</span><span class="sxs-lookup"><span data-stu-id="0aa9b-121">SerializingObject event (id = `12`)</span></span>

<span data-ttu-id="0aa9b-122">Wird ausgelöst, wenn `BinaryFormatter.Serialize` gerade einen nicht primitiven Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-122">Raised when `BinaryFormatter.Serialize` is in the process of serializing a non-primitive type.</span></span> <span data-ttu-id="0aa9b-123">Die `BinaryFormatter`-Infrastruktur behandelt bestimmte Typen (z. B. `string` und `int`) als Sonderfälle und löst dieses Ereignis nicht aus, wenn diese Typen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-123">The `BinaryFormatter` infrastructure special-cases certain types (such as `string` and `int`) and doesn't raise this event when these types are encountered.</span></span> <span data-ttu-id="0aa9b-124">Dieses Ereignis wird für benutzerdefinierte Typen und andere Typen ausgelöst, die `BinaryFormatter` nicht nativ versteht.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-124">This event is raised for user-defined types and other types that `BinaryFormatter` doesn't natively understand.</span></span>

<span data-ttu-id="0aa9b-125">Es kann sein, dass dieses Ereignis zwischen den Ereignissen `SerializationStart` und `SerializationEnd` nicht oder mehrmals ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-125">This event may be raised zero or more times between `SerializationStart` and `SerializationEnd` events.</span></span>

<span data-ttu-id="0aa9b-126">Dieses Ereignis enthält eine Nutzlast mit einem Argument:</span><span class="sxs-lookup"><span data-stu-id="0aa9b-126">This event contains a payload with one argument:</span></span>

* <span data-ttu-id="0aa9b-127">`typeName` (`string`): Der Name mit Assemblyqualifikation (siehe <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) des Typs, der serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-127">`typeName` (`string`): The assembly-qualified name (see <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) of the type being serialized.</span></span>

### <a name="deserializationstart-event-id--20"></a><span data-ttu-id="0aa9b-128">DeserializationStart-Ereignis (ID = `20`)</span><span class="sxs-lookup"><span data-stu-id="0aa9b-128">DeserializationStart event (id = `20`)</span></span>

<span data-ttu-id="0aa9b-129">Wird ausgelöst, wenn <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> aufgerufen wurde und den Deserialisierungsprozess gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-129">Raised when <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> has been called and has started the deserialization process.</span></span> <span data-ttu-id="0aa9b-130">Dieses Ereignis ist mit dem `DeserializationEnd`-Ereignis gekoppelt.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-130">This event is paired with the `DeserializationEnd` event.</span></span> <span data-ttu-id="0aa9b-131">Das `DeserializationStart`-Ereignis kann rekursiv aufgerufen werden, wenn ein Objekt `BinaryFormatter.Deserialize` in seiner eigenen Deserialisierungsroutine aufruft.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-131">The `DeserializationStart` event can be called recursively if an object calls `BinaryFormatter.Deserialize` within its own deserialization routine.</span></span>

<span data-ttu-id="0aa9b-132">Dieses Ereignis enthält keine Nutzdaten.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-132">This event doesn't contain a payload.</span></span>

### <a name="deserializationend-event-id--21"></a><span data-ttu-id="0aa9b-133">DeserializationEnd-Ereignis (ID = `21`)</span><span class="sxs-lookup"><span data-stu-id="0aa9b-133">DeserializationEnd event (id = `21`)</span></span>

<span data-ttu-id="0aa9b-134">Wird ausgelöst, wenn `BinaryFormatter.Deserialize` seine Arbeit abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-134">Raised when `BinaryFormatter.Deserialize` has completed its work.</span></span> <span data-ttu-id="0aa9b-135">Jedes Vorkommen von `DeserializationEnd` gibt den Abschluss des letzten ungekoppelten `DeserializationStart`-Ereignisses an.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-135">Each occurrence of `DeserializationEnd` denotes the completion of the last unpaired `DeserializationStart` event.</span></span>

<span data-ttu-id="0aa9b-136">Dieses Ereignis enthält keine Nutzdaten.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-136">This event doesn't contain a payload.</span></span>

### <a name="deserializingobject-event-id--22"></a><span data-ttu-id="0aa9b-137">DeserializingObject-Ereignis (ID = `22`)</span><span class="sxs-lookup"><span data-stu-id="0aa9b-137">DeserializingObject event (id = `22`)</span></span>

<span data-ttu-id="0aa9b-138">Wird ausgelöst, wenn `BinaryFormatter.Deserialize` gerade einen nicht primitiven Typ deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-138">Raised when `BinaryFormatter.Deserialize` is in the process of deserializing a non-primitive type.</span></span> <span data-ttu-id="0aa9b-139">Die `BinaryFormatter`-Infrastruktur behandelt bestimmte Typen (z. B. `string` und `int`) als Sonderfälle und löst dieses Ereignis nicht aus, wenn diese Typen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-139">The `BinaryFormatter` infrastructure special-cases certain types (such as `string` and `int`) and doesn't raise this event when these types are encountered.</span></span> <span data-ttu-id="0aa9b-140">Dieses Ereignis wird für benutzerdefinierte Typen und andere Typen ausgelöst, die `BinaryFormatter` nicht nativ versteht.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-140">This event is raised for user-defined types and other types that `BinaryFormatter` doesn't natively understand.</span></span>

<span data-ttu-id="0aa9b-141">Es kann sein, dass dieses Ereignis zwischen den Ereignissen `DeserializationStart` und `DeserializationEnd` nicht oder mehrmals ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-141">This event may be raised zero or more times between `DeserializationStart` and `DeserializationEnd` events.</span></span>

<span data-ttu-id="0aa9b-142">Dieses Ereignis enthält eine Nutzlast mit einem Argument.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-142">This event contains a payload with one argument.</span></span>

* <span data-ttu-id="0aa9b-143">`typeName` (`string`): Der Name mit Assemblyqualifikation (siehe <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) des Typs, der deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-143">`typeName` (`string`): The assembly-qualified name (see <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) of the type being deserialized.</span></span>

### <a name="advanced-subscribing-to-a-subset-of-notifications"></a><span data-ttu-id="0aa9b-144">\[Erweitertes\] Abonnieren einer Teilmenge von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="0aa9b-144">\[Advanced\] Subscribing to a subset of notifications</span></span>

<span data-ttu-id="0aa9b-145">Listener, die nur eine Teilmenge von Benachrichtigungen abonnieren möchten, können auswählen, welche Schlüsselwörter aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-145">Listeners who wish to subscribe to only a subset of notifications can choose which keywords to enable.</span></span>

* <span data-ttu-id="0aa9b-146">`Serialization` = `(EventKeywords)1`: Löst die Ereignisse `SerializationStart`, `SerializationEnd` und `SerializingObject` aus.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-146">`Serialization` = `(EventKeywords)1`: Raises the `SerializationStart`, `SerializationEnd`, and `SerializingObject` events.</span></span>
* <span data-ttu-id="0aa9b-147">`Deserialization` = `(EventKeywords)2`: Löst die Ereignisse `DeserializationStart`, `DeserializationEnd` und `DeserializingObject` aus.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-147">`Deserialization` = `(EventKeywords)2`: Raises the `DeserializationStart`, `DeserializationEnd`, and `DeserializingObject` events.</span></span>

<span data-ttu-id="0aa9b-148">Wenn während der `EventListener`-Registrierung keine Schlüsselwortfilter bereitgestellt werden, werden alle Ereignisse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-148">If no keyword filters are provided during `EventListener` registration, all events are raised.</span></span>

<span data-ttu-id="0aa9b-149">Weitere Informationen finden Sie unter <xref:System.Diagnostics.Tracing.EventKeywords?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-149">For more information, see <xref:System.Diagnostics.Tracing.EventKeywords?displayProperty=nameWithType>.</span></span>

## <a name="sample-code"></a><span data-ttu-id="0aa9b-150">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="0aa9b-150">Sample code</span></span>

<span data-ttu-id="0aa9b-151">Der folgende Code</span><span class="sxs-lookup"><span data-stu-id="0aa9b-151">The following code:</span></span>

- <span data-ttu-id="0aa9b-152">erstellt einen vom `EventListener` abgeleiteten Typ, der in die `System.Console` schreibt,</span><span class="sxs-lookup"><span data-stu-id="0aa9b-152">creates an `EventListener`-derived type that writes to `System.Console`,</span></span>
- <span data-ttu-id="0aa9b-153">abonniert diesen Listener für Benachrichtigungen, die der `BinaryFormatter` erstellt,</span><span class="sxs-lookup"><span data-stu-id="0aa9b-153">subscribes that listener to `BinaryFormatter`-produced notifications,</span></span>
- <span data-ttu-id="0aa9b-154">serialisiert und deserialisiert einen einfachen Objektgraphen mit dem `BinaryFormatter` und</span><span class="sxs-lookup"><span data-stu-id="0aa9b-154">serializes and deserializes a simple object graph using `BinaryFormatter`, and</span></span>
- <span data-ttu-id="0aa9b-155">analysiert die ausgelösten Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-155">analyzes the events that have been raised.</span></span>

:::code language="csharp" source="snippets/binaryformatter-event-source/csharp/Program.cs":::

<span data-ttu-id="0aa9b-156">Der obige Code erzeugt eine Ausgabe, die folgendem Beispiel ähnelt:</span><span class="sxs-lookup"><span data-stu-id="0aa9b-156">The preceding code produces output similar to the following example:</span></span>

```output
Event SerializationStart (id=10) received.
Event SerializingObject (id=12) received.
typeName = BinaryFormatterEventSample.Person, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event SerializingObject (id=12) received.
typeName = BinaryFormatterEventSample.Book, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event SerializationStop (id=11) received.
Event DeserializationStart (id=20) received.
Event DeserializingObject (id=22) received.
typeName = BinaryFormatterEventSample.Person, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event DeserializingObject (id=22) received.
typeName = BinaryFormatterEventSample.Book, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event DeserializationStop (id=21) received.
Rehydrated person Logan Edwards
Favorite book: A Tale of Two Cities by Charles Dickens, list price 10.25
```

<span data-ttu-id="0aa9b-157">In diesem Beispiel protokolliert der konsolenbasierte `EventListener`, dass die Serialisierung beginnt, Instanzen von `Person` und `Book` serialisiert werden und die Serialisierung abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-157">In this sample, the console-based `EventListener` logs that serialization starts, instances of `Person` and `Book` are serialized, and then serialization completes.</span></span> <span data-ttu-id="0aa9b-158">Entsprechend werden Instanzen von `Person` und `Book` deserialisiert, sobald die Deserialisierung begonnen hat, und anschließend die Deserialisierung abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-158">Similarly, once deserialization has started, instances of `Person` and `Book` are deserialized, and then deserialization completes.</span></span>

<span data-ttu-id="0aa9b-159">Die App druckt dann die Werte, die im deserialisierten `Person` enthalten sind, um zu veranschaulichen, dass das Objekt tatsächlich ordnunsgemäß serialisiert und deserialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0aa9b-159">The app then prints the values contained in the deserialized `Person` to demonstrate that the object did in fact serialize and deserialize properly.</span></span>

## <a name="see-also"></a><span data-ttu-id="0aa9b-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0aa9b-160">See also</span></span>

<span data-ttu-id="0aa9b-161">Weitere Informationen zur Verwendung des `EventListener` zum Empfang `EventSource`-basierter Benachrichtigungen finden Sie unter [`EventListener`-Klasse](xref:System.Diagnostics.Tracing.EventListener).</span><span class="sxs-lookup"><span data-stu-id="0aa9b-161">For more information on using `EventListener` to receive `EventSource`-based notifications, see [the `EventListener` class](xref:System.Diagnostics.Tracing.EventListener).</span></span>
