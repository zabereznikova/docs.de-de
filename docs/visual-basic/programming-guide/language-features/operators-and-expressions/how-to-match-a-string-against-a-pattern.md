---
title: 'Vorgehensweise: Vergleichen einer Zeichenfolge mit einem Muster (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: 884c5ddf15deb49719915f10e107ba6a3431c4bc
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965942"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Vorgehensweise: Vergleichen einer Zeichenfolge mit einem Muster (Visual Basic)
Sollten Sie ermitteln, ob einen Ausdruck, der die [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md) einem Muster entspricht, dann können Sie mithilfe der [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
 `Like` akzeptiert zwei Operanden. Der linke Operand ist ein Zeichenfolgenausdruck, und der Rechte Operand ist eine Zeichenfolge, enthält das Muster für den Abgleich verwendet werden. `Like` Gibt eine `Boolean` Wert, der angibt, ob der Ausdruck mit dem Muster entspricht.  
  
 Sie können jedes Zeichen in den Ausdruck für ein bestimmtes Zeichen, ein Platzhalterzeichen, eine Zeichenliste oder einen Zeichenbereich zuordnen. Die Positionen der Angaben in der Musterzeichenfolge entsprechen die Positionen der Zeichen im Zeichenfolgenausdruck abgeglichen werden.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Um ein Zeichen in den Ausdruck für ein bestimmtes Zeichen  
  
-   Fügen Sie das Zeichen direkt in der Musterzeichenfolge. Bestimmte Sonderzeichen müssen in Klammern eingeschlossen werden (`[ ]`). Weitere Informationen finden Sie unter [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
     Im folgenden Beispiel wird getestet, ob `myString` besteht genau aus das einzelne Zeichen `H`.  
  
     [!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Um ein Zeichen in den Ausdruck mit einem Platzhalterzeichen  
  
-   Fügen ein Fragezeichen (`?`) in der Musterzeichenfolge. Jedes gültige Zeichen an dieser Position ergibt eine Übereinstimmung.  
  
     Im folgenden Beispiel wird getestet, ob `myString` besteht aus den einzelnen Zeichens `W` gefolgt von genau zwei beliebigen Zeichen.  
  
     [!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Um ein Zeichen in den Zeichenfolgenausdruck mit einer Liste von Zeichen  
  
-   Einfügen von Klammern (`[ ]`) in der Musterzeichenfolge, und klicken Sie in den Klammern fügen Sie die Liste von Zeichen. Trennen Sie die Zeichen nicht mit Kommas oder aller anderen Trennzeichen. Beliebiges einzelnes Zeichen in der Liste wird eine Übereinstimmung.  
  
     Im folgenden Beispiel wird getestet, ob `myString` irgendeinem gültigen Zeichen, gefolgt von genau einem Zeichen bestehen `A`, `C`, oder `E`.  
  
     [!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]  
  
     Beachten Sie, dass diese Übereinstimmung Groß-/Kleinschreibung beachtet wird.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Um ein Zeichen in den Ausdruck für einen Bereich von Zeichen  
  
-   Einfügen von Klammern (`[ ]`) in der Musterzeichenfolge und innerhalb der Klammern, die die niedrigsten und höchsten Zeichen im Bereich einfügen, getrennt durch einen Bindestrich (`–`). Beliebiges einzelnes Zeichen innerhalb des Bereichs ergibt eine Übereinstimmung.  
  
     Im folgenden Beispiel wird getestet, ob `myString` besteht aus den Zeichen `num` gefolgt von genau einem Zeichen `i`, `j`, `k`, `l`, `m`, oder `n`.  
  
     [!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]  
  
     Beachten Sie, dass diese Übereinstimmung Groß-/Kleinschreibung beachtet wird.  
  
## <a name="matching-empty-strings"></a>Übereinstimmende leere Zeichenfolgen  
 `Like` behandelt die Sequenz `[]` als eine Zeichenfolge der Länge 0 (null) (`""`). Sie können `[]` zu prüfen, ob der gesamte Ausdruck leer ist, aber Sie können keine sie prüfen, ob eine bestimmte Position im Zeichenfolgenausdruck leer ist. Eine der Optionen ist eine leere Position müssen Sie testen, für die Sie verwenden können, `Like` mehr als einmal.  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Um ein Zeichen in den Ausdruck anhand einer Liste von Zeichen oder keine Zeichen  
  
1.  Rufen Sie die `Like` Operator zwei Mal auf dem gleichen Ausdruck eine Zeichenfolge, und verbinden Sie die beiden Aufrufe entweder mit der [oder-Operator](../../../../visual-basic/language-reference/operators/or-operator.md) oder [OrElse-Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
2.  In der Musterzeichenfolge für die erste `Like` -Klausel, die in Klammern eingeschlossene Zeichenliste enthalten (`[ ]`).  
  
3.  In der Musterzeichenfolge für die zweite `Like` -Klausel, platzieren Sie keines Zeichen an der Position betreffende.  
  
     Das folgende Beispiel testet die siebenstelligen Telefonnummer `phoneNum` für genau drei Ziffern, gefolgt von einem Leerzeichen, einen Bindestrich (`–`), einen Zeitraum (`.`), oder keine, gefolgt von genau vier Ziffern.  
  
     [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]  
  
## <a name="see-also"></a>Siehe auch
- [Vergleichsoperatoren](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Operatoren und Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md)
- [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md)
