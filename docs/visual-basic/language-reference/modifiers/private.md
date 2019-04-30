---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: d6e28e5e87c3a88e4db3fc81177894683dbb0908
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920444"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte Programmierelemente nur aus ihrem Deklarationskontext einschließlich aus in alle enthaltenen Typen zugegriffen werden kann.  
  
## <a name="remarks"></a>Hinweise  
 Wenn ein Programmierelement proprietäre Funktionalität darstellt, oder vertrauliche Daten enthält, möchten Sie in der Regel den Zugriff darauf so stark wie möglich einschränken. Sie erreichen die Beschränkung auf maximal ermöglicht nur die Module, Klasse oder Struktur, die definiert, um darauf zuzugreifen. Um den Zugriff auf ein Element auf diese Weise beschränken, deklarieren Sie es mit `Private`.  

> [!NOTE]
> Sie können auch die [Private Protected](private-protected.md) Zugriffsmodifizierer, dadurch wird ein Element aus zugegriffen werden, in der betreffenden Klasse und von abgeleiteten Klassen, die sich in der enthaltenden Assembly befinden.

## <a name="rules"></a>Regeln  

- **Deklarationskontext.** Sie können `Private` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarationskontext für eine `Private` Element muss ein Modul, Klasse oder Struktur sein, und eine Quelldatei, Namespace, Schnittstelle oder Prozedur nicht möglich.  
  
## <a name="behavior"></a>Verhalten  
  
- **Zugriffsebene.** Sämtlichen Code innerhalb einer Deklarationskontext kann Zugriff auf seine `Private` Elemente. Dies schließt Code innerhalb eines enthaltenen Typs, z. B. eine geschachtelte Klasse oder eines Zuweisungsausdrucks in einer Enumeration. Kein Code außerhalb der Deklarationskontext kann Zugriff auf seine `Private` Elemente.  
  
- **Zugriffsmodifizierer.** Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*. Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Der `Private`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
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
- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private Protected](./private-protected.md)
- [Protected Friend](./protected-friend.md)[Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
