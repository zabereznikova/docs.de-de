---
title: "Auflistungen und Datenstrukturen | Microsoft Docs"
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
  - "Gruppieren von Daten in Auflistungen"
  - "Objekte [.NET Framework], Gruppieren in Sammlungen"
  - "Array-Klasse, Gruppieren von Daten in Sammlungen"
  - "Threading [.NET Framework], Sicherheit"
  - "Auflistungsklassen"
  - "Auflistungen [.NET Framework]"
ms.assetid: 60cc581f-1db5-445b-ba04-a173396bf872
caps.latest.revision: 36
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 35
---
# Auflistungen und Datenstrukturen
Ähnliche Daten können häufig effizienter verarbeitet werden, wenn sie als eine Auflistung gespeichert und bearbeitet werden. Können Sie die <xref:System.Array?displayProperty=fullName> Klasse oder die Klassen in der <xref:System.Collections>, <xref:System.Collections.Generic>, <xref:System.Collections.Concurrent>, System.Collections.Immutable Namespaces hinzufügen, entfernen und ändern Sie einzelne Elemente oder einen Bereich von Elementen in einer Auflistung.  
  
 Es gibt zwei Grundarten von Auflistungen: generische Auflistungen und nicht generische Auflistungen. Generische Auflistungen wurden in .NET Framework 2.0 hinzugefügt und bieten Auflistungen, die zum Zeitpunkt der Kompilierung typsicher sind. Aus diesem Grund bieten generische Auflistungen in der Regel eine bessere Leistung. Generische Auflistungen akzeptieren beim Erstellen einen Typparameter und erfordern keine Umwandlung in den und aus dem <xref:System.Object>-Typ, wenn Sie Elemente zur Auflistung hinzufügen oder daraus entfernen.  Darüber hinaus werden die meisten generischen Auflistungen in [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)]-Apps unterstützt. Nicht generische Auflistungen speichern Elemente als <xref:System.Object>, erfordern eine Umwandlung und die meisten können nicht für [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] app-Entwicklung. Allerdings finden Sie möglicherweise in älterem Code auch nicht generische Auflistungen.  
  
 Beginnend mit der [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Sammlungen in der <xref:System.Collections.Concurrent> Namespace effiziente threadsichere Operationen für den Zugriff auf Auflistungselemente aus mehreren Threads bereit. Die unveränderlichen Auflistungsklassen im Namespace System.Collections.Immutable ([NuGet-Paket](https://www.nuget.org/packages/System.Collections.Immutable)) sind grundsätzlich threadsicher, da Vorgänge auf eine Kopie der ursprünglichen Auflistung ausgeführt werden und die ursprüngliche Auflistung kann nicht geändert werden.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="BKMK_Commoncollectionfeatures"></a>   
## <a name="common-collection-features"></a>Allgemeine Auflistungsfunktionen  
 Alle Auflistungen bieten Methoden zum Hinzufügen, Entfernen oder Suchen von Elementen in der Auflistung. Darüber hinaus alle Sammlungen, die direkt oder indirekt Implementieren der <xref:System.Collections.ICollection> Schnittstelle oder die <xref:System.Collections.Generic.ICollection%601> Schnittstelle gemeinsam verwenden, diese Funktionen:  
  
-   **Die Fähigkeit zum Enumerieren der Auflistung**  
  
     .NET Framework-Auflistungen implementieren entweder <xref:System.Collections.IEnumerable?displayProperty=fullName> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> , damit die Auflistung durchlaufen werden kann. Ein Enumerator kann als beweglicher Zeiger auf ein Element in der Auflistung betrachtet werden. Die [Foreach im](../Topic/foreach,%20in%20\(C%23%20Reference\).md) Anweisung und die [für jede... Nächste Anweisung](../Topic/For%20Each...Next%20Statement%20\(Visual%20Basic\).md) verwenden Sie den Enumerator verfügbar gemacht werden, indem Sie die <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode und verbergen die Komplexität bei der Bearbeitung des Enumerators. Darüber hinaus eine beliebige Sammlung, die implementiert <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> gilt ein *abfragbarer Typ* und mit LINQ abgefragt werden kann. LINQ-Abfragen bieten ein allgemeines Muster für den Datenzugriff. Sie sind normalerweise präziser und besser lesbar als standardmäßige `foreach`-Schleifen und bieten Filter-, Sortier- und Gruppierungsfunktionen. LINQ-Abfragen können auch die Leistung verbessern. Weitere Informationen finden Sie unter [LINQ to Objects](../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-objects.md), [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md) und [Einführung in LINQ-Abfragen (c#)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md).  
  
-   **Die Möglichkeit, den Inhalt der Auflistung in ein Array zu kopieren**  
  
     Sammlungen können kopiert werden, auf ein Array mit den **CopyTo** Methode; die Reihenfolge der Elemente im neuen Array basiert jedoch auf der Reihenfolge, in der vom Enumerator werden zurückgegeben. Das resultierende Array ist stets eindimensional mit einer unteren Grenze von&0; (Null).  
  
 Viele Auflistungsklassen enthalten außerdem die folgenden Funktionen:  
  
-   **Kapazität und Zähleigenschaften**  
  
     Die Kapazität einer Auflistung ist die Anzahl der Elemente, die sie enthalten kann. Die Anzahl einer Auflistung ist die Anzahl der tatsächlich enthaltenen Elemente. Einige Auflistungen blenden die Kapazität oder die Anzahl oder beides aus.  
  
     Die meisten Auflistungen erweitern ihre Kapazität automatisch, wenn die aktuelle Kapazität erreicht ist. Der Speicher wird neu zugewiesen, und die Elemente werden aus der alten Auflistung in die neue kopiert. Dies reduziert den Code, der für die Verwendung der Auflistung erforderlich ist. Die Leistung der Auflistung kann dadurch allerdings beeinträchtigt werden. Beispielsweise <xref:System.Collections.Generic.List%601>, wenn <xref:System.Collections.Generic.List%601.Count%2A> ist kleiner als <xref:System.Collections.Generic.List%601.Capacity%2A>, Hinzufügen eines Elements ist ein o(1)-Vorgang. Wenn die Kapazität zur Anpassung an das neue Element erhöht werden muss, Hinzufügen eines Elements ein o(n)-Vorgang, wobei n ist wird <xref:System.Collections.Generic.List%601.Count%2A>. Am besten vermeiden Sie Leistungsverluste aufgrund mehrerer Neuzuweisungen, indem Sie die anfängliche Kapazität als geschätzte Größe der Auflistung festlegen.  
  
     Ein <xref:System.Collections.BitArray> ist ein Sonderfall: Die Kapazität ist identisch mit der Länge, die wiederum mit der Anzahl übereinstimmt.  
  
-   **Eine konsistente Untergrenze**  
  
     Die untere Grenze einer Auflistung ist der Index des ersten darin enthaltenen Elements. Alle indizierten Auflistungen in den <xref:System.Collections>-Namespaces haben eine untere Grenze von Null, d.h. sie sind 0-indiziert. <xref:System.Array> verfügt über eine Untergrenze von&0; (null), standardmäßig, jedoch eine andere Untergrenze definiert werden, wenn das Erstellen einer Instanz der **Array** -Klasse mit <xref:System.Array.CreateInstance%2A?displayProperty=fullName>.  
  
-   **Synchronisierung für den Zugriff aus mehreren Threads** (nur <xref:System.Collections>-Klassen).  
  
     Nicht generische Auflistungstypen in der <xref:System.Collections> Namespace bieten einige Threadsicherheit durch die Synchronisierung; in der Regel über verfügbar gemacht, die <xref:System.Collections.ICollection.SyncRoot%2A> und <xref:System.Collections.ICollection.IsSynchronized%2A> Elemente. Diese Auflistungen sind nicht standardmäßig Thread-sicher. Wenn Sie skalierbaren und effizienten Multithreadzugriff auf eine Auflistung benötigen, verwenden Sie eine der Klassen im <xref:System.Collections.Concurrent>-Namespace, oder ziehen Sie den Einsatz einer unveränderlichen Auflistung in Erwägung. Weitere Informationen finden Sie unter [Threadsichere Auflistungen](../../../docs/standard/collections/thread-safe/index.md).  
  
<a name="BKMK_Choosingacollection"></a>   
## <a name="choosing-a-collection"></a>Auswählen einer Auflistung  
 Im Allgemeinen sollten Sie generische Auflistungen verwenden. Die folgende Tabelle beschreibt einige häufig auftretende Auflistungsszenarios sowie die Auflistungsklassen, die Sie für diese Szenarien verwenden können. Wenn Sie sich mit der Arbeit mit generischen Auflistungen noch nicht auskennen, hilft Ihnen diese Tabelle bei der Auswahl der generischen Auflistung, die am besten für Ihre Aufgabe geeignet ist.  
  
|||||  
|-|-|-|-|  
|Ziel|Optionen für generische Auflistungen|Optionen für nicht generische Auflistungen|Optionen für Thread-sichere oder unveränderliche Auflistungen|  
|Speichern von Elementen als Schlüssel-Wert-Paare für die schnelle Suche nach Schlüssel|<xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName></TKey, TValue>|<xref:System.Collections.Hashtable><br /><br /> (Eine Auflistung von Schlüssel-Wert-Paaren, die auf Grundlage des Hashcodes des Schlüssels geordnet sind.)|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>\</TKey, TValue><br /><br /> <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=fullName>\</TKey, TValue><br /><br /> [ImmutableDictionary (TKey, TValue)-Klasse](../Topic/ImmutableDictionary\(TKey,%20TValue\)%20Class.md)|  
|Zugriff auf die Elemente nach Index|<xref:System.Collections.Generic.List%601?displayProperty=fullName>|<xref:System.Array?displayProperty=fullName><br /><br /> <xref:System.Collections.ArrayList?displayProperty=fullName>|[ImmutableList(T)-Klasse](../Topic/ImmutableList\(T\)%20Class.md)<br /><br /> [ImmutableArray-Klasse](../Topic/ImmutableArray%20Class.md)|  
|Verwenden von Elementen nach First-in-First-Out (FIFO)-Prinzip|<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>|<xref:System.Collections.Queue?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName><br /><br /> [ImmutableQueue(T)-Klasse](../Topic/ImmutableQueue\(T\)%20Class.md)|  
|Verwenden von Daten nach Last-In-First-Out (LIFO)-Prinzip|<xref:System.Collections.Generic.Stack%601?displayProperty=fullName>|<xref:System.Collections.Stack?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName><br /><br /> [ImmutableStack(T)-Klasse](../Topic/ImmutableStack\(T\)%20Class.md)|  
|Zugriff auf Elemente in Reihenfolge|<xref:System.Collections.Generic.LinkedList%601?displayProperty=fullName>|Keine Empfehlung|Keine Empfehlung|  
|Empfang von Benachrichtigungen, wenn Elemente der Auflistung hinzugefügt oder aus ihr entfernt werden. (implementiert <xref:System.ComponentModel.INotifyPropertyChanged> und <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=fullName>)|<xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=fullName>|Keine Empfehlung|Keine Empfehlung|  
|Sortierte Auflistung|<xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>\</TKey, TValue>|<xref:System.Collections.SortedList?displayProperty=fullName>|[ImmutableSortedDictionary (TKey, TValue)-Klasse](../Topic/ImmutableSortedDictionary\(TKey,%20TValue\)%20Class.md)<br /><br /> [ImmutableSortedSet(T)-Klasse](../Topic/ImmutableSortedSet\(T\)%20Class.md)|  
|Ein Satz für mathematische Funktionen|<xref:System.Collections.Generic.HashSet%601?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName>|Keine Empfehlung|[ImmutableHashSet(T)-Klasse](../Topic/ImmutableHashSet\(T\)%20Class.md)<br /><br /> [ImmutableSortedSet(T)-Klasse](../Topic/ImmutableSortedSet\(T\)%20Class.md)|  
  
<a name="BKMK_RelatedTopics"></a>   
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Auswählen einer Auflistungsklasse](../../../docs/standard/collections/selecting-a-collection-class.md)|Beschreibt die verschiedenen Auflistungen und hilft Ihnen bei der Auswahl für Ihr Szenario.|  
|[Häufig verwendete Auflistungstypen](../../../docs/standard/collections/commonly-used-collection-types.md)|Beschreibt häufig verwendete generische und nicht generische Auflistungstypen, z. B. <xref:System.Array?displayProperty=fullName>, <xref:System.Collections.Generic.List%601?displayProperty=fullName>, und <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>.\</TKey, TValue>|  
|[Verwenden von generischen Auflistungen](../../../docs/standard/collections/when-to-use-generic-collections.md)|Erörtert die Verwendung generischer Auflistungstypen.|  
|[Vergleiche und Sortierungen innerhalb von Auflistungen](../../../docs/standard/collections/comparisons-and-sorts-within-collections.md)|Erläutert die Verwendung von Übereinstimmungs- und Sortiervergleichen in Auflistungen.|  
|[Sortierte Auflistungstypen](../../../docs/standard/collections/sorted-collection-types.md)|Beschreibt die Leistung und die Merkmale von sortierten Auflistungen.|  
|[Hashtable-Auflistungstyp und Dictionary-Auflistungstyp](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|Beschreibt die Funktionen von generischen und nicht generischen hashbasierten Wörterbuchtypen.|  
|[threadsichere Auflistungen](../../../docs/standard/collections/thread-safe/index.md)|Beschreibt Auflistungstypen wie z. B. <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> und <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName> , sicheren und effizienten gleichzeitigen Zugriff von mehreren Threads unterstützen.|  
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