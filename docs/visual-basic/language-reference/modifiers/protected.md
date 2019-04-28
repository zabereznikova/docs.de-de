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
ms.openlocfilehash: 88e13fcd03c6a10cf1450cec90f9ca60aedc3eb1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778711"
---
# <a name="protected-visual-basic"></a>Protected (Visual Basic)
Ein Zugriffsmodifizierer für Member, der angibt, dass eine oder mehrere Programmierelemente deklarierte sind nur von innerhalb ihrer eigenen Klasse oder von einer abgeleiteten Klasse zugegriffen werden.  
  
## <a name="remarks"></a>Hinweise  
 Manchmal enthält ein Programmierelement, das in einer Klasse deklariert, vertrauliche Daten oder eingeschränkten Code, und Sie Zugriff auf das Element einschränken möchten. Wenn die Klasse geerbt wird, und Sie erwarten, eine Hierarchie von abgeleiteten Klassen dass, sie für diese abgeleiteten Klassen Zugriff auf die Daten oder Code erforderlich sind möglicherweise jedoch. In diesem Fall möchten Sie das Element, das sowohl von der Basisklasse als auch von allen abgeleiteten Klassen zugegriffen werden. Um den Zugriff auf ein Element auf diese Weise beschränken, deklarieren Sie es mit `Protected`.  

> [!NOTE]
> Die `Protected` Zugriffsmodifizierer mit zwei andere Modifizierer kombiniert werden kann:
> - Die [Protected Friend](protected-friend.md) Modifizierer macht einen Klassenmember kann innerhalb dieser Klasse, aus der gleichen Assembly, die in der die Klasse definiert ist und von abgeleiteten Klassen zugegriffen werden. 
> - Die [Private Protected](private-protected.md) Modifizierer macht einen Klassenmember von abgeleiteten Typen, jedoch nur innerhalb der enthaltenden Assembly zugegriffen werden kann.
  
## <a name="rules"></a>Regeln  
  
- **Deklarationskontext.** Sie können `Protected` nur auf Klassenebene. Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.  

## <a name="behavior"></a>Verhalten  
  
- **Zugriffsebene.** Gesamten Code in einer Klasse kann Zugriff auf die Elemente auf. Code in einer Klasse, die von einer Basisklasse abgeleitet wird, kann auf alle zugreifen der `Protected` Elemente der Basisklasse. Dies gilt für alle Generationen der Ableitung. Dies bedeutet, dass der Zugriff auf eine Klasse kann `Protected` Elemente der Basisklasse der Basisklasse und So weiter.  
  
     Geschützter Zugriff ist nicht auf, eine Obermenge oder eine Teilmenge der Friend-Zugriff.  
  
- **Zugriffsmodifizierer.** Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*. Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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

- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
