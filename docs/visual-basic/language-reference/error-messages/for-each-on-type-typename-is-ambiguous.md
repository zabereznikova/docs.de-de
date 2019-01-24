---
title: '&#39;Für jede&#39; auf &#39; &lt;Typename&gt; &#39; ist mehrdeutig, da der Typ mehrere Instanziierungen von implementiert &#39;System.Collections.Generic.IEnumerable (Of T)&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 7fd779ba34afa2a59fa6c42971597df8ce01495a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597345"
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a>&#39;Für jede&#39; auf &#39; &lt;Typename&gt; &#39; ist mehrdeutig, da der Typ mehrere Instanziierungen von implementiert &#39;System.Collections.Generic.IEnumerable (Of T)&#39;
Ein `For Each` -Anweisung gibt eine Iteratorvariable, die mehr als eine <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode.  
  
 Die Iteratorvariable muss von einem Typ sein, die implementiert die <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> Schnittstelle in einer der der `Collections` Namespaces und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Es ist möglich, dass eine Klasse, um mehr als eine konstruierte generische Schnittstelle, über ein anderes Typargument für jeden Erstellung zu implementieren. Wenn eine Klasse, die ihn durchführt, die für die Iteratorvariable verwendet wird, wird diese Variable hat mehr als ein <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode. In diesem Fall können Visual Basic die aufzurufende Methode nicht auswählen.  
  
 **Fehler-ID:** BC32096  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) oder [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) umzuwandelnde den Typ der Iteratorvariablen auf die Schnittstelle zum Definieren der <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode, die Sie verwenden möchten.  
  
## <a name="see-also"></a>Siehe auch
- [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
