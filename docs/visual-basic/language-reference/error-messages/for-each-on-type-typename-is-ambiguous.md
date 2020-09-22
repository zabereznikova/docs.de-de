---
title: "\"For Each\" für den <typename>-Typ ist mehrdeutig, da der Typ mehrere Instanziierungen von System.Collections.Generic.IEnumerable(Of T) implementiert."
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: d04a77291ecf09f88ad189667540e9e353246f28
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874081"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a>"For Each" für den \<typename>-Typ ist mehrdeutig, da der Typ mehrere Instanziierungen von System.Collections.Generic.IEnumerable(Of T) implementiert.

Eine- `For Each` Anweisung gibt eine Iteratorvariable an, die über mehr als eine <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode verfügt.  
  
 Die Iteratorvariable muss einen Typ aufweisen, der die- <xref:System.Collections.IEnumerable?displayProperty=nameWithType> Schnittstelle oder die- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> Schnittstelle in einem der `Collections` Namespaces des .NET Framework implementiert. Es ist möglich, dass eine Klasse mehr als eine konstruierte generische Schnittstelle implementiert, wobei für jede Konstruktion ein anderes Typargument verwendet wird. Wenn eine Klasse, die diese verwendet, für die Iteratorvariable verwendet wird, hat diese Variable mehr als eine <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode. In einem solchen Fall können Visual Basic nicht auswählen, welche Methode aufgerufen werden soll.  
  
 **Fehler-ID:** BC32096  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden Sie den [DirectCast-Operator](../operators/directcast-operator.md) oder den [TryCast-Operator](../operators/trycast-operator.md) , um den iteratorvariablentyp in die-Schnittstelle umzuwandeln, die die <xref:System.Collections.IEnumerable.GetEnumerator%2A> gewünschte Methode definiert.  
  
## <a name="see-also"></a>Weitere Informationen

- [For Each...Next-Anweisung](../statements/for-each-next-statement.md)
- [Schnittstellen](../../programming-guide/language-features/interfaces/index.md)
