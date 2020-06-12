---
title: Auflistungen und Datenstrukturen
description: Erfahren Sie, wie Sie Auflistungen und Datenstrukturen in .NET verwenden. Verwenden Sie generische und nicht generische Auflistungen in threadsicheren Vorgängen.
ms.date: 04/30/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- grouping data in collections
- objects [.NET Framework], grouping in collections
- Array class, grouping data in collections
- threading [.NET Framework], safety
- Collections classes
- collections [.NET Framework]
ms.assetid: 60cc581f-1db5-445b-ba04-a173396bf872
ms.openlocfilehash: 3d5b16dccdd9867293a52c74a2d379c807fd93e7
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662744"
---
# <a name="collections-and-data-structures"></a>Auflistungen und Datenstrukturen

Ähnliche Daten können häufig effizienter verarbeitet werden, wenn sie als eine Auflistung gespeichert und bearbeitet werden. Verwenden Sie die Klasse <xref:System.Array?displayProperty=nameWithType> oder die Klassen in den Namespaces <xref:System.Collections>, <xref:System.Collections.Generic>, <xref:System.Collections.Concurrent>, <xref:System.Collections.Immutable>, um einzelne Elemente oder einen Bereich von Elementen zu einer Sammlung hinzuzufügen, aus dieser zu entfernen und zu ändern.

Es gibt zwei Grundarten von Auflistungen: generische Auflistungen und nicht generische Auflistungen. Generische Auflistungen wurden in .NET Framework 2.0 hinzugefügt und bieten Auflistungen, die zum Zeitpunkt der Kompilierung typsicher sind. Aus diesem Grund bieten generische Auflistungen in der Regel eine bessere Leistung. Generische Auflistungen akzeptieren beim Erstellen einen Typparameter und erfordern nicht, dass Sie eine Umwandlung in den und aus dem <xref:System.Object>-Typ durchführen, wenn Sie Elemente aus der Auflistung hinzufügen oder entfernen.  Darüber hinaus werden die meisten generischen Auflistungen in Windows Store-Apps unterstützt. Nicht generische Auflistungen speichern Elemente als <xref:System.Object>, erfordern eine Umwandlung, und die meisten werden für die Windows Store-App-Entwicklung nicht unterstützt. Allerdings finden Sie möglicherweise in älterem Code auch nicht generische Auflistungen.

