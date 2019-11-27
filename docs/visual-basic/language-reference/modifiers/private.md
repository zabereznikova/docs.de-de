---
title: Privat
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 5600744aeca79a54f51a1f9ecd0ef00fed4b00fd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351329"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)
Gibt an, dass auf ein oder mehrere deklarierte Programmier Elemente nur innerhalb Ihres Deklarations Kontexts zugegriffen werden kann, einschließlich aus allen enthaltenen Typen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn ein Programmier Element proprietäre Funktionen darstellt oder vertrauliche Daten enthält, sollten Sie den Zugriff auf das Element in der Regel so streng wie möglich einschränken. Die maximale Beschränkung erreichen Sie, indem nur das Modul, die Klasse oder die Struktur, die das Modul definiert, für den Zugriff zugelassen wird. Um den Zugriff auf ein Element auf diese Weise einzuschränken, können Sie es mit `Private`deklarieren.  

> [!NOTE]
> Sie können auch den [privaten geschützten](private-protected.md) Zugriffsmodifizierer verwenden, wodurch ein Member innerhalb dieser Klasse und aus abgeleiteten Klassen, die sich in der enthaltenden Assembly befinden, zugänglich ist.

## <a name="rules"></a>Regeln  

- **Deklarations Kontext.** Sie können `Private` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein `Private` Element ein Modul, eine Klasse oder eine Struktur sein muss und weder eine Quelldatei noch ein Namespace, eine Schnittstelle oder eine Prozedur sein darf.  
  
## <a name="behavior"></a>Verhalten  
  
- **Zugriffsebene.** Der gesamte Code in einem Deklarations Kontext kann auf seine `Private` Elemente zugreifen. Dies schließt Code in einem enthaltenen Typ ein, z. b. eine geschachtelte Klasse oder einen Zuweisungs Ausdruck in einer Enumeration. Kein Code außerhalb des Deklarations Kontexts kann auf seine `Private` Elemente zugreifen.  
  
- **Zugriffsmodifizierer** Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet. Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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
- Zugriffsebenen [geschützter Freunde](./protected-friend.md)[in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
