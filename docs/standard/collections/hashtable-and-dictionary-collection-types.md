---
title: Hashtable-Auflistungstyp und Dictionary-Auflistungstyp
description: Hashtable-Auflistungstyp und Dictionary-Auflistungstyp
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 0f18fac7-fd0d-4f25-a046-1d3d51de062e
translationtype: Human Translation
ms.sourcegitcommit: e07788926a995b41571be276379ad9285747951d
ms.openlocfilehash: 373948733acc883a3fdc04d8dfc34f66435362af

---

# <a name="hashtable-and-dictionary-collection-types"></a>Hashtable-Auflistungstyp und Dictionary-Auflistungstyp

Die [System.Collections.Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable)-Klasse und die generischen Klassen [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) und [System.Collections.Concurrent.ConcurrentDictionary<T>](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2) implementieren die [System.Collections.IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)-Schnittstelle. Die generische Klasse `Dictionary<T>` implementiert außerdem die generische [IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2)-Schnittstelle. Daher ist jedes Element in diesen Auflistungen ein Schlüssel-Wert-Paar.

Ein `Hashtable`-Objekt besteht aus Buckets, die die Elemente der Auflistung enthalten. Ein Buckets ist eine virtuelle Untergruppe von Elementen innerhalb der `Hashtable`, der das Suchen und Abrufen schneller und einfacher als in den meisten Auflistungen ermöglicht. Jedem Bucket ist ein Hashcode zugeordnet, der mithilfe einer Hashfunktion generiert wird und auf dem Schlüssel des Elements basiert.

Die generische Klasse [HashSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.HashSet-1) ist eine ungeordnete Auflistung für eindeutige Elemente. 

Eine Hashfunktion ist ein Algorithmus, der einen numerischen Hashcode anhand eines Schlüssels zurückgibt. Der Schlüssel ist der Wert einer Eigenschaft des Objekts, das gespeichert wird. Eine Hashfunktion muss immer denselben Hashcode für denselben Schlüssel zurückgeben. Es ist möglich, dass eine Hashfunktion, den gleichen Hashcode für zwei verschiedene Schlüssel generiert. Eine Hashfunktion, die einen eindeutigen Hashcode für jeden eindeutigen Schlüssel generiert, führt jedoch zu besserer Leistung beim Abrufen von Elementen aus der Hashtabelle.

Jedes Objekt, das als ein Element in einer `Hashtable` verwendet wird, muss in der Lage sein, einen Hashcode für sich selbst zu generieren, indem eine Implementierung der Methode `GetHashCode` verwendet wird. 

Wenn ein Objekt einer `Hashtable` hinzugefügt wird, wird es in dem Bucket gespeichert, der dem Hashcode zugeordnet ist, der mit dem Hashcode des Objekts übereinstimmt. Wenn in der `Hashtable` nach einem Wert gesucht wird, wird der Hashcode für diesen Wert generiert, dann wird der diesem Hashcode zugeordnete Bucket durchsucht.

Eine Hashfunktion für eine Zeichenfolge kann z. B. die ASCII-Codes jedes Zeichens in der Zeichenfolge annehmen und sie dann zusammen hinzufügen, um einen Hashcode zu generieren. Die Zeichenfolge "Segel" besitzt z. B. einen anderen Hashcode als die Zeichenfolge "Seife". Daher werden die Zeichenfolgen "Segel" und "Seife" in verschiedenen Buckets gespeichert. Im Gegensatz dazu weisen "nie" und "ein" den gleichen Hashcode auf und befinden sich im gleichen Bucket.

Die Klassen `Dictionary<T>` und `ConcurrentDictionary<T>` weisen die gleiche Funktionalität wie die Klasse `Hashtable` auf. Ein `Dictionary<T>` eines bestimmten Typs (außer `Object`) bietet eine bessere Leistung als eine `Hashtable` für Werttypen. Der Grund hierfür ist, dass die Elemente von `Hashtable` vom Typ `Object` sind. Daher treten das Boxing und das Unboxing in der Regel beim Speichern oder Abrufen eines Werttyps auf. Die Klasse `ConcurrentDictionary<T>` sollte verwendet werden, wenn mehrere Threads möglicherweise gleichzeitig auf die Auflistung zugreifen.

## <a name="see-also"></a>Siehe auch

[Hashtabelle](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable)

[IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)

[Dictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2)

[System.Collections.Generic.IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2)

[System.Collections.Concurrent.ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2)

[Häufig verwendete Sammlungstypen](commonly-used-collection-types.md)




<!--HONumber=Nov16_HO3-->


