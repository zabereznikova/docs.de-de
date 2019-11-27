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
ms.openlocfilehash: 35bf1a65e0b8f24a1263adc480719c69b95dff9b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351293"
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
Gibt an, dass ein oder mehrere deklarierte Programmier Elemente über keine Zugriffs Einschränkungen verfügen.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie eine Komponente oder eine Gruppe von Komponenten veröffentlichen (z. b. eine Klassenbibliothek), möchten Sie in der Regel von jedem Code, der mit der Assembly interagiert, auf die Programmier Elemente zugreifen können. Um einen solchen uneingeschränkten Zugriff auf ein Element zu gewähren, können Sie es mit `Public`deklarieren.  
  
 Der öffentliche Zugriff ist die normale Ebene für ein Programmier Element, wenn Sie den Zugriff darauf nicht einschränken müssen. Beachten Sie, dass die Zugriffsebene eines Elements, das in einer Schnittstelle, einem Modul, einer Klasse oder einer Struktur deklariert ist, standardmäßig `Public`, wenn Sie es nicht anders deklarieren.  
  
## <a name="rules"></a>Regeln  
  
- **Deklarations Kontext.** Sie können `Public` nur auf der Ebene "Module", "Interface" oder "Namespace" verwenden. Dies bedeutet, dass der Deklarations Kontext für ein `Public` Element eine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Klasse oder eine Struktur sein muss und keine Prozedur sein muss.  
  
## <a name="behavior"></a>Verhalten  
  
- **Zugriffsebene.** Sämtlicher Code, der auf ein Modul, eine Klasse oder eine Struktur zugreifen kann, kann auf seine `Public` Elemente zugreifen.  
  
- **Standard Zugriff.** Lokale Variablen innerhalb einer Prozedur werden standardmäßig auf den öffentlichen Zugriff fest, und Sie können keine Zugriffsmodifizierer verwenden.  
  
- **Zugriffsmodifizierer** Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet. Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Der `Public`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Protected](../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Private Protected](private-protected.md)
- [Protected Friend](protected-friend.md)
- [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
