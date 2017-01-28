---
title: Sortierte Auflistungstypen
description: Sortierte Auflistungstypen
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bdc9c13e-e56a-433b-a293-c92364f6e9cb
translationtype: Human Translation
ms.sourcegitcommit: 149086110d7470d97e1ab3e5969269626290b523
ms.openlocfilehash: 4359ec4c55921497f32d5891ea337a30867e4fa5

---

# <a name="sorted-collection-types"></a>Sortierte Auflistungstypen  
 
 Die Klasse [System.Collections.SortedList](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList), die generische Klasse [System.Collections.Generic.SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) und die generische Klasse [System.Collections.Generic.SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) ähneln der [Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable)-Klasse und der generischen Klasse [Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) insofern, als dass sie die [IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)-Schnittstelle implementieren. Sie verwalten jedoch ihre Elemente in der Sortierreihenfolge nach Schlüssel, und sie verfügen nicht über die O(1)-Einfüge- und -Abrufeigenschaft von Hashtabellen. Die drei Klassen haben verschiedene Merkmale gemeinsam:  

 *   Alle drei Klassen implementieren die [System.Collections.IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)-Schnittstelle. Die beiden generischen Klassen implementieren außerdem die generische Schnittstelle [System.Collections.Generic.IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2).  
 
 *   Jedes Element ist ein Schlüssel-Wert-Paar zu Enumerationszwecken.   
  
> [!NOTE]  
> Die nicht generische [SortedList](https://docs.microsoft.com/dotnet/core/api/System.Collections.SortedList)-Klasse gibt bei der Enumeration [DictionaryEntry](https://docs.microsoft.com/dotnet/core/api/System.Collections.DictionaryEntry)-Objekte zurück, obwohl die beiden generischen Typen [KeyValuePair&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.KeyValuePair-2)-Objekte zurückgeben.  
   
*   Elemente werden entsprechend einer [System.Collections.IComparer](https://docs.microsoft.com/dotnet/core/api/System.Collections.IComparer)-Implementierung (für eine nicht generische `SortedList`-Klasse) oder einer [System.Collections.Generic.IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1)-Implementierung (für die beiden generischen Klassen) sortiert.  
   
 *   Jede Klasse enthält Eigenschaften, die Sammlungen zurückgeben, die nur die Schlüssel oder nur die Werte enthalten.  
   
Die folgende Tabelle enthält einige Unterschiede zwischen den beiden SortedList-Klassen und der [SortedDictionary<TKey, TValue>](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2)-Klasse.  
   
 Nicht generische `SortedList`-Klasse und generische `SortedList<TKey, TValue>`-Klasse | Generische `SortedDictionary<TKey, TValue>`-Klasse  
 --------------------------------------------------------------------------------- | ------------------------------  
 Die Eigenschaften, die Schlüssel und Werte zurückgeben, werden indiziert, um einen effizienten Abruf zu ermöglichen. | Kein indizierter Abruf.  
 Abruf erfolgt über „O(log n)“. | Abruf erfolgt über „O(log n)“.  
 Das Einfügen und Entfernen erfolgen im Allgemeinen über „O(n)“. Das Einfügen erfolgt jedoch über „O(1)“ für Daten, die bereits in der Sortierreihenfolge vorliegen, sodass jedes Element am Ende der Liste hinzugefügt wird. (Dies setzt voraus, dass keine Größenänderung erforderlich ist.) | Einfügen und Entfernen erfolgen über „O(log n)“.  
 Benötigt weniger Speicher als `SortedDictionary<TKey, TValue>`. | Benötigt mehr Arbeitsspeicher als die nicht generische Klasse `SortedList` und die generische Klasse `SortedList<TKey, TValue>`.  
  
 Für sortierte Listen oder Wörterbücher, die gleichzeitig für mehrere Threads zugänglich sein müssen, können Sie einer Klasse Sortierlogik hinzufügen, die von [ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2) abgeleitet wird.  
  
 > [!NOTE]  
 > Für Werte, die ihre eigenen Schlüssel enthalten (z.B. Mitarbeiterdatensätze mit einer Mitarbeiter-ID), können Sie durch Ableiten von der generischen Klasse [KeyedCollection&lt;TKey, TItem&gt;]() eine schlüsselgebundene Sammlung erstellen, die einige Merkmale einer Liste und einige Merkmale eines Wörterbuchs aufweist.  
   
 Die Klasse [SortedSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedSet-1) stellt eine selbstausgleichende Struktur bereit, in der Daten nach Einfüge-, Lösch- und Suchvorgängen in sortierter Reihenfolge verwaltet werden. Diese Klasse und die Klasse [HashSet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.HashSet-1) implementieren die [ISet&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.ISet-1)-Schnittstelle.  
   
## <a name="see-also"></a>Siehe auch  
  
[System.Collections.IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)  
   
[System.Collections.Generic.IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2)  
   
[ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2)  
 
[Häufig verwendete Sammlungstypen](commonly-used-collection-types.md) 



<!--HONumber=Nov16_HO3-->


