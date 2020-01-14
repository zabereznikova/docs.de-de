---
title: Sortierte Sammlungstypen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- SortedDictionary collection type
- SortedList class, grouping data in collections
- grouping data in collections, SortedList collection type
- SortedList collection type
- collections [.NET Framework], SortedList collection type
ms.assetid: 3db965b2-36a6-4b12-b76e-7f074ff7275a
ms.openlocfilehash: adabda4801abc7a11a9b22181701eb233b35a251
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711336"
---
# <a name="sorted-collection-types"></a>Sortierte Sammlungstypen
Die <xref:System.Collections.SortedList?displayProperty=nameWithType>-Klasse, die generische <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType>-Klasse sowie die generische <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType>-Klasse sind der <xref:System.Collections.Hashtable>-Klasse und der generischen <xref:System.Collections.Generic.Dictionary%602>-Klasse in der Weise ähnlich, dass sie die <xref:System.Collections.IDictionary>-Schnittstelle implementieren. Sie behalten jedoch ihre Elemente in der Reihenfolge nach Schlüssel bei, und sie verfügen nicht über die O(1)-Einfüge- und -Abrufeigenschaften von Hashtabellen. Die drei Klassen haben verschiedene Merkmale gemeinsam:  
  
- Alle drei Klassen implementieren die <xref:System.Collections.IDictionary?displayProperty=nameWithType>-Schnittstelle. Die zwei generischen Klassen implementieren außerdem die generische <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>-Schnittstelle.  
  
- Jedes Element ist ein Schlüssel-Wert-Paar zu Enumerationszwecken.  
  
    > [!NOTE]
    > Die nicht-generische <xref:System.Collections.SortedList>-Klasse gibt bei einer Enumeration <xref:System.Collections.DictionaryEntry>-Objekte zurück, obwohl zwei generische Typen <xref:System.Collections.Generic.KeyValuePair%602>-Objekte zurückgeben.  
  
- Elemente werden nach einer <xref:System.Collections.IComparer?displayProperty=nameWithType>-Implementierung (für nicht-generische <xref:System.Collections.SortedList>) oder einer <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType>-Implementierung (für die zwei generischen Klassen) sortiert.  
  
- Jede Klasse enthält Eigenschaften, die Sammlungen zurückgeben, die nur die Schlüssel oder nur die Werte enthalten.  
  
 Die folgende Tabelle enthält einige Unterschiede zwischen den beiden SortedList-Klassen und der <xref:System.Collections.Generic.SortedDictionary%602>-Klasse.  
  
|Nicht generische <xref:System.Collections.SortedList>-Klasse und generische <xref:System.Collections.Generic.SortedList%602>-Klasse|Generische <xref:System.Collections.Generic.SortedDictionary%602>-Klasse|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|Die Eigenschaften, die Schlüssel und Werte zurückgeben, werden indiziert, um einen effizienten Abruf zu ermöglichen.|Kein indizierter Abruf.|  
|Der Abruf erfolgt über O(log `n`).|Der Abruf erfolgt über O(log `n`).|  
|Das Einfügen und Entfernen erfolgt im Allgemeinen über „O(`n`)“. Das Einfügen erfolgt jedoch über „O(log `n`)“ für Daten, die bereits in der Sortierreihenfolge vorliegen, sodass jedes Element am Ende der Liste hinzugefügt wird. (Dies setzt voraus, dass keine Größenänderung erforderlich ist.)|Einfügen und Entfernen erfolgen über „O(log `n`)“.|  
|Benötigt weniger Speicher als <xref:System.Collections.Generic.SortedDictionary%602>.|Benötigt mehr Arbeitsspeicher als die nicht generische Klasse <xref:System.Collections.SortedList> und die generische Klasse <xref:System.Collections.Generic.SortedList%602>.|  
  
 Für sortierte Listen oder Wörterbücher, die gleichzeitig für mehrere Threads zugänglich sein müssen, können Sie einer Klasse Sortierlogik hinzufügen, die von <xref:System.Collections.Concurrent.ConcurrentDictionary%602> abgeleitet wird.  
  
> [!NOTE]
> Für Werte, die ihre eigenen Schlüssel enthalten (z.B. Mitarbeiterdatensätze mit einer Mitarbeiter-ID), können Sie durch Ableiten von der generischen Klasse <xref:System.Collections.ObjectModel.KeyedCollection%602> eine schlüsselgebundene Sammlung erstellen, die einige Merkmale einer Liste und einige Merkmale eines Wörterbuchs aufweist.  
  
 Ab .NET Framework 4 stellt die Klasse <xref:System.Collections.Generic.SortedSet%601> eine selbstausgleichende Struktur bereit, in der Daten nach Einfüge-, Lösch- und Suchvorgängen in sortierter Reihenfolge verwaltet werden. Diese Klasse sowie die <xref:System.Collections.Generic.HashSet%601>-Klasse implementieren die <xref:System.Collections.Generic.ISet%601>-Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.IDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.ConcurrentDictionary%602>
- [Häufig verwendete Auflistungstypen](../../../docs/standard/collections/commonly-used-collection-types.md)
