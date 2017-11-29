---
title: 'Gewusst wie: Vergleichen einer Zeichenfolge mit einem Muster (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83433bdb41df0ce40d0979f3f44603f10ba1c7d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>Gewusst wie: Vergleichen einer Zeichenfolge mit einem Muster (Visual Basic)
Wenn Sie, ob einen Ausdruck eines ermitteln möchten der [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md) einem Muster entspricht, dann können Sie mithilfe der [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
 `Like`verfügt über zwei Operanden. Der linke Operand ist ein Zeichenfolgenausdruck, und der Rechte Operand ist eine Zeichenfolge, enthält das Muster für den Abgleich verwendet werden. `Like`Gibt eine `Boolean` Wert, der angibt, ob der Zeichenfolgenausdruck dem Muster entspricht.  
  
 Sie können jedes Zeichen in der Zeichenfolgenausdruck für ein bestimmtes Zeichen, ein Platzhalterzeichen, eine Zeichenliste oder einem Bereich von Zeichen übereinstimmen. Die Positionen der Angaben in der Musterzeichenfolge entsprechen die Positionen der Zeichen im Zeichenfolgenausdruck verglichen werden.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>Um ein Zeichen im Zeichenfolgenausdruck für ein bestimmtes Zeichen  
  
-   Fügen Sie das Zeichen direkt in der Musterzeichenfolge. Bestimmte Sonderzeichen müssen in Klammern eingeschlossen werden (`[ ]`). Weitere Informationen finden Sie unter [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md).  
  
     Im folgenden Beispiel wird getestet, ob `myString` besteht das einzelne Zeichen genau `H`.  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>Um ein Zeichen im Zeichenfolgenausdruck mit einem Platzhalterzeichen  
  
-   Versetzen ein Fragezeichen (`?`) in der Musterzeichenfolge. An dieser Position irgendeinem gültigen Zeichen ergibt eine Übereinstimmung.  
  
     Im folgenden Beispiel wird getestet, ob `myString` besteht das einzelne Zeichen `W` gefolgt von genau zwei Zeichen aller Werte.  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>Um ein Zeichen im Zeichenfolgenausdruck mit einer Liste von Zeichen  
  
-   Platzieren von Klammern (`[ ]`) in der Musterzeichenfolge und innerhalb der Klammern setzen die Liste der Zeichen. Trennen Sie die Zeichen nicht durch Kommas oder einem anderen Trennzeichen. Beliebiges einzelnes Zeichen in der Liste wird eine erfolgreiche Übereinstimmung.  
  
     Im folgenden Beispiel wird getestet, ob `myString` besteht aus einem beliebigen gültigen Zeichen gefolgt von genau einem Zeichen `A`, `C`, oder `E`.  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     Beachten Sie, dass diese Übereinstimmung Groß-/Kleinschreibung beachtet wird.  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>Um ein Zeichen im Zeichenfolgenausdruck für einen Bereich von Zeichen  
  
-   Platzieren von Klammern (`[ ]`) in der Musterzeichenfolge und innerhalb der Klammern setzen die niedrigsten und höchsten Zeichen im Bereich durch einen Bindestrich getrennt (`–`). Beliebiges einzelnes Zeichen innerhalb des Bereichs wird eine erfolgreiche Übereinstimmung.  
  
     Im folgenden Beispiel wird getestet, ob `myString` besteht aus den Zeichen `num` gefolgt von genau einem Zeichen `i`, `j`, `k`, `l`, `m`, oder `n`.  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     Beachten Sie, dass diese Übereinstimmung Groß-/Kleinschreibung beachtet wird.  
  
## <a name="matching-empty-strings"></a>Übereinstimmende leere Zeichenfolgen  
 `Like`behandelt die Sequenz `[]` als eine Zeichenfolge der Länge 0 (null) (`""`). Sie können `[]` zu prüfen, ob der gesamte Zeichenfolgenausdruck leer ist, jedoch können sie überprüfen, ob eine bestimmte Position im Zeichenfolgenausdruck leer ist. Wenn eine leere Position eine der Optionen ist müssen Sie für die Sie verwenden können, testen `Like` mehr als einmal.  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>Um ein Zeichen im Zeichenfolgenausdruck mit einer Liste von Zeichen oder kein Zeichen  
  
1.  Rufen Sie die `Like` Operator zweimal in derselben Zeichenfolgeausdruck, und verbinden Sie die beiden Aufrufe entweder mit der [oder-Operator](../../../../visual-basic/language-reference/operators/or-operator.md) oder [OrElse-Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
2.  In der Musterzeichenfolge zum ersten `Like` -Klausel, enthalten die Zeichenliste in Klammern eingeschlossen (`[ ]`).  
  
3.  In der Musterzeichenfolge für die zweite `Like` -Klausel, nehmen Sie keines Zeichen an der Position fraglichen.  
  
     Das folgende Beispiel testet die siebenstellige Telefonnummer `phoneNum` für genau drei Ziffern, gefolgt von einem Leerzeichen, ein Bindestrich (`–`), einen Punkt (`.`), oder keine Zeichen überhaupt, gefolgt von genau vier Ziffern.  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Vergleichsoperatoren](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Operatoren und Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md)  
 [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md)
