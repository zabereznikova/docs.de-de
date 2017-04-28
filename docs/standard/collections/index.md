---
title: Auflistungen und Datenstrukturen | Microsoft-Dokumentation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grouping data in collections
- objects [.NET Framework], grouping in collections
- Array class, grouping data in collections
- threading [.NET Framework], safety
- Collections classes
- collections [.NET Framework]
ms.assetid: 60cc581f-1db5-445b-ba04-a173396bf872
caps.latest.revision: 36
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 27c475b8d29eb295bb3d6be24aa9ee9188f5c114
ms.lasthandoff: 04/08/2017

---
# <a name="collections-and-data-structures"></a>Auflistungen und Datenstrukturen
Ähnliche Daten können häufig effizienter verarbeitet werden, wenn sie als eine Auflistung gespeichert und bearbeitet werden. Sie können die <xref:System.Array?displayProperty=fullName>-Klasse oder die Klassen in den <xref:System.Collections>, <xref:System.Collections.Generic>, <xref:System.Collections.Concurrent> und System.Collections.Immutable verwenden, um einzelne Elemente oder einen Elementbereich zu einer Auflistung hinzuzufügen, darin zu ändern oder daraus zu entfernen.  
  
 Es gibt zwei Grundarten von Auflistungen: generische Auflistungen und nicht generische Auflistungen. Generische Auflistungen wurden in .NET Framework 2.0 hinzugefügt und bieten Auflistungen, die zum Zeitpunkt der Kompilierung typsicher sind. Aus diesem Grund bieten generische Auflistungen in der Regel eine bessere Leistung. Generische Auflistungen akzeptieren beim Erstellen einen Typparameter und erfordern keine Umwandlung in den und aus dem <xref:System.Object>-Typ, wenn Sie Elemente zur Auflistung hinzufügen oder daraus entfernen.  Darüber hinaus werden die meisten generischen Auflistungen in [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)]-Apps unterstützt. Nicht generische Auflistungen speichern Elemente als <xref:System.Object>, erfordern eine Umwandlung, und die meisten werden für die [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)]-App-Entwicklung nicht unterstützt. Allerdings finden Sie möglicherweise in älterem Code auch nicht generische Auflistungen.  
  
 Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] stellen die Auflistungen im <xref:System.Collections.Concurrent>-Namespace effiziente threadsichere Vorgänge für den Zugriff auf Auflistungselemente aus mehreren Threads bereit. Die unveränderlichen Auflistungsklassen im Namespace „System.Collections.Immutable“ ([NuGet-Paket](https://www.nuget.org/packages/System.Collections.Immutable)) sind grundsätzlich threadsicher, da Vorgänge mit einer Kopie der ursprünglichen Auflistung ausgeführt werden und die ursprüngliche Auflistung nicht geändert werden kann.  
  
  
<a name="BKMK_Commoncollectionfeatures"></a>   
## <a name="common-collection-features"></a>Allgemeine Auflistungsfunktionen  
 Alle Auflistungen bieten Methoden zum Hinzufügen, Entfernen oder Suchen von Elementen in der Auflistung. Darüber hinaus teilen sich alle Auflistungen, die die <xref:System.Collections.ICollection>-Schnittstelle oder die <xref:System.Collections.Generic.ICollection%601>-Schnittstelle direkt oder indirekt implementieren, diese Merkmale:  
  
-   **Die Fähigkeit zum Enumerieren der Auflistung**  
  
     .NET Framework-Auflistungen implementieren entweder <xref:System.Collections.IEnumerable?displayProperty=fullName> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>, damit die Auflistung durchlaufen werden kann. Ein Enumerator kann als beweglicher Zeiger auf ein Element in der Auflistung betrachtet werden. Die Anweisungen [foreach, in](~/docs/csharp/language-reference/keywords/foreach-in.md) und [For Each...Next](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) verwenden den Enumerator, der von der <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode verfügbar gemacht wird, und verbergen die Komplexität der Bearbeitung des Enumerators. Darüber hinaus gilt jede Auflistung, die <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> implementiert, als *abfragbarer Typ* und kann mit LINQ abgefragt werden. LINQ-Abfragen bieten ein allgemeines Muster für den Datenzugriff. Sie sind normalerweise präziser und besser lesbar als standardmäßige `foreach`-Schleifen und bieten Filter-, Sortier- und Gruppierungsfunktionen. LINQ-Abfragen können auch die Leistung verbessern. Weitere Informationen finden Sie unter [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9), [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md) und [Einführung in LINQ-Abfragen (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
-   **Die Möglichkeit, den Inhalt der Auflistung in ein Array zu kopieren**  
  
     Alle Auflistungen können mit der **CopyTo**-Methode in ein Array kopiert werden. Die Reihenfolge der Elemente im neuen Array basiert jedoch auf der Reihenfolge, in der sie vom Enumerator zurückgegeben werden. Das resultierende Array ist stets eindimensional mit einer unteren Grenze von 0 (Null).  
  
 Viele Auflistungsklassen enthalten außerdem die folgenden Funktionen:  
  
-   **Kapazität und Zähleigenschaften**  
  
     Die Kapazität einer Auflistung ist die Anzahl der Elemente, die sie enthalten kann. Die Anzahl einer Auflistung ist die Anzahl der tatsächlich enthaltenen Elemente. Einige Auflistungen blenden die Kapazität oder die Anzahl oder beides aus.  
  
     Die meisten Auflistungen erweitern ihre Kapazität automatisch, wenn die aktuelle Kapazität erreicht ist. Der Speicher wird neu zugewiesen, und die Elemente werden aus der alten Auflistung in die neue kopiert. Dies reduziert den Code, der für die Verwendung der Auflistung erforderlich ist. Die Leistung der Auflistung kann dadurch allerdings beeinträchtigt werden. Beispiel für <xref:System.Collections.Generic.List%601>: Wenn <xref:System.Collections.Generic.List%601.Count%2A> kleiner als <xref:System.Collections.Generic.List%601.Capacity%2A> ist, ist das Hinzufügen eines Elements ein O(1)-Vorgang. Wenn die Kapazität für das neue Element erhöht werden muss, ist das Hinzufügen eines Elements ein O(n)-Vorgang, wobei n <xref:System.Collections.Generic.List%601.Count%2A> ist. Am besten vermeiden Sie Leistungsverluste aufgrund mehrerer Neuzuweisungen, indem Sie die anfängliche Kapazität als geschätzte Größe der Auflistung festlegen.  
  
     Ein <xref:System.Collections.BitArray> ist ein Sonderfall: Die Kapazität ist identisch mit der Länge, die wiederum mit der Anzahl übereinstimmt.  
  
-   **Eine konsistente Untergrenze**  
  
     Die untere Grenze einer Auflistung ist der Index des ersten darin enthaltenen Elements. Alle indizierten Auflistungen in den <xref:System.Collections>-Namespaces haben die untere Grenze null, d.h. sie sind nullindiziert. <xref:System.Array> hat standardmäßig die untere Grenze null. Es kann jedoch eine andere Untergrenze definiert werden, wenn Sie eine Instanz der **Array**-Klasse mit <xref:System.Array.CreateInstance%2A?displayProperty=fullName> erstellen.  
  
-   **Synchronisierung für den Zugriff aus mehreren Threads** (nur <xref:System.Collections>-Klassen).  
  
     Nicht generische Auflistungstypen im <xref:System.Collections>-Namespace bieten durch Synchronisierung ein gewisses Maß an Threadsicherheit. In der Regel werden sie durch die Member <xref:System.Collections.ICollection.SyncRoot%2A> und <xref:System.Collections.ICollection.IsSynchronized%2A> verfügbar gemacht. Diese Auflistungen sind nicht standardmäßig Thread-sicher. Wenn Sie skalierbaren und effizienten Multithreadzugriff auf eine Auflistung benötigen, verwenden Sie eine der Klassen im <xref:System.Collections.Concurrent>-Namespace, oder ziehen Sie den Einsatz einer unveränderlichen Auflistung in Erwägung. Weitere Informationen finden Sie unter [Threadsichere Auflistungen](../../../docs/standard/collections/thread-safe/index.md).  
  
<a name="BKMK_Choosingacollection"></a>   
## <a name="choosing-a-collection"></a>Auswählen einer Auflistung  
 Im Allgemeinen sollten Sie generische Auflistungen verwenden. Die folgende Tabelle beschreibt einige häufig auftretende Auflistungsszenarios sowie die Auflistungsklassen, die Sie für diese Szenarien verwenden können. Wenn Sie sich mit der Arbeit mit generischen Auflistungen noch nicht auskennen, hilft Ihnen diese Tabelle bei der Auswahl der generischen Auflistung, die am besten für Ihre Aufgabe geeignet ist.  
<!-- todo: All code-formatted API refs in the table need to be changed into links -->  
|Ziel|Optionen für generische Auflistungen|Optionen für nicht generische Auflistungen|Optionen für Thread-sichere oder unveränderliche Auflistungen|  
|-|-|-|-|  
|Speichern von Elementen als Schlüssel-Wert-Paare für die schnelle Suche nach Schlüssel|<xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>|<xref:System.Collections.Hashtable><br /><br /> (Eine Auflistung von Schlüssel-Wert-Paaren, die auf Grundlage des Hashcodes des Schlüssels geordnet sind.)|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName><br /><br /> <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=fullName><br /><br /> `ImmutableDictionary(TKey, TValue) Class`|  
|Zugriff auf die Elemente nach Index|<xref:System.Collections.Generic.List%601?displayProperty=fullName>|<xref:System.Array?displayProperty=fullName><br /><br /> <xref:System.Collections.ArrayList?displayProperty=fullName>|`ImmutableList(T) Class`<br /><br /> `ImmutableArray Class`|  
|Verwenden von Elementen nach First-in-First-Out (FIFO)-Prinzip|<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>|<xref:System.Collections.Queue?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName><br /><br /> `ImmutableQueue(T) Class`|  
|Verwenden von Daten nach Last-In-First-Out (LIFO)-Prinzip|<xref:System.Collections.Generic.Stack%601?displayProperty=fullName>|<xref:System.Collections.Stack?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName><br /><br /> `ImmutableStack(T) Class`|  
|Zugriff auf Elemente in Reihenfolge|<xref:System.Collections.Generic.LinkedList%601?displayProperty=fullName>|Keine Empfehlung|Keine Empfehlung|  
|Empfang von Benachrichtigungen, wenn Elemente der Auflistung hinzugefügt oder aus ihr entfernt werden. (implementiert <xref:System.ComponentModel.INotifyPropertyChanged> und <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=fullName>)|<xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=fullName>|Keine Empfehlung|Keine Empfehlung|  
|Sortierte Auflistung|<xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>|<xref:System.Collections.SortedList?displayProperty=fullName>|`ImmutableSortedDictionary(TKey, TValue) Class`<br /><br /> `ImmutableSortedSet(T) Class`|  
|Ein Satz für mathematische Funktionen|<xref:System.Collections.Generic.HashSet%601?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName>|Keine Empfehlung|`ImmutableHashSet(T) Class`<br /><br /> `ImmutableSortedSet(T) Class`|  
  
<a name="BKMK_RelatedTopics"></a>   
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Auswählen einer Auflistungsklasse](../../../docs/standard/collections/selecting-a-collection-class.md)|Beschreibt die verschiedenen Auflistungen und hilft Ihnen bei der Auswahl für Ihr Szenario.|  
|[Häufig verwendete Auflistungstypen](../../../docs/standard/collections/commonly-used-collection-types.md)|Beschreibt häufig verwendete generische und nicht generische Auflistungstypen wie z.B. <xref:System.Array?displayProperty=fullName>, <xref:System.Collections.Generic.List%601?displayProperty=fullName> und <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>.|  
|[Verwenden von generischen Auflistungen](../../../docs/standard/collections/when-to-use-generic-collections.md)|Erörtert die Verwendung generischer Auflistungstypen.|  
|[Vergleiche und Sortierungen innerhalb von Auflistungen](../../../docs/standard/collections/comparisons-and-sorts-within-collections.md)|Erläutert die Verwendung von Übereinstimmungs- und Sortiervergleichen in Auflistungen.|  
|[Sortierte Auflistungstypen](../../../docs/standard/collections/sorted-collection-types.md)|Beschreibt die Leistung und die Merkmale von sortierten Auflistungen.|  
|[Hashtable-Auflistungstyp und Dictionary-Auflistungstyp](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|Beschreibt die Funktionen von generischen und nicht generischen hashbasierten Wörterbuchtypen.|  
|[threadsichere Auflistungen](../../../docs/standard/collections/thread-safe/index.md)|Beschreibt Auflistungstypen wie <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> und <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>, die einen sicheren und effizienten gleichzeitigen Zugriff aus mehreren Threads unterstützen.|  
|System.Collections.Immutable|Enthält einführende Informationen zu unveränderlichen Auflistungen und Links zu den Auflistungstypen.|  
  
<a name="BKMK_Reference"></a>   
## <a name="reference"></a>Verweis  
 <xref:System.Array?displayProperty=fullName>  
  
 <xref:System.Collections?displayProperty=fullName>  
  
 <xref:System.Collections.Concurrent?displayProperty=fullName>  
  
 <xref:System.Collections.Generic?displayProperty=fullName>  
  
 <xref:System.Collections.Specialized?displayProperty=fullName>  
  
 <xref:System.Linq?displayProperty=fullName>  
  
 System.Collections.Immutable
