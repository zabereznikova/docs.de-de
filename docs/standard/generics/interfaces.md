---
title: Generische Schnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- generic interfaces [.NET]
- equality comparisons [.NET]
- generics [.NET], interfaces
- ordering comparisons [.NET]
ms.assetid: 88bf5b04-d371-4edb-ba38-01ec7cabaacf
ms.openlocfilehash: 429aa3c4d48fa6805b498206bcb699b56f522409
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827190"
---
# <a name="generic-interfaces"></a>Generische Schnittstellen

Dieser Artikel bietet einen Überblick über generische Schnittstellen, die allgemeine Funktionen für Familien generischer Typen bereitstellen.  
  
Generische Schnittstellen bieten typsichere Entsprechungen zu nicht generischen Schnittstellen für Reihenfolgen- und Übereinstimmungsvergleiche sowie für Funktionen, die von generischen Auflistungstypen gemeinsam verwendet werden.  
  
> [!NOTE]
> Die Typparameter mehrerer generischer Schnittstellen sind als kovariant oder kontravariant gekennzeichnet. Dies bietet mehr Flexibilität beim Zuweisen und Verwenden von Typen, die diese Schnittstellen implementieren. Siehe [Kovarianz und Kontravarianz](covariance-and-contravariance.md).  
  
## <a name="equality-and-ordering-comparisons"></a>Übereinstimmungs- und Reihenfolgenvergleiche  
 Im <xref:System>-Namespace definieren die generische <xref:System.IComparable%601?displayProperty=nameWithType>-Schnittstelle und die generische <xref:System.IEquatable%601?displayProperty=nameWithType>-Schnittstelle (wie ihre nicht generischen Entsprechungen) Methoden für Reihenfolgen- bzw. Übereinstimmungsvergleiche. Typen implementieren diese Schnittstellen, um die Durchführungsfähigkeit für solche Vergleiche zu bieten.  
  
 Im <xref:System.Collections.Generic>-Namespace bieten die generische <xref:System.Collections.Generic.IComparer%601>-Schnittstelle und die generische <xref:System.Collections.Generic.IEqualityComparer%601>-Schnittstelle eine Möglichkeit zum Definieren von Reihenfolgen- oder Übereinstimmungsvergleichen für Typen, die die generische <xref:System.IComparable%601?displayProperty=nameWithType>- oder <xref:System.IEquatable%601?displayProperty=nameWithType>-Schnittstelle nicht implementieren, und sie bieten auch eine Möglichkeit, diese Beziehungen für Typen erneut zu definieren, die diese Schnittstellen implementieren. Diese Schnittstellen werden von Methoden und Konstruktoren vieler generischer Auflistungsklassen verwendet. Sie können beispielsweise ein generisches <xref:System.Collections.Generic.IComparer%601>-Objekt an den Konstruktor der <xref:System.Collections.Generic.SortedDictionary%602>-Klasse übergeben, um eine Sortierreihenfolge für einen Typ anzugeben, der keine generischen <xref:System.IComparable%601?displayProperty=nameWithType>-Schnittstellen implementiert. Für die generische statische <xref:System.Array.Sort%2A?displayProperty=nameWithType>-Methode und für die <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType>-Instanzmethode sind Überladungen zum Sortieren von Arrays und Listen mithilfe der generischen <xref:System.Collections.Generic.IComparer%601>-Implementierungen vorhanden.  
  
 Die generischen Klassen <xref:System.Collections.Generic.Comparer%601> und <xref:System.Collections.Generic.EqualityComparer%601> stellen Basisklassen für Implementierungen der generischen Schnittstellen <xref:System.Collections.Generic.IComparer%601> und <xref:System.Collections.Generic.IEqualityComparer%601> sowie standardmäßige Reihenfolgen- und Übereinstimmungsvergleiche mithilfe der <xref:System.Collections.Generic.Comparer%601.Default%2A?displayProperty=nameWithType>-Eigenschaft bzw. der <xref:System.Collections.Generic.EqualityComparer%601.Default%2A?displayProperty=nameWithType>-Eigenschaft bereit.  
  
## <a name="collection-functionality"></a>Auflistungsfunktionen  
 Die generische <xref:System.Collections.Generic.ICollection%601>-Schnittstelle ist die Basisschnittstelle für generische Auflistungstypen. Sie stellt grundlegende Funktionen zum Hinzufügen, Entfernen, Kopieren und Auflisten von Elementen bereit. <xref:System.Collections.Generic.ICollection%601> erbt sowohl von der generischen <xref:System.Collections.Generic.IEnumerable%601> als auch von der nicht generischen <xref:System.Collections.IEnumerable>.  
  
 Die generische <xref:System.Collections.Generic.IList%601>-Schnittstelle erweitert die generische <xref:System.Collections.Generic.ICollection%601>-Schnittstelle um Methoden für den indizierten Abruf.  
  
 Die generische <xref:System.Collections.Generic.IDictionary%602>-Schnittstelle erweitert die generische <xref:System.Collections.Generic.ICollection%601>-Schnittstelle um Methoden für den Abruf anhand von Schlüsseln. Generische Wörterbuchtypen in der .NET-Basisklassenbibliothek implementieren auch die nicht generische Schnittstelle <xref:System.Collections.IDictionary>.  
  
 Die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle stellt eine generische Enumeratorstruktur bereit. Die generische <xref:System.Collections.Generic.IEnumerator%601>-Schnittstelle, die von generischen Enumeratoren implementiert wird, erbt die nicht generische <xref:System.Collections.IEnumerator>-Schnittstelle. Die Member <xref:System.Collections.IEnumerator.MoveNext%2A> und <xref:System.Collections.IEnumerator.Reset%2A>, die nicht vom `T`-Typparameter abhängig sind, sind nur für die nicht generische Schnittstelle vorhanden. Dies bedeutet, dass jeder Consumer der nicht generischen Schnittstelle auch die generische Schnittstelle verwenden kann.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel?displayProperty=nameWithType>
- [Generics](index.md)
- [Generische Sammlungen in .NET](collections.md)
- [Generische Delegaten zum Bearbeiten von Arrays und Listen](delegates-for-manipulating-arrays-and-lists.md)
- [Kovarianz und Kontravarianz](covariance-and-contravariance.md)
