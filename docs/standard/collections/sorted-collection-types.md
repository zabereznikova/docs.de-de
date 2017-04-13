---
title: "Sortierte Auflistungstypen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Auflistungen [.NET Framework], SortedList-Auflistungstyp"
  - "Gruppieren von Daten in Auflistungen, SortedList-Auflistungstyp"
  - "SortedDictionary-Auflistungstyp"
  - "SortedList-Klasse, Gruppieren von Daten in Auflistungen"
  - "SortedList-Auflistungstyp"
ms.assetid: 3db965b2-36a6-4b12-b76e-7f074ff7275a
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Sortierte Auflistungstypen
Die <xref:System.Collections.SortedList?displayProperty=fullName>\-Klasse, die generische <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>\-Klasse und die generische <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName>\-Klasse sind insofern mit der <xref:System.Collections.Hashtable>\-Klasse und der generischen <xref:System.Collections.Generic.Dictionary%602>\-Klasse vergleichbar, als sie die <xref:System.Collections.IDictionary>\-Schnittstelle implementieren. Sie behalten jedoch ihre Elemente in der Sortierreihenfolge nach Schlüssel bei und verfügen nicht über die O\(1\)\-Einfüge\- und \-Abrufmerkmale von Hashtabellen.  Die drei Klassen verfügen über mehrere gemeinsame Features:  
  
-   Alle drei Klassen implementieren die <xref:System.Collections.IDictionary?displayProperty=fullName>\-Schnittstelle.  Die beiden generischen Klassen implementieren zusätzlich die generische <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>\-Schnittstelle.  
  
-   Jedes Element ist ein Schlüssel\/Wert\-Paar zu Enumerationszwecken.  
  
    > [!NOTE]
    >  Die nicht generische <xref:System.Collections.SortedList>\-Klasse gibt bei der Enumeration <xref:System.Collections.DictionaryEntry>\-Objekte zurück, während die beiden generischen Typen <xref:System.Collections.Generic.KeyValuePair%602>\-Objekte zurückgeben.  
  
-   Elemente werden entsprechend einer <xref:System.Collections.IComparer?displayProperty=fullName>\-Implementierung \(für die nicht generische <xref:System.Collections.SortedList>\-Klasse\) oder einer <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName>\-Implementierung \(für die beiden generischen Klassen\) sortiert.  
  
-   Jede Klasse stellt Eigenschaften bereit, die Auflistungen zurückgeben, die nur die Schlüssel oder nur die Werte enthalten.  
  
 In der folgenden Tabelle sind einige Unterschiede zwischen den beiden SortedList\-Klassen und der <xref:System.Collections.Generic.SortedDictionary%602>\-Klasse aufgelistet.  
  
|Nicht generische <xref:System.Collections.SortedList>\-Klasse und generische <xref:System.Collections.Generic.SortedList%602>\-Klasse|Generische <xref:System.Collections.Generic.SortedDictionary%602>\-Klasse|  
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|Da die Eigenschaften zum Zurückgeben von Schlüsseln und Werten indiziert sind, ist ein effizienter indizierter Abruf möglich.|Kein indizierter Abruf.|  
|O\(log `n`\)\-Abruf.|O\(log `n`\)\-Abruf.|  
|Einfüge\- und Abrufvorgänge erfolgen generell nach O\(`n`\); bei Daten, die sich bereits in der richtigen Sortierreihenfolge befinden, wird jedoch nach O\(1\) eingefügt, sodass jedes Element am Ende der Liste hinzugefügt wird. \(Dabei wird davon ausgegangen, dass keine Größenanpassung erforderlich ist.\)|O\(log `n`\)\-Einfüge\- und \-Abrufvorgänge.|  
|Benötigt weniger Arbeitsspeicher als <xref:System.Collections.Generic.SortedDictionary%602>.|Benötigt mehr Arbeitsspeicher als die nicht generische <xref:System.Collections.SortedList>\-Klasse und die generische <xref:System.Collections.Generic.SortedList%602>\-Klasse.|  
  
 In sortierten Listen oder Wörterbüchern, auf die von mehreren Threads gleichzeitig zugegriffen werden muss, können Sie einer Klasse, die von <xref:System.Collections.Concurrent.ConcurrentDictionary%602> abgeleitet wird, eine Sortierlogik hinzufügen.  
  
> [!NOTE]
>  Bei Werten, die eigene Schlüssel enthalten \(z. B. Mitarbeiterdatensätze mit einer Mitarbeiter\-ID\), können Sie durch Ableitung von der generischen <xref:System.Collections.ObjectModel.KeyedCollection%602>\-Klasse eine verschlüsselte Auflistung erstellen, die einige Merkmale einer Liste und einige Merkmale eines Wörterbuchs aufweist.  
  
 Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] stellt die <xref:System.Collections.Generic.SortedSet%601>\-Klasse eine selbstausgleichende Struktur bereit, die die Sortierung von Daten nach Einfüge\-, Lösch\- und Suchvorgängen beibehält.  Diese Klasse und die <xref:System.Collections.Generic.HashSet%601>\-Klasse implementieren die <xref:System.Collections.Generic.ISet%601>\-Schnittstelle.  
  
## Siehe auch  
 <xref:System.Collections.IDictionary?displayProperty=fullName>   
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>   
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>   
 [Häufig verwendete Auflistungstypen](../../../docs/standard/collections/commonly-used-collection-types.md)