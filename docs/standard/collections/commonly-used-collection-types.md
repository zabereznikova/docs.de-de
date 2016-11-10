---
title: "Häufig verwendete Auflistungstypen"
description: "Häufig verwendete Auflistungstypen"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 55861611-1e40-4cc2-9ec5-0b2df4ba6c0c
translationtype: Human Translation
ms.sourcegitcommit: d4e7ef84480aa9f735fb8d1ff03c9e8a61127c83
ms.openlocfilehash: 063e43b156771ba0db7c6b8ef5823330a4405c2c

---

# <a name="commonly-used-collection-types"></a>Häufig verwendete Auflistungstypen

Auflistungstypen sind die allgemeinen Variationen von Datenauflistungen, z. B. Hashtabellen, Warteschlangen, Stapel, Sammlungen, Wörterbücher und Listen.

Auflistungen basieren auf der [`ICollection`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ICollection)-Schnittstelle, der [`IList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IList)-Schnittstelle, der [`IDictionary`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)-Schnittstelle oder auf ihren generischen Entsprechungen. Die `IList`-Schnittstelle und die `IDictionary`-Schnittstelle leiten sich beide aus der `ICollection`-Schnittstelle ab. Daher basieren alle Auflistungen direkt oder indirekt auf der `ICollection`-Schnittstelle. In Auflistungen, die auf der `IList`-Schnittstelle basieren (z.B. [`Array`](https://docs.microsoft.com/dotnet/core/api/System.Array), [`ArrayList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList) oder [`List<T>)`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1)), bzw. direkt auf der `ICollection`-Schnittstelle (z.B. [`Queue`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Queue), [`ConcurrentQueue<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1), [`Stack`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Stack), [`ConcurrentStack<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) oder [`LinkedList<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.LinkedList-1)), enthält jedes Element nur einen Wert. In Auflistungen, die auf der `IDictionary`-Schnittstelle basieren (zum Beispiel die Klassen [`Hashtable`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) und [`SortedList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList), die generischen Klassen [`Dictionary<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) und [`SortedList<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2)), oder die auf den [`ConcurrentDictionary<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2)-Klassen basieren, enthält jedes Element einen Schlüssel und einen Wert. Die [`KeyedCollection<TKey, TItem>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2)-Klasse ist eindeutig, da sie eine Liste von Werten mit Schlüsseln darstellt, die in den Werten eingebettet sind. Deshalb verhält sie sich wie eine Liste und wie ein Wörterbuch.

Generische Auflistungen sind die beste Lösung für eine starke Typisierung. Wenn Ihre Sprache allerdings keine generischen Auflistungen unterstützt, enthält der [`System.Collections`](https://docs.microsoft.com/dotnet/core/api/System.Collections)-Namespace Basisauflistungen, z.B. [`CollectionBase`](https://docs.microsoft.com/dotnet/core/api/System.Collections.CollectionBase), [`ReadOnlyCollectionBase`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ReadOnlyCollectionBase) und [`DictionaryBase`](https://docs.microsoft.com/dotnet/core/api/System.Collections.DictionaryBase). Dabei handelt es sich um abstrakte Basisklassen, die erweitert werden können, um Auflistungsklassen zu erstellen, die stark typisiert sind. Wenn effizienter Zugriff auf Multithreadauflistungen erforderlich ist, verwenden Sie die generischen Auflistungen im [`System.Collections.Concurrent`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)-Namespace.

Auflistungen können variieren, je nachdem, wie die Elemente gespeichert werden, wie sie sortiert werden, wie Suchvorgänge ausgeführt werden und wie Vergleiche vorgenommen werden. Die [`Queue`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Queue)-Klasse und die generische [`Queue<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1)-Klasse stellen First-in-First-Out-Listen bereit, während die [`Stack`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Stack)-Klasse und die generische [`Stack<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1)-Klasse Last-in-First-Out-Listen bereitstellen. Die [`SortedList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList)-Klasse und die generische [`SortedList<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2)-Klasse stellen sortierte Versionen der [`Hashtable`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable)-Klasse und der generischen [`Dictionary<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2)-Klasse bereit. Der Zugriff auf die Elemente einer `Hashtable` oder `Dictionary<TKey, TValue>` ist nur über den Schlüssel des Elements möglich, aber der Zugriff auf Elemente einer `SortedList` oder [`KeyedCollection<TKey, TItem>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2) ist über den Schlüssel oder den Index des Elements möglich. Die Indizes in allen Auflistungen sind nullbasiert, mit Ausnahme von [`Array`](https://docs.microsoft.com/dotnet/core/api/System.Array), wodurch auch Arrays, die nicht nullbasiert sind, zulässig sind.

Mit der LINQ to Objects-Funktion können Sie LINQ-Abfragen für den Zugriff auf Objekte im Arbeitsspeicher verwenden, solange der Objekttyp [`IEnumerable`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IEnumerable) oder [`IEnumerable<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1) implementiert. LINQ-Abfragen bieten ein allgemeines Muster für den Datenzugriff, sind normalerweise präziser und besser lesbar als standardmäßige Foreach-Schleifen und stellen Filter-, Sortier- und Gruppierungsfunktionen bereit. LINQ-Abfragen können auch die Leistung verbessern.

## <a name="related-topics"></a>Verwandte Themen

Titel | Beschreibung
----- | -----------
[`Collections and Data Structures`](index.md) | Erläutert die unterschiedlichen Auflistungstypen, die in .NET Framework verfügbar sind, z.B. Stapel, Warteschlangen, Listen, Arrays und Wörterbücher.
[`Hashtable and Dictionary Collection Types`](hashtable-and-dictionary-collection-types.md) | Beschreibt die Funktionen von generischen und nicht generischen hashbasierten Wörterbuchtypen.
[`Sorted Collection Types`](sorted-collection-types.md) | Beschreibt die Leistung und die Merkmale von sortierten Auflistungen.

## <a name="reference"></a>Verweis

[`System.Collections`](https://docs.microsoft.com/dotnet/core/api/System.Collections)

[`System.Collections.Generic`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic)

[`System.Collections.ICollection`](https://docs.microsoft.com/dotnet/core/api/System.Collections.ICollection)

[`System.Collections.Generic.ICollection<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.ICollection-1)

[`System.Collections.IList`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IList)

[`System.Collections.Generic.IList<T>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IList-1)

[`System.Collections.IDictionary`](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)

[`System.Collections.Generic.IDictionary<TKey, TValue>`](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2)

[`System.Linq`](https://docs.microsoft.com/dotnet/core/api/System.Linq)



<!--HONumber=Nov16_HO1-->


