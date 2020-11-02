---
title: Vergleiche und Sortierungen innerhalb von Sammlungen
description: Führen Sie Vergleiche und Sortierungen mithilfe der System.Collections-Klassen in .NET durch, die dabei helfen, ein Element zu finden, das entfernt werden soll, oder den Wert eines Schlüssel-Wert-Paars zurückzugeben.
ms.date: 04/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data, collections
- IComparable.CompareTo method
- Collections classes
- Equals method
- collections [.NET], comparisons
ms.assetid: 5e4d3b45-97f0-423c-a65f-c492ed40e73b
ms.openlocfilehash: 40a59809723298ddda21e642098ec8ae74a1828b
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889373"
---
# <a name="comparisons-and-sorts-within-collections"></a>Vergleiche und Sortierungen innerhalb von Auflistungen

Die <xref:System.Collections>-Klassen führen bei nahezu allen Vorgängen zur Verwaltung von Auflistungen Vergleiche durch, sei es bei der Suche nach zu entfernenden Elementen oder bei der Rückgabe eines Schlüssel-Wert-Paars.

Auflistungen verwenden in der Regel einen Gleichheitsvergleich und/oder einen Reihenfolgenvergleich. Für Vergleiche werden zwei Konstrukte verwendet.

<a name="BKMK_Checkingforequality"></a>
## <a name="check-for-equality"></a>Durchführen von Gleichheitsüberprüfungen

Methoden wie `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>und `Remove` verwenden einen Gleichheitsvergleich für die Elemente der Auflistung. Wenn die Sammlung generisch ist, werden die Elemente anhand der folgenden Richtlinien auf Gleichheit verglichen:

- Wenn Typ T die generische Schnittstelle <xref:System.IEquatable%601> implementiert, dann ist der Gleichheitsvergleich die <xref:System.IEquatable%601.Equals%2A> -Methode dieser Schnittstelle.

- Wenn der Typ T <xref:System.IEquatable%601>nicht implementiert, wird <xref:System.Object.Equals%2A?displayProperty=nameWithType> verwendet.

Darüber hinaus akzeptieren einige Konstruktorüberladungen für Wörterbuchauflistungen eine <xref:System.Collections.Generic.IEqualityComparer%601> -Implementierung, die zum Vergleichen von Schlüsseln auf Gleichheit verwendet wird. Ein Beispiel dafür finden Sie unter <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A> -Konstruktor.

<a name="BKMK_Determiningsortorder"></a>
## <a name="determine-sort-order"></a>Festlegen der Sortierreihenfolge

Methoden, wie `BinarySearch` und `Sort` , verwenden einen Reihenfolgenvergleich für Elemente der Auflistung. Die Vergleiche können zwischen Elementen in der Auflistung oder zwischen einem Element und einem angegebenen Wert durchgeführt werden. Für den Vergleich von Objekten gibt es die Konzepte `default comparer` und `explicit comparer`.

Der Standardvergleich beruht auf dem Vergleich von mindestens einem Objekt, um die **IComparable** -Schnittstelle zu implementieren. Es ist empfehlenswert, **IComparable** in allen Klassen zu implementieren, die als Werte in einer Listenauflistung oder als Schlüssel in einer Wörterbuchauflistung verwendet werden. Bei einer generischen Auflistung wird der Gleichheitsvergleich gemäß dem Folgenden bestimmt:

- Wenn Typ T die generische Schnittstelle <xref:System.IComparable%601?displayProperty=nameWithType> implementiert, dann ist der Standardvergleich die <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> -Methode dieser Schnittstelle.

- Wenn Typ T die nicht generische Schnittstelle <xref:System.IComparable?displayProperty=nameWithType> implementiert, dann ist der Standardvergleich die <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> -Methode dieser Schnittstelle.

- Wenn Typ T keine der Schnittstellen implementiert, gibt es keinen Standardvergleich, und ein Vergleich oder ein Vergleichsdelegat muss explizit angegeben werden.

Um explizite Vergleiche zu ermöglichen, akzeptieren einige Methoden eine **IComparer** -Implementierung als Parameter. Beispiel: Die <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> -Methode akzeptiert eine <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> -Implementierung.

Die aktuelle Kultureinstellung des Systems kann sich auf die Vergleichs- und Sortiervorgänge innerhalb einer Auflistung auswirken. Standardmäßig sind die Vergleichs- und Sortiervorgänge in den **Auflistungen** -Klassen kulturabhängig. Um die Kultureinstellung zu ignorieren und daher konsistente Vergleichs- und Sortierergebnisse zu erhalten, verwenden Sie <xref:System.Globalization.CultureInfo.InvariantCulture%2A> mit Memberüberladungen, die <xref:System.Globalization.CultureInfo>akzeptieren. Weitere Informationen finden Sie unter [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Auflistungen](../globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) und [Durchführen kulturunabhängiger Zeichenfolgenoperationen in Arrays](../globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).

<a name="BKMK_Equalityandsortexample"></a>
## <a name="equality-and-sort-example"></a>Beispiel für Gleichheit und Sortierung

Der folgende Code zeigt eine Implementierung von <xref:System.IEquatable%601> und <xref:System.IComparable%601> für ein einfaches Geschäftsobjekt. Wenn das Objekt in einer Liste gespeichert und sortiert wird, sehen Sie darüber hinaus, dass durch den Aufruf der <xref:System.Collections.Generic.List%601.Sort>-Methode der Standardvergleich für den `Part`-Typ verwendet wird und die <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29>-Methode mit einer anonymen Methode implementiert wird.

[!code-csharp[System.Collections.Generic.List.Sort#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.collections.generic.list.sort/cs/program.cs#1)]
[!code-vb[System.Collections.Generic.List.Sort#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.collections.generic.list.sort/vb/module1.vb#1)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.IComparer>
- <xref:System.IEquatable%601>
- <xref:System.Collections.Generic.IComparer%601>
- <xref:System.IComparable>
- <xref:System.IComparable%601>
