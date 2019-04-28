---
title: Typografische und Codekonventionen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- typographic conventions [Visual Basic]
- document conventions [Visual Basic]
- conventions [Visual Basic], documentation
- Visual Basic code, conventions
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
ms.openlocfilehash: 3255dff8268cd5500a1244716f37bf30f5b43cfb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698602"
---
# <a name="typographic-and-code-conventions-visual-basic"></a>Typografische und Codekonventionen (Visual Basic)
Dokumentation zu Visual Basic verwendet die folgenden typografische und Codekonventionen.  
  
## <a name="typographic-conventions"></a>Typografische Konventionen  
  
|Beispiel|Beschreibung|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Sprachspezifische Schlüsselwörter und Common Language Runtime-Elemente haben stehender Großbuchstaben und werden wie im folgenden Beispiel gezeigt formatiert.|  
|**SmallProject**, **ButtonCollection**|Wörter und Ausdrücke, die Sie zur Eingabe aufgefordert werden, werden wie im folgenden Beispiel gezeigt formatiert.|  
|[Module-Anweisung](../../visual-basic/language-reference/statements/module-statement.md)|Wie im folgenden Beispiel gezeigt, werden Verknüpfungen aus, die Sie klicken können, um zu einer anderen Seite wechseln formatiert.|  
|*object*, *variableName*, `argumentList`|Platzhalter für Informationen, die Sie angeben, werden formatiert, wie im folgenden Beispiel gezeigt.|  
|[Schatten], [ *ExpressionList* ]|In der Syntax werden die optionalen Elemente in Klammern eingeschlossen.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|In der Syntax Wenn Sie eine Wahl zwischen zwei oder mehr Elementen vornehmen, müssen die Elemente sind in geschweifte Klammern eingeschlossen und durch senkrechte Striche getrennt.<br /><br /> Sie müssen eine und nur eines der Elemente auswählen.|  
|[ `Protected` &#124; `Friend` ]|In der Syntax Wenn man die Möglichkeit auszuwählen, die zwischen zwei oder mehr Elemente, die Elemente sind in eckige Klammern eingeschlossen und durch senkrechte Striche getrennt.<br /><br /> Sie können eine beliebige Kombination der Elemente oder kein Element auswählen.|  
|[{ `ByVal` &#124; `ByRef` }]|Wenn Sie nicht mehr als ein Element auswählen können, aber Sie können Elemente auch komplett weglassen werden die Elemente in der Syntax in eckigen Klammern von geschweiften Klammern umgeben und durch senkrechte Striche getrennte eingeschlossen.|  
|*memberName*1, *memberName*2, *memberName*3|Mehrere Instanzen eines Platzhalters unterscheiden sich von Feldindizes angegeben werden, wie im Beispiel gezeigt.|  
|*memberName1*<br /><br /> ...<br /><br /> *memberNameN*|In der Syntax ist ein Auslassungszeichen (...) Dient zum Angeben einer unbestimmten Anzahl von Elementen der Art unmittelbar vor der Ellipse.<br /><br /> Im Code stellen Ellipsen Code, die aus Gründen der Übersichtlichkeit weggelassen.|  
|ESC, ENTER|Schlüsselnamen und Tastenkombinationen auf der Tastatur, die in Großbuchstaben angezeigt werden.|  
|ALT+F1|Wenn zwischen den Schlüsselnamen Pluszeichen (+) angezeigt werden, müssen Sie eine Taste gedrückt halten, und drücken die andere. ALT + F1 bedeutet beispielsweise, die der ALT-Taste gedrückt halten, während Sie die Taste F1 drücken.|  
  
## <a name="code-conventions"></a>Codekonventionen  
  
|Beispiel|Beschreibung|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|Codebeispiele werden in einer Schriftart mit fester Zeichenbreite und werden wie im folgenden Beispiel gezeigt formatiert.|  
|Die vorherige Anweisung legt den Wert der `sampleString` um "Hello, World!"|Code-Elementen im erläuternden Text werden in einer Schriftart mit fester Zeichenbreite, angezeigt, wie im folgenden Beispiel gezeigt.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|Codekommentare werden durch ein Apostroph (') oder dem REM-Schlüsselwort eingeführt.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Ein Leerzeichen, gefolgt von einem Unterstrich (_) am Ende einer Zeile gibt an, dass die Anweisung in der folgenden Zeile fortgesetzt wird.|  
  
## <a name="see-also"></a>Siehe auch

- [Sprachreferenz zu Visual Basic](../../visual-basic/language-reference/index.md)
- [Schlüsselwörter](../../visual-basic/language-reference/keywords/index.md)
- [Member der Visual Basic-Laufzeitbibliothek](../../visual-basic/language-reference/runtime-library-members.md)
- [Visual Basic-Benennungskonventionen](../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Kommentare in Code](../../visual-basic/programming-guide/program-structure/comments-in-code.md)
