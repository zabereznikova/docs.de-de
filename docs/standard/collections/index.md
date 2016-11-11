---
title: Auflistungen und Datenstrukturen
description: Auflistungen und Datenstrukturen
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 9e70255a-c02a-4046-86b7-10c84bab2d38
translationtype: Human Translation
ms.sourcegitcommit: cfe65fcba1b3fdc09ffcac704a760d8ce29ea60b
ms.openlocfilehash: 3f2831f21654d9eb1523cd80166b674e7c41d8bb

---

# <a name="collections-and-data-structures"></a>Auflistungen und Datenstrukturen

Ähnliche Daten können häufig effizienter verarbeitet werden, wenn sie als eine Auflistung gespeichert und bearbeitet werden. Sie können die [System.Array](https://docs.microsoft.com/dotnet/core/api/System.Array)-Klasse oder die Klassen in den Namespaces [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections), [System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic) oder [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent) verwenden, um einzelne Elemente oder einen Elementbereich zu einer Auflistung hinzuzufügen, darin zu ändern oder daraus zu entfernen.

Es gibt zwei Grundarten von Auflistungen: generische Auflistungen und nicht generische Auflistungen. Generische Auflistungen sind beim Kompilieren typsicher. Aus diesem Grund bieten generische Auflistungen in der Regel eine bessere Leistung. Generische Auflistungen akzeptieren beim Erstellen einen Typparameter und erfordern keine Umwandlung in den und aus dem [Object](https://docs.microsoft.com/dotnet/core/api/System.Object)-Typ, wenn Sie Elemente zur Auflistung hinzufügen oder daraus entfernen. Nicht generische Auflistungen speichern Elemente als [Object](https://docs.microsoft.com/dotnet/core/api/System.Object) und erfordern eine Umwandlung. In älterem Code finden sich möglicherweise noch nicht generische Auflistungen.

Die Auflistungen im [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)-Namespace stellen effiziente threadsichere Vorgänge für den Zugriff auf Auflistungselemente aus mehreren Threads bereit.

## <a name="common-collection-features"></a>Allgemeine Auflistungsfunktionen

Alle Auflistungen bieten Methoden zum Hinzufügen, Entfernen oder Suchen von Elementen in der Auflistung. Darüber hinaus teilen sich alle Auflistungen, die die [ICollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.ICollection)-Schnittstelle oder die [ICollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.ICollection-1)-Schnittstelle direkt oder indirekt implementieren, diese Funktionen: 

* **Die Fähigkeit zum Enumerieren der Auflistung**

   .NET Framework-Auflistungen implementieren entweder [System.Collections.IEnumerable](https://docs.microsoft.com/dotnet/core/api/System.Collections.IEnumerable) oder [System.Collections.Generic.IEnumerable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1),damit die Auflistung durchlaufen werden kann. Ein Enumerator kann als beweglicher Zeiger auf ein Element in der Auflistung betrachtet werden. Die Anweisung `foreach, in` (C#) verwendet den Enumerator, der von der `GetEnumerator`-Methode verfügbar gemacht wird, und verbirgt die Komplexität der Bearbeitung des Enumerators. Darüber hinaus gilt jede Auflistung, die [System.Collections.Generic.IEnumerable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1) implementiert, als abfragbarer Typ und kann mit LINQ abgefragt werden. LINQ-Abfragen bieten ein allgemeines Muster für den Datenzugriff. Sie sind normalerweise präziser und besser lesbar als standardmäßige foreach-Schleifen und bieten Filter-, Sortier- und Gruppierungsfunktionen. LINQ-Abfragen können auch die Leistung verbessern.
    
* **Die Möglichkeit, den Inhalt der Auflistung in ein Array zu kopieren**

   Alle Auflistungen können mit der `CopyTo`-Methode in ein Array kopiert werden. Die Reihenfolge der Elemente im neuen Array basiert jedoch auf der Reihenfolge, in der sie vom Enumerator zurückgegeben werden. Das resultierende Array ist stets eindimensional mit einer unteren Grenze von 0 (Null).
    
Viele Auflistungsklassen enthalten außerdem die folgenden Funktionen:

* **Kapazität und Zähleigenschaften**

   Die Kapazität einer Auflistung ist die Anzahl der Elemente, die sie enthalten kann. Die Anzahl einer Auflistung ist die Anzahl der tatsächlich enthaltenen Elemente. Einige Auflistungen blenden die Kapazität oder die Anzahl oder beides aus.
    
   Die meisten Auflistungen erweitern ihre Kapazität automatisch, wenn die aktuelle Kapazität erreicht ist. Der Speicher wird neu zugewiesen, und die Elemente werden aus der alten Auflistung in die neue kopiert. Dies reduziert den Code, der für die Verwendung der Auflistung erforderlich ist. Die Leistung der Auflistung kann dadurch allerdings beeinträchtigt werden. Beispiel für [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1): Wenn `Count` kleiner als `Capacity` ist, ist das Hinzufügen eines Elements ein O(1)-Vorgang. Wenn die Kapazität für das neue Element erhöht werden muss, ist das Hinzufügen eines Elements ein O(n)-Vorgang, wobei n `Count` ist. Am besten vermeiden Sie Leistungsverluste aufgrund mehrerer Neuzuweisungen, indem Sie die anfängliche Kapazität als geschätzte Größe der Auflistung festlegen. 
    
   Ein [BitArray](https://docs.microsoft.com/dotnet/core/api/System.Collections.BitArray) ist ein Sonderfall: Die Kapazität ist identisch mit der Länge, die wiederum mit der Anzahl übereinstimmt.
    
*   **Eine konsistente Untergrenze**

   Die untere Grenze einer Auflistung ist der Index des ersten darin enthaltenen Elements. Alle indizierten Auflistungen in den [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)-Namespaces haben eine untere Grenze von Null, d.h. sie sind 0-indiziert. [Array](https://docs.microsoft.com/dotnet/core/api/System.Array) hat standardmäßig eine untere Grenze von Null. Es kann jedoch eine andere Untergrenze definiert werden, wenn Sie eine Instanz der `Array`-Klasse mit `Array.CreateInstance` erstellen.

*   **Synchronisierung für den Zugriff aus mehreren Threads** (nur [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)-Klassen).

   Nicht generische Auflistungstypen im [System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)-Namespace bieten durch Synchronisierung ein gewisses Maß an Threadsicherheit. In der Regel werden sie durch die Member `SyncRoot` und `IsSynchronized` verfügbar gemacht. Diese Auflistungen sind nicht standardmäßig Thread-sicher. Wenn Sie skalierbaren und effizienten Multithreadzugriff auf eine Auflistung benötigen, verwenden Sie eine der Klassen im [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)-Namespace, oder ziehen Sie den Einsatz einer unveränderlichen Auflistung in Erwägung. Weitere Informationen finden Sie unter [Threadsichere Auflistungen](threadsafe/index.md).    
    
## <a name="choosing-a-collection"></a>Auswählen einer Auflistung 

Im Allgemeinen sollten Sie generische Auflistungen verwenden. Die folgende Tabelle beschreibt einige häufig auftretende Auflistungsszenarios sowie die Auflistungsklassen, die Sie für diese Szenarien verwenden können. Wenn Sie sich mit der Arbeit mit generischen Auflistungen noch nicht auskennen, hilft Ihnen diese Tabelle bei der Auswahl der generischen Auflistung, die am besten für Ihre Aufgabe geeignet ist.

Ziel | Optionen für generische Auflistungen | Optionen für nicht generische Auflistungen
---------- | ---------------------------- | --------------------------------
Speichern von Elementen als Schlüssel-Wert-Paare für die schnelle Suche nach Schlüssel | [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) | [Hashtabelle](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable)
Zugriff auf die Elemente nach Index | [System.Collections.Generic.List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) | [System.Array](https://docs.microsoft.com/dotnet/core/api/System.Array), [System.Collections.ArrayList](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList)
Verwenden von Elementen nach First-in-First-Out (FIFO)-Prinzip | [System.Collections.Generic.Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1) | [System.Collections.Queue](https://docs.microsoft.com/dotnet/core/api/System.Collections.Queue)
Verwenden von Daten nach Last-In-First-Out (LIFO)-Prinzip | [System.Collections.Generic.Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1) | [System.Collections.Stack](https://docs.microsoft.com/dotnet/core/api/System.Collections.Stack)
Zugriff auf Elemente in Reihenfolge | [System.Collections.Generic.LinkedList&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.LinkedList-1) | Keine Empfehlung
Empfang von Benachrichtigungen, wenn Elemente der Auflistung hinzugefügt oder aus ihr entfernt werden. (implementiert [INotifyPropertyChanged](https://docs.microsoft.com/dotnet/core/api/System.ComponentModel.INotifyPropertyChanged) und [INotifyCollectionChanged](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.INotifyCollectionChanged)) | [System.Collections.ObjectModel.ObservableCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.ObservableCollection-1) | Keine Empfehlung
Verwenden einer sortierten Auflistung | [System.Collections.Generic.SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) | [System.Collections.SortedList](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList)
Verwalten eines effizienten Speichers und Zugriff auf eindeutige Elemente | [System.Collections.Generic.HashSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.HashSet-1), [System.Collections.Generic.SortedSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedSet-1) | Keine Empfehlung

## <a name="related-topics"></a>Verwandte Themen

Titel | Beschreibung
----- | -----------
[Auswählen einer Auflistungsklasse](selecting-a-collection-class.md) | Beschreibt die verschiedenen Auflistungen und hilft Ihnen bei der Auswahl für Ihr Szenario.
[Häufig verwendete Auflistungstypen](commonly-used-collection-types.md) | Beschreibt häufig verwendete generische und nicht generische Auflistungstypen wie z.B. [System.Array](https://docs.microsoft.com/dotnet/core/api/System.Array), [System.Collections.Generic.List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) und [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2). 
[Verwenden von generischen Auflistungen](when-to-use-generic-collections.md) | Erörtert die Verwendung generischer Auflistungstypen.
[Vergleiche und Sortierungen innerhalb von Auflistungen](comparisons-and-sorts-within-collections.md) | Erläutert die Verwendung von Übereinstimmungs- und Sortiervergleichen in Auflistungen.
[Sortierte Auflistungstypen](sorted-collection-types.md) | Beschreibt die Leistung und die Merkmale von sortierten Auflistungen.
[Hashtable-Auflistungstyp und Dictionary-Auflistungstyp](hashtable-and-dictionary-collection-types.md) | Beschreibt die Funktionen von generischen und nicht generischen hashbasierten Wörterbuchtypen.
[threadsichere Auflistungen](threadsafe/index.md) | Beschreibt Auflistungstypen wie [System.Collections.Concurrent.BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) und [System.Collections.Concurrent.ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1), die einen sicheren und effizienten gleichzeitigen Zugriff aus mehreren Threads unterstützen.

## <a name="reference"></a>Verweis

[System.Array](https://docs.microsoft.com/dotnet/core/api/System.Array)

[System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic)

[System.Collections.Specialized](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized)

[System.Linq](https://docs.microsoft.com/dotnet/core/api/System.Linq)
  



<!--HONumber=Nov16_HO1-->


