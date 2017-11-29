---
title: Typografische und Codekonventionen (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- typographic conventions [Visual Basic]
- document conventions [Visual Basic]
- conventions [Visual Basic], documentation
- Visual Basic code, conventions
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7b6db5c223b0548e308b49a686cff72eaaf8da36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="typographic-and-code-conventions-visual-basic"></a>Typografische und Codekonventionen (Visual Basic)
Dokumentation zu Visual Basic verwendet die folgenden typografische und Codekonventionen.  
  
## <a name="typographic-conventions"></a>Typografische Konventionen  
  
|Beispiel|Beschreibung|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Language-spezifische Schlüsselwörter und Member-stehender Großbuchstaben haben, und werden wie im folgenden Beispiel gezeigt formatiert.|  
|**SmallProject**, **ButtonCollection**|Wörter und Ausdrücke, die Sie zur Eingabe aufgefordert werden, werden wie im folgenden Beispiel gezeigt formatiert.|  
|[Module-Anweisung](../../visual-basic/language-reference/statements/module-statement.md)|Verknüpfungen aus, die Sie klicken können, gehen Sie zu einer anderen Hilfeseite werden wie im folgenden Beispiel gezeigt formatiert.|  
|*Objekt*, *VariableName*,`argumentList`|Platzhalter für Informationen, die Sie angeben, werden wie im folgenden Beispiel gezeigt formatiert.|  
|[Schatten], [ *ExpressionList* ]|In der Syntax werden optionale Elemente in Klammern eingeschlossen.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|In der Syntax Wenn Sie eine Auswahl zwischen zwei oder mehr Elementen vornehmen, müssen die Elemente sind in geschweifte Klammern eingeschlossen und durch senkrechte Striche getrennte.<br /><br /> Sie müssen eine und nur eines der Elemente auswählen.|  
|[ `Protected` &#124; `Friend` ]|In der Syntax Wenn stehen Ihnen die Möglichkeit, die Auswahl zwischen zwei oder mehr Elemente, die Elemente sind in eckige Klammern eingeschlossen und durch senkrechte Striche getrennte.<br /><br /> Sie können eine beliebige Kombination der Elemente oder kein Element auswählen.|  
|[{ `ByVal` &#124; `ByRef` }]|Wenn können Sie nicht mehr als ein Element auswählen, aber Sie können Elemente auch vollständig auslassen sind die Elemente in der Syntax in eckigen Klammern umgeben und durch senkrechte Striche getrennte eingeschlossen.|  
|*MemberName*1 *MemberName*2, *MemberName*3|Mehrere Instanzen des gleichen Platzhalters unterscheiden sich von Feldindizes angegeben werden, wie im Beispiel gezeigt.|  
|*memberName1*<br /><br /> ...<br /><br /> *memberNameN*|In der Syntax ein Auslassungszeichen (...) verwendet, um eine unbegrenzte Anzahl von Elementen der Art unmittelbar vor der Ellipse anzugeben.<br /><br /> Im Code stellen Ellipsen Code, die aus Gründen der Übersichtlichkeit weggelassen.|  
|ESC, GEBEN SIE|Schlüsselnamen und Tastenkombinationen auf der Tastatur, die in Großbuchstaben angezeigt werden.|  
|ALT + F1|Wenn zwischen Schlüsselnamen Pluszeichen (+) angezeigt werden, müssen Sie eine Taste gedrückt halten, beim Drücken die andere. ALT + F1 bedeutet z. B. die ALT-Taste gedrückt halten, beim Drücken der F1-Taste.|  
  
## <a name="code-conventions"></a>Codekonventionen  
  
|Beispiel|Beschreibung|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|Codebeispiele werden in einer Schriftart fester Schriftbreite angezeigt und formatiert sind, wie im folgenden Beispiel gezeigt.|  
|Die vorherige Anweisung legt den Wert der `sampleString` um "Hello, World!"|Codeelemente in erläuternden Text werden in einer Schriftart fester Schriftbreite angezeigt, wie im folgenden Beispiel gezeigt.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|Codekommentare werden durch ein Apostroph (') oder das Schlüsselwort REM eingeführt.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Ein Leerzeichen, gefolgt von einem Unterstrich (_) am Ende einer Zeile gibt an, dass die Anweisung in der folgenden Zeile fortgesetzt wird.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sprachreferenz zu Visual Basic](../../visual-basic/language-reference/index.md)  
 [Schlüsselwörter](../../visual-basic/language-reference/keywords/index.md)  
 [Member der Visual Basic-Laufzeitbibliothek](../../visual-basic/language-reference/runtime-library-members.md)  
 [Visual Basic-Benennungskonventionen](../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [Kommentare in Code](../../visual-basic/programming-guide/program-structure/comments-in-code.md)
