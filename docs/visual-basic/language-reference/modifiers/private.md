---
title: Privat
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 59f1c1666ce38923a2861244fb377007cd0fa992
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874985"
---
# <a name="private-visual-basic"></a>Private (Visual Basic)

Gibt an, dass auf ein oder mehrere deklarierte Programmier Elemente nur innerhalb Ihres Deklarations Kontexts zugegriffen werden kann, einschließlich aus allen enthaltenen Typen.  
  
## <a name="remarks"></a>Bemerkungen  

 Wenn ein Programmier Element proprietäre Funktionen darstellt oder vertrauliche Daten enthält, sollten Sie den Zugriff auf das Element in der Regel so streng wie möglich einschränken. Die maximale Beschränkung erreichen Sie, indem nur das Modul, die Klasse oder die Struktur, die das Modul definiert, für den Zugriff zugelassen wird. Um den Zugriff auf ein Element auf diese Weise einzuschränken, können Sie es mit deklarieren `Private` .  

> [!NOTE]
> Sie können auch den [privaten geschützten](private-protected.md) Zugriffsmodifizierer verwenden, wodurch ein Member innerhalb dieser Klasse und aus abgeleiteten Klassen, die sich in der enthaltenden Assembly befinden, zugänglich ist.

## <a name="rules"></a>Regeln  

- **Deklarationskontext.** Sie können `Private` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein- `Private` Element ein Modul, eine Klasse oder eine Struktur sein muss und nicht eine Quelldatei, ein Namespace, eine Schnittstelle oder eine Prozedur sein darf.  
  
## <a name="behavior"></a>Verhalten  
  
- **Zugriffsebene.** Der gesamte Code in einem Deklarations Kontext kann auf seine `Private` Elemente zugreifen. Dies schließt Code in einem enthaltenen Typ ein, z. b. eine geschachtelte Klasse oder einen Zuweisungs Ausdruck in einer Enumeration. Kein Code außerhalb des Deklarations Kontexts kann auf seine `Private` Elemente zugreifen.  
  
- **Zugriffsmodifizierer** Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet. Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
 Der `Private`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Class-Anweisung](../statements/class-statement.md)  
  
 [Const-Anweisung](../statements/const-statement.md)  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Delegate-Anweisung](../statements/delegate-statement.md)  
  
 [Dim-Anweisung](../statements/dim-statement.md)  
  
 [Enum-Anweisung](../statements/enum-statement.md)  
  
 [Event-Anweisung](../statements/event-statement.md)  
  
 [Function-Anweisung](../statements/function-statement.md)  
  
 [Interface-Anweisung](../statements/interface-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Structure Statement](../statements/structure-statement.md)  
  
 [Sub-Anweisung](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Öffentlich](public.md)
- [Gebieten](protected.md)
- [Friend](friend.md)
- [Privat geschützt](./private-protected.md)
- [Protected Friend](./protected-friend.md)
- [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Vorgehensweisen](../../programming-guide/language-features/procedures/index.md)
- [Strukturen](../../programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../programming-guide/language-features/objects-and-classes/index.md)
