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
# <a name="binaryformatter-event-source"></a>BinaryFormatter-Ereignisquelle

Ab .NET 5.0 umfasst <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> eine integrierte <xref:System.Diagnostics.Tracing.EventSource>, die Ihnen den Einblick verschafft, wann eine Objektserialisierung oder -deserialisierung stattfindet. Apps können mit von <xref:System.Diagnostics.Tracing.EventListener> abgeleiteten Typen auf diese Benachrichtigungen lauschen und sie protokollieren.

Diese Funktion ist kein Ersatz für einen <xref:System.Runtime.Serialization.SerializationBinder> oder ein <xref:System.Runtime.Serialization.ISerializationSurrogate> und kann nicht verwendet werden, um die Daten zu ändern, die serialisiert oder deserialisiert werden. Vielmehr soll dieses Ereignissystem einen Einblick in die serialisierten oder deserialisierten Typen bieten. Damit können auch unbeabsichtigte in die `BinaryFormatter`-Infrastruktur gerichtete Aufrufe erkannt werden, z. B. Aufrufe aus einem Bibliothekscode von Drittanbietern.

## <a name="description-of-events"></a>Beschreibung von Ereignissen

Die `BinaryFormatter`-Ereignisquelle hat den bekannten Namen `System.Runtime.Serialization.Formatters.Binary.BinaryFormatterEventSource`. Listener können bis zu 6 Ereignisse abonnieren.

### <a name="serializationstart-event-id--10"></a>SerializationStart-Ereignis (ID = `10`)

Wird ausgelöst, wenn <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> aufgerufen wurde und den Serialisierungsprozess gestartet hat. Dieses Ereignis ist mit dem `SerializationEnd`-Ereignis gekoppelt. Das `SerializationStart`-Ereignis kann rekursiv aufgerufen werden, wenn ein Objekt `BinaryFormatter.Serialize` in seiner eigenen Serialisierungsroutine aufruft.

Dieses Ereignis enthält keine Nutzdaten.

### <a name="serializationend-event-id--11"></a>SerializationEnd-Ereignis (ID = `11`)

Wird ausgelöst, wenn `BinaryFormatter.Serialize` seine Arbeit abgeschlossen hat. Jedes Vorkommen von `SerializationEnd` gibt den Abschluss des letzten ungekoppelten `SerializationStart`-Ereignisses an.

Dieses Ereignis enthält keine Nutzdaten.

### <a name="serializingobject-event-id--12"></a>SerializingObject-Ereignis (ID = `12`)

Wird ausgelöst, wenn `BinaryFormatter.Serialize` gerade einen nicht primitiven Typ serialisiert. Die `BinaryFormatter`-Infrastruktur behandelt bestimmte Typen (z. B. `string` und `int`) als Sonderfälle und löst dieses Ereignis nicht aus, wenn diese Typen gefunden werden. Dieses Ereignis wird für benutzerdefinierte Typen und andere Typen ausgelöst, die `BinaryFormatter` nicht nativ versteht.

Es kann sein, dass dieses Ereignis zwischen den Ereignissen `SerializationStart` und `SerializationEnd` nicht oder mehrmals ausgelöst wird.

Dieses Ereignis enthält eine Nutzlast mit einem Argument:

* `typeName` (`string`): Der Name mit Assemblyqualifikation (siehe <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) des Typs, der serialisiert wird.

### <a name="deserializationstart-event-id--20"></a>DeserializationStart-Ereignis (ID = `20`)

Wird ausgelöst, wenn <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> aufgerufen wurde und den Deserialisierungsprozess gestartet hat. Dieses Ereignis ist mit dem `DeserializationEnd`-Ereignis gekoppelt. Das `DeserializationStart`-Ereignis kann rekursiv aufgerufen werden, wenn ein Objekt `BinaryFormatter.Deserialize` in seiner eigenen Deserialisierungsroutine aufruft.

