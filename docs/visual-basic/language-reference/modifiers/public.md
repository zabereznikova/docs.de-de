---
title: Öffentlich
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 35332e50227cdef6386362df17c10b5b2cdaa689
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415348"
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
Gibt an, dass ein oder mehrere deklarierte Programmier Elemente über keine Zugriffs Einschränkungen verfügen.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn Sie eine Komponente oder eine Gruppe von Komponenten veröffentlichen (z. b. eine Klassenbibliothek), möchten Sie in der Regel von jedem Code, der mit der Assembly interagiert, auf die Programmier Elemente zugreifen können. Um einen solchen uneingeschränkten Zugriff auf ein Element zu gewähren, können Sie es mit deklarieren `Public` .  
  
 Der öffentliche Zugriff ist die normale Ebene für ein Programmier Element, wenn Sie den Zugriff darauf nicht einschränken müssen. Beachten Sie, dass die Zugriffsebene eines Elements, das innerhalb einer Schnittstelle, eines Moduls, einer Klasse oder einer Struktur deklariert ist, standardmäßig auf festgelegt ist, `Public` Wenn Sie es nicht andernfalls  
  
## <a name="rules"></a>Regeln  
  
- **Deklarationskontext.** Sie können `Public` nur auf der Ebene "Module", "Interface" oder "Namespace" verwenden. Dies bedeutet, dass der Deklarations Kontext für ein- `Public` Element eine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Klasse oder eine Struktur sein muss und keine Prozedur sein muss.  
  
## <a name="behavior"></a>Verhalten  
  
- **Zugriffsebene.** Sämtlicher Code, der auf ein Modul, eine Klasse oder eine Struktur zugreifen kann, kann auf seine `Public` Elemente zugreifen.  
  
- **Standard Zugriff.** Lokale Variablen innerhalb einer Prozedur werden standardmäßig auf den öffentlichen Zugriff fest, und Sie können keine Zugriffsmodifizierer verwenden.  
  
- **Zugriffsmodifizierer** Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet. Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
 Der `Public`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Class-Anweisung](../statements/class-statement.md)  
  
 [Const-Anweisung](../statements/const-statement.md)  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Delegate-Anweisung](../statements/delegate-statement.md)  
  
 [Dim-Anweisung](../statements/dim-statement.md)  
  
 [Enum-Anweisung](../statements/enum-statement.md)  
  
 [Event-Anweisung](../statements/event-statement.md)  
  
 [Function-Anweisung](../statements/function-statement.md)  
  
 [Interface-Anweisung](../statements/interface-statement.md)  
  
 [Module-Anweisung](../statements/module-statement.md)  
  
 [Operator Statement](../statements/operator-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Structure Statement](../statements/structure-statement.md)  
  
 [Sub-Anweisung](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Gebieten](protected.md)
- [Kollegen](friend.md)
- [Privat](private.md)
- [Privat geschützt](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Vorgehensweisen](../../programming-guide/language-features/procedures/index.md)
- [Strukturen](../../programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../programming-guide/language-features/objects-and-classes/index.md)
