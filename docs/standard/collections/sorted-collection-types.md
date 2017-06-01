---
title: Sortierte Sammlungstypen | Microsoft-Dokumentation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SortedDictionary collection type
- SortedList class, grouping data in collections
- grouping data in collections, SortedList collection type
- SortedList collection type
- collections [.NET Framework], SortedList collection type
ms.assetid: 3db965b2-36a6-4b12-b76e-7f074ff7275a
caps.latest.revision: 16
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2ac1552dba8756d033ee02651142476c4a15a485
ms.lasthandoff: 04/18/2017

---
# <a name="sorted-collection-types"></a>Sortierte Sammlungstypen
Die Klasse <xref:System.Collections.SortedList?displayProperty=fullName>, die generische Klasse <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> und die generische Klasse <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> ähneln der generischen Klasse <xref:System.Collections.Hashtable> und der generischen Klasse <xref:System.Collections.Generic.Dictionary%602> insofern, als sie die <xref:System.Collections.IDictionary>-Schnittstelle implementieren, sie behalten jedoch die Sortierreihenfolge ihrer Elemente nach Schlüssel bei und weisen nicht die O(1)-Einfüge- und Entnahmemerkmale von Hashtabellen auf. Die drei Klassen haben verschiedene Merkmale gemeinsam:  
  
-   Alle drei Klassen implementieren die <xref:System.Collections.IDictionary?displayProperty=fullName>-Schnittstelle. Die zwei generischen Klassen implementieren darüber hinaus die generische Schnittstelle <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>.  
  
-   Jedes Element ist ein Schlüssel-Wert-Paar zu Enumerationszwecken.  
  
    > [!NOTE]
    >  Die nicht generische Klasse <xref:System.Collections.SortedList> gibt bei der Enumerierung <xref:System.Collections.DictionaryEntry>-Objekte zurück, hingegeben geben die zwei generischen Typen <xref:System.Collections.Generic.KeyValuePair%602>-Objekte zurück.  
  
-   Elemente werden gemäß einer <xref:System.Collections.IComparer?displayProperty=fullName>-Implementierung (für nicht generische <xref:System.Collections.SortedList>) oder einer <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName>-Implementierung (für die zwei generischen Klassen) sortiert.  
  
-   Jede Klasse enthält Eigenschaften, die Sammlungen zurückgeben, die nur die Schlüssel oder nur die Werte enthalten.  
  
 Die folgende Tabelle enthält einige Unterschiede zwischen den beiden sortierten Listenklassen und der <xref:System.Collections.Generic.SortedDictionary%602>-Klasse.  
  
|Nicht generische Klasse <xref:System.Collections.SortedList> und generische Klasse <xref:System.Collections.Generic.SortedList%602>|Generische Klasse <xref:System.Collections.Generic.SortedDictionary%602>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|Die Eigenschaften, die Schlüssel und Werte zurückgeben, werden indiziert, um einen effizienten Abruf zu ermöglichen.|Kein indizierter Abruf.|  
|Der Abruf erfolgt über O(log `n`).|Der Abruf erfolgt über O(log `n`).|  
|Das Einfügen und Entfernen erfolgen im Allgemeinen über „O(`n`)“. Das Einfügen erfolgt jedoch über „O(1)“ für Daten, die bereits in der Sortierreihenfolge vorliegen, sodass jedes Element am Ende der Liste hinzugefügt wird. (Dies setzt voraus, dass keine Größenänderung erforderlich ist.)|Einfügen und Entfernen erfolgen über „O(log `n`)“.|  
|Belegt weniger Speicher als ein <xref:System.Collections.Generic.SortedDictionary%602>.|Belegt mehr Speicher als die nicht generische Klasse <xref:System.Collections.SortedList> und die generische Klasse <xref:System.Collections.Generic.SortedList%602>.|  
  
 Für sortierte Listen oder Wörterbücher, die gleichzeitig für mehrere Threads zugänglich sein müssen, können Sie einer Klasse Sortierlogik hinzufügen, die von <xref:System.Collections.Concurrent.ConcurrentDictionary%602> abgeleitet wird.  
  
> [!NOTE]
>  Für Werte, die ihre eigenen Schlüssel enthalten (z.B. Mitarbeiterdatensätze mit einer Mitarbeiter-ID), können Sie durch Ableiten von der generischen Klasse <xref:System.Collections.ObjectModel.KeyedCollection%602> eine schlüsselgebundene Sammlung erstellen, die einige Merkmale einer Liste und einige Merkmale eines Wörterbuchs aufweist.  
  
 Von [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] an stellt die Klasse <xref:System.Collections.Generic.SortedSet%601> eine selbstausgleichende Struktur bereit, in der Daten nach Einfüge-, Lösch- und Suchvorgängen in sortierter Reihenfolge verwaltet werden. Diese Klasse und die Klasse <xref:System.Collections.Generic.HashSet%601> implementieren die <xref:System.Collections.Generic.ISet%601>-Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.IDictionary?displayProperty=fullName>   
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>   
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>   
 [Häufig verwendete Auflistungstypen](../../../docs/standard/collections/commonly-used-collection-types.md)
