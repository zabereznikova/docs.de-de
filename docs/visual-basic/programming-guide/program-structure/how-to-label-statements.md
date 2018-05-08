---
title: 'Gewusst wie: Label-Anweisungen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: df368bdba73ca35dd70bdd2f4e88cc10af894b5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-label-statements-visual-basic"></a>Gewusst wie: Label-Anweisungen (Visual Basic)
Anweisungsblöcke erfolgen der Codezeilen, die durch Doppelpunkte getrennt. Codezeilen, die eine identifizierende Zeichenfolge oder eine ganze Zahl vorangestellt werden als *mit der Bezeichnung*. Anweisungsbezeichnungen dienen zum Kennzeichnen einer Zeile des Codes für die Verwendung mit Anweisungen wie z. B. dienen `On Error Goto`.  
  
 Bezeichnungen können entweder gültiger Visual Basic-Bezeichner sein – z. B. solche, die Programmierelemente identifizieren – oder Integer-Literale. Eine Bezeichnung muss am Anfang einer Zeile des Quellcodes angezeigt werden und muss unabhängig davon, ob sie eine Anweisung in der gleichen Zeile folgt, wird ein Doppelpunkt folgen.  
  
 Der Compiler identifiziert Bezeichnungen, indem Sie überprüfen, ob der Anfang der Zeile eine bereits definierte Bezeichner entspricht. Ist dies nicht der Fall ist, wird der Compiler davon ausgegangen, dass es sich um eine Bezeichnung ist.  
  
 Bezeichnungen haben ihre eigenen Deklarationsabschnitt und verursachen keine Konflikte mit anderen Bezeichnern. Eine Bezeichnung Bereich ist der Text der Methode. Bezeichnungsdeklaration hat Vorrang vor in allen Situationen mit mehrdeutig.  
  
> [!NOTE]
>  Bezeichnungen können nur auf die ausführbaren Anweisungen in Methoden verwendet werden.  
  
### <a name="to-label-a-line-of-code"></a>Um eine Codezeile zu bezeichnen.  
  
-   Platzieren Sie einen Bezeichner zeigen, gefolgt von einem Doppelpunkt am Anfang der Zeile des Quellcodes.  
  
     Z. B. die folgenden Codezeilen mit beschriftet `Jump` und `120`bzw.:  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
