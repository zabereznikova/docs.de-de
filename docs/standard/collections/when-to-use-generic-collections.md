---
title: Verwenden von generischen Auflistungen
description: Verwenden von generischen Auflistungen
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 971e08bd-b63f-4832-9e61-9f65cbedd352
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: bde317c165981775330e1d0d8261d355e2401bc9
ms.lasthandoff: 03/03/2017

---

# <a name="when-to-use-generic-collections"></a>Verwenden von generischen Auflistungen

Das Verwenden von generischen Auflistungen wird generell empfohlen, da Sie den unmittelbaren Vorteil die Typsicherheit erhalten, ohne von einem Basisauflistungstyp abweichen und typenspezifische Member implementieren zu müssen. Generische Auflistungstypen bieten allgemein auch eine bessere Leistung als die entsprechenden nicht generischen Auflistungstypen (und besser als Typen, die von nicht generischen Basisauflistungstypen abgeleitet sind), wenn die Auflistungselemente Werttypen sind, da bei generischen Typen keine Notwendigkeit zum Einschließen der Elemente besteht. 

Sie sollten die generischen Sammlungsklassen im [System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)-Namespace verwenden, wenn mehrere Threads möglicherweise Elemente gleichzeitig der Sammlung hinzufügen oder daraus entfernen.

Die folgenden generischen Typen entsprechen vorhandenen Auflistungstypen: 

*   [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) ist die generische Klasse, die [ArrayList](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList) entspricht.

*   [Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) und [ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2) sind die generischen Klassen, die [Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable) entsprechen. 

*   [Collection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.Collection-1) ist die generische Klasse, die [CollectionBase](https://docs.microsoft.com/dotnet/core/api/System.Collections.CollectionBase) entspricht. `Collection<T>` kann als Basisklasse verwendet werden, ist aber im Gegensatz zu `CollectionBase` nicht abstrakt. Dadurch kann sie viel einfacher verwendet werden.

*   [ReadOnlyCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.ReadOnlyCollection-1) ist die generische Klasse, die [ReadOnlyCollectionBase](https://docs.microsoft.com/dotnet/core/api/System.Collections.ReadOnlyCollectionBase) entspricht. `ReadOnlyCollection<T>` ist nicht abstrakt und verfügt über einen Konstruktor, der es einfach macht, eine vorhandene [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) als schreibgeschützte Sammlung verfügbar zu machen.

*   Die generischen Klassen [Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1), [ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1), [Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1), [ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) und [SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) entsprechen den jeweiligen nicht generischen Klassen mit dem gleichen Namen.

## <a name="additional-types"></a>Zusätzliche Typen

Einige generische Auflistungstypen haben keine nicht generischen Entsprechungen. Hierzu gehören Folgende: 

*   [LinkedList&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.LinkedList-1) ist eine vielfältig einsetzbare verknüpfte Liste, die O(1)-Einfüge- und Löschvorgänge bereitstellt.

*   [SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) ist ein sortiertes Wörterbuch mit O(log n)-Einfüge- und Abrufvorgängen – eine nützliche Alternative zu [SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2). 

*   [KeyedCollection&lt;TKey, TItem&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2) ist eine Mischung aus Liste und Wörterbuch und bietet eine Möglichkeit, Objekte zu speichern, die ihre eigenen Schlüssel enthalten.

*   [BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) implementiert eine Sammlungsklasse mit Begrenzungs- und Blockadefunktionen.

*   [ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1) ermöglicht das schnelle Einfügen und Entfernen unsortierter Elemente.

## <a name="linq-to-objects"></a>LINQ to Objects

Mit der LINQ to Objects-Funktion können Sie LINQ-Abfragen für den Zugriff auf Objekte im Arbeitsspeicher verwenden, sofern der Objekttyp die [System.Collections.IEnumerable](https://docs.microsoft.com/dotnet/core/api/System.Collections.IEnumerable)- oder die [System.Collections.Generic.IEnumerable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1)-Schnittstelle implementiert. LINQ-Abfragen bieten ein allgemeines Muster für den Datenzugriff, sind normalerweise präziser und besser lesbar als standardmäßige `foreach`-Schleifen und stellen Filter-, Sortier- und Gruppierungsfunktionen bereit. LINQ-Abfragen können auch die Leistung verbessern.

## <a name="additional-functionality"></a>Zusätzliche Funktionen

Einige der generischen Typen besitzen Funktionen, die es in den nicht generischen Auflistungstypen nicht gibt. Die [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1)-Klasse, die der nicht generischen [ArrayList](https://docs.microsoft.com/dotnet/core/api/System.Collections.ArrayList)-Klasse entspricht, hat z.B. eine Reihe von Methoden, die generische Delegaten akzeptieren, z.B. den [Predicate&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Predicate-1)-Delegaten, mit dem Sie Methoden zum Durchsuchen der Liste angeben können, und den [Action&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Action-1)-Delegaten, der Methoden für die einzelnen Listenelemente darstellt.

Mit der [List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1)-Klasse können Sie Ihre eigenen generischen [IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1)-Schnittstellenimplementierungen zum Sortieren und Durchsuchen der Liste angeben. Die Klassen [SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) und [SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) verfügen ebenfalls über diese Funktion. Darüber hinaus ermöglichen Ihnen diese Klassen das Angeben von Vergleichen beim Erstellen der Auflistung. In ähnlicher Weise können Sie mit den Klassen [Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) und [KeyedCollection&lt;TKey, TItem&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2) eigene Gleichheitsvergleiche angeben.

## <a name="see-also"></a>Siehe auch

[Sammlungen und Datenstrukturen](index.md) 

[Häufig verwendete Sammlungstypen](commonly-used-collection-types.md)