Dieses Ereignis enthält keine Nutzdaten.

### <a name="deserializationend-event-id--21"></a>DeserializationEnd-Ereignis (ID = `21`)

Wird ausgelöst, wenn `BinaryFormatter.Deserialize` seine Arbeit abgeschlossen hat. Jedes Vorkommen von `DeserializationEnd` gibt den Abschluss des letzten ungekoppelten `DeserializationStart`-Ereignisses an.

Dieses Ereignis enthält keine Nutzdaten.

### <a name="deserializingobject-event-id--22"></a>DeserializingObject-Ereignis (ID = `22`)

Wird ausgelöst, wenn `BinaryFormatter.Deserialize` gerade einen nicht primitiven Typ deserialisiert. Die `BinaryFormatter`-Infrastruktur behandelt bestimmte Typen (z. B. `string` und `int`) als Sonderfälle und löst dieses Ereignis nicht aus, wenn diese Typen gefunden werden. Dieses Ereignis wird für benutzerdefinierte Typen und andere Typen ausgelöst, die `BinaryFormatter` nicht nativ versteht.

Es kann sein, dass dieses Ereignis zwischen den Ereignissen `DeserializationStart` und `DeserializationEnd` nicht oder mehrmals ausgelöst wird.

Dieses Ereignis enthält eine Nutzlast mit einem Argument.

* `typeName` (`string`): Der Name mit Assemblyqualifikation (siehe <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) des Typs, der deserialisiert wird.

### <a name="advanced-subscribing-to-a-subset-of-notifications"></a>\[Erweitertes\] Abonnieren einer Teilmenge von Benachrichtigungen

Listener, die nur eine Teilmenge von Benachrichtigungen abonnieren möchten, können auswählen, welche Schlüsselwörter aktiviert werden sollen.

* `Serialization` = `(EventKeywords)1`: Löst die Ereignisse `SerializationStart`, `SerializationEnd` und `SerializingObject` aus.
* `Deserialization` = `(EventKeywords)2`: Löst die Ereignisse `DeserializationStart`, `DeserializationEnd` und `DeserializingObject` aus.

Wenn während der `EventListener`-Registrierung keine Schlüsselwortfilter bereitgestellt werden, werden alle Ereignisse ausgelöst.

Weitere Informationen finden Sie unter <xref:System.Diagnostics.Tracing.EventKeywords?displayProperty=nameWithType>.

## <a name="sample-code"></a>Beispielcode

Der folgende Code

- erstellt einen vom `EventListener` abgeleiteten Typ, der in die `System.Console` schreibt,
- abonniert diesen Listener für Benachrichtigungen, die der `BinaryFormatter` erstellt,
- serialisiert und deserialisiert einen einfachen Objektgraphen mit dem `BinaryFormatter` und
- analysiert die ausgelösten Ereignisse.

:::code language="csharp" source="snippets/binaryformatter-event-source/csharp/Program.cs":::

Der obige Code erzeugt eine Ausgabe, die folgendem Beispiel ähnelt:

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

In diesem Beispiel protokolliert der konsolenbasierte `EventListener`, dass die Serialisierung beginnt, Instanzen von `Person` und `Book` serialisiert werden und die Serialisierung abgeschlossen wird. Entsprechend werden Instanzen von `Person` und `Book` deserialisiert, sobald die Deserialisierung begonnen hat, und anschließend die Deserialisierung abgeschlossen.

Die App druckt dann die Werte, die im deserialisierten `Person` enthalten sind, um zu veranschaulichen, dass das Objekt tatsächlich ordnunsgemäß serialisiert und deserialisiert wurde.

## <a name="see-also"></a>Weitere Informationen

Weitere Informationen zur Verwendung des `EventListener` zum Empfang `EventSource`-basierter Benachrichtigungen finden Sie unter [`EventListener`-Klasse](xref:System.Diagnostics.Tracing.EventListener).
