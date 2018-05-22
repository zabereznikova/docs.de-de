---
title: Public (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: a5e9161132ba6d571daa30ce82e1bfb1dd2b064f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="public-visual-basic"></a>Public (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte Programmierelemente uneingeschränkt Zugriff haben.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie eine Komponente oder ein Satz von Komponenten, z. B. eine Klassenbibliothek, veröffentlichen möchten Sie in der Regel die Programmierelemente von jedem Code zugegriffen werden kann, die mit der Assembly interagiert. Um solche unbegrenzten Zugriff auf ein Element zu gewähren, deklarieren Sie ihn mit `Public`.  
  
 Öffentlicher Zugriff ist der normale Ebene für ein Programmierelement, wenn Sie nicht benötigen, um den Zugriff darauf zu beschränken. Beachten Sie, dass die Zugriffsebene eines Elements innerhalb einer Schnittstelle, Modul, Klasse oder Struktur deklariert wird standardmäßig auf `Public` , wenn Sie es andernfalls nicht deklarieren.  
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Sie können `Public` nur auf Modul, Schnittstelle oder Namespace-Ebene. Dies bedeutet, dass der Deklarationskontext für eine `Public` Element muss eine Quelldatei, Namespace, Schnittstelle, Modul, Klasse oder Struktur sein und darf keine Prozedur sein.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zugriffsebene.** Der gesamte Code, der ein Modul, Klasse oder Struktur zugreifen kann erreichen die `Public` Elemente.  
  
-   **Der Standardzugriff.** Keine Zugriffsmodifizierer können keine lokale Variablen in einer Prozedur erhalten standardmäßig öffentlichen Zugriff, und Sie darauf.  
  
-   **Zugriffsmodifizierer.** Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*. Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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
  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Geschützt privat](private-protected.md)   
 [Protected Friend](protected-friend.md)   
 [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
