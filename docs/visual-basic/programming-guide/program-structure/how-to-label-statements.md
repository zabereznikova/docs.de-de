---
title: 'Vorgehensweise: Label-Anweisungen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 00a08bd3bd1f866cec883b6591b03ebd9d858b90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552258"
---
# <a name="how-to-label-statements-visual-basic"></a>Vorgehensweise: Label-Anweisungen (Visual Basic)
Anweisungsblöcke bestehen von Codezeilen, die durch Doppelpunkte getrennt sind. Codezeilen, die eine identifizierende Zeichenfolge oder ganzen Zahl vorangestellt werden als *mit der Bezeichnung*. Anweisungsbezeichnungen werden verwendet, um eine einzige Zeile Code für die Verwendung mit Anweisungen wie z. B. Identifikation markieren `On Error Goto`.  
  
 Bezeichnungen können entweder gültiger Visual Basic-Bezeichner sein – z. B. die Programmierelemente identifizieren – oder Integer-Literale. Eine Bezeichnung muss am Anfang einer Zeile des Quellcodes angezeigt werden und muss von einem Doppelpunkt, unabhängig davon, ob sie eine Anweisung in der gleichen Zeile folgt, wird gefolgt sein.  
  
 Der Compiler identifiziert Bezeichnungen wird geprüft, ob der Anfang der Zeile auf einen bereits definierten Bezeichner entspricht. Wenn dies nicht der Fall ist, wird der Compiler davon ausgegangen, dass es sich um eine Bezeichnung ist.  
  
 Bezeichnungen müssen ihre eigenen Deklarationsabschnitt und verursachen keine Konflikte mit anderen Bezeichnern. Eine Bezeichnung für den Bereich ist der Text der Methode. Deklaration der Bezeichnung hat Vorrang vor in einer mehrdeutigen Situation.  
  
> [!NOTE]
>  Bezeichnungen können nur auf ausführbaren Anweisungen in Methoden verwendet werden.  
  
### <a name="to-label-a-line-of-code"></a>Um eine einzige Zeile Code zu beschriften.  
  
-   Fügen Sie einen Bezeichner, gefolgt von einem Doppelpunkt am Anfang der Zeile des Quellcodes.  
  
     Z. B. die folgenden Codezeilen sind mit der Bezeichnung `Jump` und `120`bzw.:  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
- [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
