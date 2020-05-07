---
title: Verwenden von generischen Auflistungen
ms.date: 04/30/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- collections [.NET Framework], generic
- generic collections [.NET Framework]
ms.assetid: e7b868b1-11fe-4ac5-bed3-de68aca47739
ms.openlocfilehash: feccd8c53e5171889666ed407258b9d36ad8a140
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728197"
---
# <a name="when-to-use-generic-collections"></a>Verwenden von generischen Sammlungen

Das Verwenden von generischen Sammlungen bietet den unmittelbaren Vorteil von Typsicherheit, ohne typenspezifische Member von einem Basissammlungstyp ableiten und implementieren zu müssen. Generische Sammlungstypen bieten allgemein auch eine bessere Leistung als die entsprechenden nicht generischen Sammlungstypen (und besser als Typen, die von nicht generischen Basissammlungstypen abgeleitet sind), wenn die Sammlungselemente Werttypen sind, da bei Generics keine Notwendigkeit zum Einschließen der Elemente besteht.

Für Programme, die auf .NET Standard 1.0 oder höher abzielen, sollten Sie die generischen Auflistungsklasse im <xref:System.Collections.Concurrent>-Namespace verwenden, wenn mehrere Threads möglicherweise Elemente gleichzeitig der Auflistung hinzufügen oder daraus entfernen. Wenn außerdem Unveränderlichkeit gewünscht ist, sollten Sie die generischen Auflistungsklasse im Namespace <xref:System.Collections.Immutable> in Erwägung ziehen.

Die folgenden generischen Typen entsprechen vorhandenen Auflistungstypen:

- <xref:System.Collections.Generic.List%601> ist die generische Klasse, die <xref:System.Collections.ArrayList>entspricht.

- <xref:System.Collections.Generic.Dictionary%602> und <xref:System.Collections.Concurrent.ConcurrentDictionary%602> sind die generischen Klassen, die <xref:System.Collections.Hashtable>entsprechen.

- <xref:System.Collections.ObjectModel.Collection%601> ist die generische Klasse, die <xref:System.Collections.CollectionBase>entspricht. <xref:System.Collections.ObjectModel.Collection%601> kann als Basisklasse verwendet werden, ist aber im Gegensatz zu <xref:System.Collections.CollectionBase> nicht abstrakt und daher viel einfacher zu verwenden.

- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> ist die generische Klasse, die <xref:System.Collections.ReadOnlyCollectionBase>entspricht. <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> ist nicht abstrakt und verfügt über einen Konstruktor, der es einfach macht, eine vorhandene <xref:System.Collections.Generic.List%601> als schreibgeschützte Auflistung verfügbar zu machen.

- Die generischen Klassen <xref:System.Collections.Generic.Queue%601>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, <xref:System.Collections.Immutable.ImmutableQueue%601>, <xref:System.Collections.Immutable.ImmutableArray%601>, <xref:System.Collections.Generic.SortedList%602> und <xref:System.Collections.Immutable.ImmutableSortedSet%601> entsprechen den jeweiligen nicht generischen Klassen mit denselben Namen.

## <a name="additional-types"></a>Zusätzliche Typen

Einige generische Auflistungstypen haben keine nicht generischen Entsprechungen. Hierzu gehören Folgende:

- <xref:System.Collections.Generic.LinkedList%601> ist eine vielfältig einsetzbare verknüpfte Liste, die O(1)-Einfüge- und Löschvorgänge bereitstellt.

- <xref:System.Collections.Generic.SortedDictionary%602> ist ein sortiertes Wörterbuch mit O(log `n`)-Einfüge- und Abrufvorgängen – eine nützliche Alternative zu <xref:System.Collections.Generic.SortedList%602>.

- <xref:System.Collections.ObjectModel.KeyedCollection%602> ist eine Mischung aus Liste und Wörterbuch und bietet eine Möglichkeit, Objekte zu speichern, die ihre eigenen Schlüssel enthalten.

- <xref:System.Collections.Concurrent.BlockingCollection%601> implementiert eine Auflistungsklasse mit Begrenzungs- und Blockadefunktionen.

- <xref:System.Collections.Concurrent.ConcurrentBag%601> ermöglicht das schnelle Einfügen und Entfernen unsortierter Elemente.

### <a name="immutable-builders"></a>Unveränderliche Generatoren

