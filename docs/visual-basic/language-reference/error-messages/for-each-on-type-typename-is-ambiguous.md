---
title: '&#39;Für jede&#39; für den Typ &#39; &lt;Typename&gt; &#39; ist mehrdeutig, da der Typ mehrere Instanziierungen von implementiert &#39;System.Collections.Generic.IEnumerable (Of T)&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 8c48a7134eb8da83fb418b9aa91d55dcbe8e8bcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590964"
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a>&#39;Für jede&#39; für den Typ &#39; &lt;Typename&gt; &#39; ist mehrdeutig, da der Typ mehrere Instanziierungen von implementiert &#39;System.Collections.Generic.IEnumerable (Of T)&#39;
Ein `For Each` -Anweisung gibt eine Iteratorvariable, die weist mehr als eine <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode.  
  
 Die Iteratorvariable muss ein Typ, implementiert der <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> Schnittstelle in einer der der `Collections` Namespaces und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Es ist möglich, dass eine Klasse, um ein anderes Typargument für jeden Konstruktion mit mehr als eine konstruierte generische-Schnittstelle implementieren. Wenn eine Klasse, die dies tut, für die Iteratorvariable verwendet wird, wird diese Variable hat mehr als ein <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode. In einem solchen Fall können Visual Basic die aufzurufende Methode nicht auswählen.  
  
 **Fehler-ID:** BC32096  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) oder [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) umwandeln den Iterator Variablentyp auf die Schnittstelle zum Definieren der <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode, die Sie verwenden möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