Ab .NET Framework 4 stellen die Auflistungen im <xref:System.Collections.Concurrent>-Namespace effiziente threadsichere Vorgänge für den Zugriff auf Auflistungselemente aus mehreren Threads bereit. Die unveränderlichen Sammlungsklassen im Namespace <xref:System.Collections.Immutable> ([NuGet-Paket](https://www.nuget.org/packages/System.Collections.Immutable)) sind grundsätzlich threadsicher, da Vorgänge mit einer Kopie der ursprünglichen Sammlung ausgeführt werden und die ursprüngliche Sammlung nicht geändert werden kann.

<a name="BKMK_Commoncollectionfeatures"></a>
## <a name="common-collection-features"></a>Allgemeine Auflistungsfunktionen

Alle Sammlungen bieten Methoden zum Hinzufügen, Entfernen oder Suchen von Elementen in der Sammlung. Darüber hinaus teilen sich alle Auflistungen, die die <xref:System.Collections.ICollection>-Schnittstelle oder die <xref:System.Collections.Generic.ICollection%601>-Schnittstelle direkt oder indirekt implementieren, diese Funktionen:

- **Die Fähigkeit zum Enumerieren der Auflistung**

    .NET Framework-Auflistungen implementieren entweder <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>, damit die Auflistung durchlaufen werden kann. Ein Enumerator kann als beweglicher Zeiger auf ein Element in der Auflistung betrachtet werden. Die Anweisung [foreach, in](../../csharp/language-reference/keywords/foreach-in.md) und die [For Each...Next-Anweisung](../../visual-basic/language-reference/statements/for-each-next-statement.md) verwenden den Enumerator, der mit der <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode verfügbar gemacht wird, und verbergen die Komplexität bei der Bearbeitung des Enumerators. Darüber hinaus gilt jede Auflistung, die <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> implementiert, als *abfragbarer Typ* und kann mit LINQ abgefragt werden. LINQ-Abfragen bieten ein allgemeines Muster für den Datenzugriff. Sie sind normalerweise präziser und besser lesbar als standardmäßige `foreach`-Schleifen und bieten Filter-, Sortier- und Gruppierungsfunktionen. LINQ-Abfragen können auch die Leistung verbessern. Weitere Informationen finden Sie unter [LINQ to Objects (C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md), [LINQ to Objects (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md), [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md), [Einführung in LINQ-Abfragen (C#)](../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) und [Basic Query Operations (Visual Basic) (Grundlegende Abfragevorgänge (Visual Basic))](../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).

- **Die Möglichkeit, den Inhalt der Auflistung in ein Array zu kopieren**

    Alle Auflistungen können mit der **CopyTo**-Methode in ein Array kopiert werden. Die Reihenfolge der Elemente im neuen Array basiert jedoch auf der Reihenfolge, in der sie vom Enumerator zurückgegeben werden. Das resultierende Array ist stets eindimensional mit einer unteren Grenze von 0 (Null).

Viele Auflistungsklassen enthalten außerdem die folgenden Funktionen:

- **Kapazität und Zähleigenschaften**

    Die Kapazität einer Auflistung ist die Anzahl der Elemente, die sie enthalten kann. Die Anzahl einer Auflistung ist die Anzahl der tatsächlich enthaltenen Elemente. Einige Auflistungen blenden die Kapazität oder die Anzahl oder beides aus.

    Die meisten Auflistungen erweitern ihre Kapazität automatisch, wenn die aktuelle Kapazität erreicht ist. Der Speicher wird neu zugewiesen, und die Elemente werden aus der alten Auflistung in die neue kopiert. Dies reduziert den Code, der für die Verwendung der Auflistung erforderlich ist. Die Leistung der Auflistung kann dadurch allerdings beeinträchtigt werden. Beispiel: Für <xref:System.Collections.Generic.List%601> ist das Hinzufügen eines Elements ein O(1)-Vorgang, wenn <xref:System.Collections.Generic.List%601.Count%2A> kleiner als <xref:System.Collections.Generic.List%601.Capacity%2A> ist. Wenn die Kapazität für das neue Element erhöht werden muss, ist das Hinzufügen eines Elements ein O(`n`)-Vorgang, wobei `n` <xref:System.Collections.Generic.List%601.Count%2A> ist. Am besten vermeiden Sie Leistungsverluste aufgrund mehrerer Neuzuweisungen, indem Sie die anfängliche Kapazität als geschätzte Größe der Auflistung festlegen.

    Ein <xref:System.Collections.BitArray> ist ein Sonderfall; die Kapazität ist identisch mit der Länge, die wiederum mit der Anzahl übereinstimmt.

- **Eine konsistente Untergrenze**

    Die untere Grenze einer Auflistung ist der Index des ersten darin enthaltenen Elements. Alle indizierten Auflistungen in den <xref:System.Collections>-Namespaces haben eine untere Grenze von 0 (Null), d. h. sie sind 0-indiziert. <xref:System.Array> hat standardmäßig eine untere Grenze von 0; es kann jedoch eine andere Untergrenze definiert werden, wenn Sie eine Instanz der **Array**-Klasse mit <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> erstellen.

- **Synchronisierung für den Zugriff von mehreren Threads** (nur <xref:System.Collections>-Klassen).

    Nicht generische Auflistungstypen im <xref:System.Collections>-Namespace bieten ein gewisses Maß an Thread-Sicherheit durch die Synchronisierung; in der Regel werden sie durch die <xref:System.Collections.ICollection.SyncRoot%2A>- und <xref:System.Collections.ICollection.IsSynchronized%2A>-Member verfügbar gemacht. Diese Auflistungen sind nicht standardmäßig Thread-sicher. Wenn Sie skalierbaren und effizienten Multithreadzugriff auf eine Auflistung benötigen, verwenden Sie eine der Klassen im <xref:System.Collections.Concurrent>-Namespace oder ziehen Sie den Einsatz einer unveränderlichen Auflistung in Erwägung. Weitere Informationen finden Sie unter [Threadsichere Auflistungen](thread-safe/index.md).

<a name="BKMK_Choosingacollection"></a>
## <a name="choose-a-collection"></a>Auswählen einer Sammlung

Im Allgemeinen sollten Sie generische Auflistungen verwenden. Die folgende Tabelle beschreibt einige häufig auftretende Auflistungsszenarios sowie die Auflistungsklassen, die Sie für diese Szenarien verwenden können. Wenn Sie sich mit der Arbeit mit generischen Auflistungen noch nicht auskennen, hilft Ihnen diese Tabelle bei der Auswahl der generischen Auflistung, die am besten für Ihre Aufgabe geeignet ist.

|Ziel|Optionen für generische Auflistungen|Optionen für nicht generische Auflistungen|Optionen für threadsichere oder unveränderliche Auflistungen|
|-|-|-|-|
|Speichern von Elementen als Schlüssel-Wert-Paare für die schnelle Suche nach Schlüssel|<xref:System.Collections.Generic.Dictionary%602>|<xref:System.Collections.Hashtable><br /><br /> (Eine Sammlung von Schlüssel-Wert-Paaren, die auf Grundlage des Hashcodes des Schlüssels geordnet sind.)|<xref:System.Collections.Concurrent.ConcurrentDictionary%602><br /><br /> <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602><br /><br /> <xref:System.Collections.Immutable.ImmutableDictionary%602>|
|Zugriff auf die Elemente nach Index|<xref:System.Collections.Generic.List%601>|<xref:System.Array><br /><br /> <xref:System.Collections.ArrayList>|<xref:System.Collections.Immutable.ImmutableList%601><br /><br /> <xref:System.Collections.Immutable.ImmutableArray>|
|Verwenden von Elementen nach First-in-First-Out (FIFO)-Prinzip|<xref:System.Collections.Generic.Queue%601>|<xref:System.Collections.Queue>|<xref:System.Collections.Concurrent.ConcurrentQueue%601><br /><br /> <xref:System.Collections.Immutable.ImmutableQueue%601>|
|Verwenden von Daten nach Last-In-First-Out (LIFO)-Prinzip|<xref:System.Collections.Generic.Stack%601>|<xref:System.Collections.Stack>|<xref:System.Collections.Concurrent.ConcurrentStack%601><br /><br /> <xref:System.Collections.Immutable.ImmutableStack%601>|
|Zugriff auf Elemente in Reihenfolge|<xref:System.Collections.Generic.LinkedList%601>|Keine Empfehlung|Keine Empfehlung|
|Empfang von Benachrichtigungen, wenn Elemente der Auflistung hinzugefügt oder aus ihr entfernt werden. (Implementiert <xref:System.ComponentModel.INotifyPropertyChanged> und <xref:System.Collections.Specialized.INotifyCollectionChanged>)|<xref:System.Collections.ObjectModel.ObservableCollection%601>|Keine Empfehlung|Keine Empfehlung|
|Sortierte Auflistung|<xref:System.Collections.Generic.SortedList%602>|<xref:System.Collections.SortedList>|<xref:System.Collections.Immutable.ImmutableSortedDictionary%602><br /><br /> <xref:System.Collections.Immutable.ImmutableSortedSet%601>|
|Ein Satz für mathematische Funktionen|<xref:System.Collections.Generic.HashSet%601><br /><br /> <xref:System.Collections.Generic.SortedSet%601>|Keine Empfehlung|<xref:System.Collections.Immutable.ImmutableHashSet%601><br /><br /> <xref:System.Collections.Immutable.ImmutableSortedSet%601>|

### <a name="algorithmic-complexity-of-collections"></a>Algorithmische Komplexität von Sammlungen

Bei der Auswahl einer [Sammlungsklasse](selecting-a-collection-class.md) ist es sinnvoll, potenzielle Leistungseinbußen zu berücksichtigen. Verwenden Sie die folgende Tabelle als Referenz für den Vergleich zwischen verschiedenen veränderlichen Sammlungstypen und ihren unveränderlichen Gegenstücken in Bezug auf algorithmische Komplexität. Häufig sind unveränderliche Sammlungstypen weniger leistungsfähig, bieten aber aufgrund ihrer Unveränderlichkeit einen Vergleichsvorteil.

| Veränderlich                   | Amortisiert  | Ungünstigster Fall                | Unveränderlich                          | Komplexität |
|---------------------------|------------|---------------------------|------------------------------------|------------|
| `Stack<T>.Push`           | O(1)       | O(`n`)                    | `ImmutableStack<T>.Push`           | O(1)       |
| `Queue<T>.Enqueue`        | O(1)       | O(`n`)                    | `ImmutableQueue<T>.Enqueue`        | O(1)       |
| `List<T>.Add`             | O(1)       | O(`n`)                    | `ImmutableList<T>.Add`             | O(log `n`) |
| `List<T>.Item[Int32]`     | O(1)       | O(1)                      | `ImmutableList<T>.Item[Int32]`     | O(log `n`) |
| `List<T>.Enumerator`      | O(`n`)     | O(`n`)                    | `ImmutableList<T>.Enumerator`      | O(`n`)     |
| `HashSet<T>.Add`, lookup  | O(1)       | O(`n`)                    | `ImmutableHashSet<T>.Add`          | O(log `n`) |
| `SortedSet<T>.Add`        | O(log `n`) | O(`n`)                    | `ImmutableSortedSet<T>.Add`        | O(log `n`) |
| `Dictionary<T>.Add`       | O(1)       | O(`n`)                    | `ImmutableDictionary<T>.Add`       | O(log `n`) |
| `Dictionary<T>` lookup    | O(1)       | O(1) – oder strikt O(`n`) | `ImmutableDictionary<T>` lookup    | O(log `n`) |
| `SortedDictionary<T>.Add` | O(log `n`) | O(`n` log `n`)            | `ImmutableSortedDictionary<T>.Add` | O(log `n`) |

Eine `List<T>`-Klasse kann effizient mithilfe einer `for`-Schleife oder einer `foreach`-Schleife erstellt werden. Eine `ImmutableList<T>`-Klasse führt jedoch aufgrund der O(log `n`)-Zeit für ihren Indexer in einer `for`-Schleife zu schlechten Ergebnissen. Das Enumerieren einer `ImmutableList<T>`-Klasse mithilfe einer `foreach`-Schleife ist effizient, da `ImmutableList<T>` anstelle eines einfachen Arrays wie `List<T>` eine binäre Struktur verwendet, um die Daten zu speichern. Ein Array kann sehr schnell indiziert werden, wohingegen eine binäre Struktur durchlaufen werden muss, bis der Knoten mit dem gewünschten Index gefunden wird.

Außerdem ist `SortedSet<T>` genauso komplex wie `ImmutableSortedSet<T>`. Das liegt daran, dass beide binäre Strukturen verwenden. Der wesentliche Unterschied besteht darin, dass `ImmutableSortedSet<T>` eine unveränderliche binäre Struktur verwendet. Da `ImmutableSortedSet<T>` auch eine <xref:System.Collections.Immutable.ImmutableSortedSet%601.Builder?displayProperty=nameWithType>-Klasse bietet, die Mutation zulässt, können Sie sowohl von Unveränderlichkeit als auch von guten Leistungen profitieren.

<a name="BKMK_RelatedTopics"></a>
## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----------|-----------------|
|[Auswählen einer Auflistungsklasse](selecting-a-collection-class.md)|Beschreibt die verschiedenen Auflistungen und hilft Ihnen bei der Auswahl für Ihr Szenario.|
|[Häufig verwendete Auflistungstypen](commonly-used-collection-types.md)|Beschreibt häufig verwendete generische und nicht generische Auflistungstypen, z. B. <xref:System.Array?displayProperty=nameWithType>, <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> und <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.|
|[Verwenden von generischen Auflistungen](when-to-use-generic-collections.md)|Erörtert die Verwendung generischer Auflistungstypen.|
|[Vergleiche und Sortierungen innerhalb von Auflistungen](comparisons-and-sorts-within-collections.md)|Erläutert die Verwendung von Übereinstimmungs- und Sortiervergleichen in Auflistungen.|
|[Sortierte Auflistungstypen](sorted-collection-types.md)|Beschreibt die Leistung und die Merkmale von sortierten Auflistungen.|
|[Hashtable-Auflistungstyp und Dictionary-Auflistungstyp](hashtable-and-dictionary-collection-types.md)|Beschreibt die Funktionen von generischen und nicht generischen hashbasierten Wörterbuchtypen.|
|[Threadsichere Sammlungen](thread-safe/index.md)|Beschreibt Auflistungstypen wie <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> und <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>, die den sicheren und effizienten gleichzeitigen Zugriff von mehreren Threads unterstützen.|
|System.Collections.Immutable|Enthält einführende Informationen zu unveränderlichen Auflistungen und Links zu den Auflistungstypen.|

<a name="BKMK_Reference"></a>
## <a name="reference"></a>Referenz
<xref:System.Array?displayProperty=nameWithType>
<xref:System.Collections?displayProperty=nameWithType>
<xref:System.Collections.Concurrent?displayProperty=nameWithType>
<xref:System.Collections.Generic?displayProperty=nameWithType>
<xref:System.Collections.Specialized?displayProperty=nameWithType>
<xref:System.Linq?displayProperty=nameWithType>
<xref:System.Collections.Immutable>