Wenn Sie in Ihrer App Unveränderlichkeitsfunktionen wünschen, bietet der Namespace <xref:System.Collections.Immutable> generische Auflistungstypen, die Sie verwenden können. Alle unveränderlichen Auflistungstypen bieten `Builder`-Klassen, die die Leistung optimieren können, wenn Sie mehrere Mutationen ausführen. Die `Builder`-Klasse wendet Batches auf Vorgänge in einem veränderlichen Zustand an. Wenn alle Mutationen abgeschlossen sind, rufen Sie die `ToImmutable`-Methode auf, um alle Knoten zu „fixieren“, und erstellen Sie eine unveränderliche generische Auflistung, zum Beispiel eine <xref:System.Collections.Immutable.ImmutableList%601>.

Das `Builder`-Objekt kann durch Aufruf der nicht generischen `CreateBuilder()`-Methode erstellt werden. Über eine `Builder`-Instanz können Sie `ToImmutable()` aufrufen. Ebenso können Sie über die `Immutable*`-Auflistung `ToBuilder()` aufrufen, um eine Generator-Instanz aus der generischen unveränderlichen Auflistung zu erstellen. Folgende Typen sind unterschiedliche `Builder`-Typen.

- <xref:System.Collections.Immutable.ImmutableArray%601.Builder>
- <xref:System.Collections.Immutable.ImmutableDictionary%602.Builder>
- <xref:System.Collections.Immutable.ImmutableHashSet%601.Builder>
- <xref:System.Collections.Immutable.ImmutableList%601.Builder>
- <xref:System.Collections.Immutable.ImmutableSortedDictionary%602.Builder>
- <xref:System.Collections.Immutable.ImmutableSortedSet%601.Builder>

## <a name="linq-to-objects"></a>LINQ to Objects

Mit der LINQ to Objects-Funktion können Sie LINQ-Abfragen für den Zugriff auf Objekte im Arbeitsspeicher verwenden, solange der Objekttyp die <xref:System.Collections.IEnumerable?displayProperty=nameWithType> - oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> -Schnittstelle implementiert. LINQ-Abfragen bieten ein allgemeines Muster für den Datenzugriff, sind normalerweise präziser und besser lesbar als standardmäßige `foreach`-Schleifen und stellen Filter-, Sortier- und Gruppierungsfunktionen bereit. LINQ-Abfragen können auch die Leistung verbessern. Weitere Informationen finden Sie unter [LINQ to Objects (C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md), [LINQ to Objects (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) und [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md).

## <a name="additional-functionality"></a>Zusätzliche Funktionen
Einige der generischen Typen besitzen Funktionen, die es in den nicht generischen Auflistungstypen nicht gibt. Die <xref:System.Collections.Generic.List%601> -Klasse, die der nicht generischen <xref:System.Collections.ArrayList> -Klasse entspricht, hat z. B. eine Reihe von Methoden, die generische Delegaten akzeptieren, z. B. den <xref:System.Predicate%601> -Delegaten, mit dem Sie Methoden zum Durchsuchen der Liste angeben können, den <xref:System.Action%601> -Delegaten, der Methoden für die einzelnen Listenelemente darstellt, und den <xref:System.Converter%602> -Delegaten, mit dem Sie Konvertierungen zwischen Typen definieren können.

Mit der <xref:System.Collections.Generic.List%601> -Klasse können Sie Ihre eigenen generischen <xref:System.Collections.Generic.IComparer%601> -Schnittstellenimplementierungen zum Sortieren und Durchsuchen der Liste angeben. Die Klassen <xref:System.Collections.Generic.SortedDictionary%602> und <xref:System.Collections.Generic.SortedList%602> verfügen ebenfalls über diese Funktion. Darüber hinaus ermöglichen Ihnen diese Klassen das Angeben von Vergleichen beim Erstellen der Auflistung. In ähnlicher Weise können Sie mit den Klassen <xref:System.Collections.Generic.Dictionary%602> und <xref:System.Collections.ObjectModel.KeyedCollection%602> eigene Gleichheitsvergleiche angeben.

## <a name="see-also"></a>Siehe auch

- [Sammlungen und Datenstrukturen](../../../docs/standard/collections/index.md)
- [Häufig verwendete Auflistungstypen](../../../docs/standard/collections/commonly-used-collection-types.md)
- [Generics](../../../docs/standard/generics/index.md)
