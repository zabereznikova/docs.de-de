---
ms.openlocfilehash: 9dada93c3330331064b7a944d97d61edb4dea299
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620252"
---
### <a name="listsort-algorithm-changed"></a>Der List.Sort-Algorithmus wurde geändert

#### <a name="details"></a>Details

Ab .NET Framework 4.5 wird als Sortieralgorithmus von <xref:System.Collections.Generic.List%601?displayProperty=fullName> nicht mehr Quicksort, sondern Introsort verwendet. Der Sortieralgorithmus von <xref:System.Collections.Generic.List%601?displayProperty=fullName> war noch nie stabil. Nun treten jedoch möglicherweise bei Sortiervorgängen in anderen Szenarios Instabilitäten auf. Das bedeutet, dass gleichwertige Elemente bei aufeinanderfolgenden Aufrufen der API in verschiedenen Reihenfolgen sortiert werden.

#### <a name="suggestion"></a>Vorschlag

Da der alte Sortieralgorithmus ebenfalls instabil war (wenn auch in anderer Hinsicht), sollte kein Code vorhanden sein, in dem gleichwertige Element immer in einer bestimmten Reihenfolge sortiert werden müssen. Wenn andere Codeinstanzen auf dieses Verhalten oder das alte Verhalten angewiesen sind, sollte dieser Code durch die Einführung einer Vergleichsfunktion aktualisiert werden, die die Elemente deterministisch in der gewünschten Reihenfolge sortiert.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Transparent|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li></ul>|
