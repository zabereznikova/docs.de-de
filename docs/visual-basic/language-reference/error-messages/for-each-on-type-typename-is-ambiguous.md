---
title: "\"For Each\" für den <typename>-Typ ist mehrdeutig, da der Typ mehrere Instanziierungen von System.Collections.Generic.IEnumerable(Of T) implementiert."
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 6c34ca43decc3c5d8c72b529d8f51d7cc3b0c6b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801464"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a>"For Each" für Typ '\<Typname >' ist mehrdeutig, da der Typ mehrere Instanziierungen von "System.Collections.Generic.IEnumerable (Of T)" implementiert.
Ein `For Each` -Anweisung gibt eine Iteratorvariable, die mehr als eine <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode.  
  
 Die Iteratorvariable muss von einem Typ sein, die implementiert die <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> Schnittstelle in einer der der `Collections` Namespaces und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Es ist möglich, dass eine Klasse, um mehr als eine konstruierte generische Schnittstelle, über ein anderes Typargument für jeden Erstellung zu implementieren. Wenn eine Klasse, die ihn durchführt, die für die Iteratorvariable verwendet wird, wird diese Variable hat mehr als ein <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode. In diesem Fall können Visual Basic die aufzurufende Methode nicht auswählen.  
  
 **Fehler-ID:** BC32096  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden Sie [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) oder [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) umzuwandelnde den Typ der Iteratorvariablen auf die Schnittstelle zum Definieren der <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode, die Sie verwenden möchten.  
  
## <a name="see-also"></a>Siehe auch

- [For Each...Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
