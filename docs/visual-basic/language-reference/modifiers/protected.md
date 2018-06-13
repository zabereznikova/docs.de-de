---
title: Protected (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 5f279ed0a33840bb1f2321c17a1ffba412837c07
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234756"
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)
Zugriffsmodifizierer für einen Member, der angibt, dass eine oder mehrere Programmierelemente deklariert werden nur von ihrer eigenen Klasse oder von einer abgeleiteten Klasse zugegriffen werden.  
  
## <a name="remarks"></a>Hinweise  
 Manchmal enthält ein Programmierelement in einer Klasse deklariert, vertrauliche Daten oder eingeschränkten Code, und Sie den Zugriff auf das Element einschränken möchten. Jedoch wenn die Klasse vererbbar ist, und Sie erwarten, eine Hierarchie von abgeleiteten Klassen dass, es für diese abgeleiteten Klassen den Zugriff auf die Daten oder Code möglicherweise erforderlich. In einem solchen Fall möchten Sie das Element aus der Basisklasse und aus allen abgeleiteten Klassen zugegriffen werden kann. Um den Zugriff auf ein Element auf diese Weise beschränken möchten, deklarieren Sie es mit `Protected`.  

> [!NOTE]
> Die `Protected` Zugriffsmodifizierer mit zwei weiteren Modifizierer kombiniert werden kann:
> - Die [Protected Friend](protected-friend.md) Modifizierer macht einen Klassenmember aus zugegriffen werden, in der betreffenden Klasse, die von abgeleiteten Klassen und aus der gleichen Assembly, in dem die Klasse definiert ist. 
> - Die [Private geschützte](private-protected.md) Modifizierer macht einen Klassenmember von abgeleiteten Typen, jedoch nur innerhalb der enthaltenden Assembly zugegriffen werden kann.
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Sie können `Protected` nur auf Klassenebene. Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.  

## <a name="behavior"></a>Verhalten  
  
-   **Zugriffsebene.** Der gesamte Code in einer Klasse kann ihre Elemente zugreifen. Code in einer Klasse, die von einer Basisklasse abgeleitet ist, kann auf alle zugreifen die `Protected` Elemente der Basisklasse. Dies gilt für alle Generationen der Ableitung. Dies bedeutet, dass eine Klasse zugreifen kann `Protected` Elemente der Basisklasse der Basisklasse und So weiter.  
  
     Geschützter Zugriff ist eine Obermenge oder eine Teilmenge der Friend-Zugriff.  
  
-   **Zugriffsmodifizierer.** Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*. Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Der `Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Geschützt privat](private-protected.md)   
 [Protected Friend](protected-friend.md)   
 [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
