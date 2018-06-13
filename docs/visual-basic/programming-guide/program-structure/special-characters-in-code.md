---
title: Sonderzeichen in Code (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
ms.openlocfilehash: 932b38d97b36292e66bfad91a9a3799459d3b73c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654355"
---
# <a name="special-characters-in-code-visual-basic"></a>Sonderzeichen in Code (Visual Basic)
In einigen Fällen müssen Sie Sonderzeichen in Ihrem Code, d. h. Zeichen verwenden, die nicht alphabetisch oder numerisch sind. Interpunktion und Sonderzeichen in der Visual Basic-Zeichensatz haben verschiedene Funktionen, reichen von der Strukturierung Programmtext zur Definition der Aufgaben, die der Compiler oder das kompilierte Programm ausführt. Sie legen keine auszuführende Operation fest.  
  
## <a name="parentheses"></a>Klammern  
 Verwenden Sie Klammern, wenn Sie eine Prozedur, wie z. B. definieren eine `Sub` oder `Function`. Sie müssen alle Prozedur Argumentlisten in Klammern einschließen. Sie verwenden auch Klammern für das zusammensetzen von Variablen oder Argumente in logischen Gruppen, insbesondere, um die Standardreihenfolge der Rangfolge von Operatoren in einem komplexen Ausdruck zu überschreiben. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 Nach der Ausführung des vorherigen Code den Wert der `d` "8.225" und der Wert des `e` ist 3. Die Berechnung von `d` verwendet der Standardvorrang gilt der `/` über `+` und entspricht dem `d = b + (c / a)`. Die Klammern in die Berechnung von `e` außer Kraft setzen der Standardvorrang gilt.  
  
## <a name="separators"></a>Trennzeichen  
 Trennzeichen sind, was ihre Name schon sagt: Trennen Sie Abschnitte des Codes. In Visual Basic ist das Trennzeichen der Doppelpunkt (`:`). Verwenden Sie als Trennzeichen, wenn mehrere Anweisungen in einer einzelnen Zeile anstelle von separaten Zeilen enthalten sein sollen. Dies spart Platz und verbessert die Lesbarkeit des Codes. Das folgende Beispiel zeigt drei Anweisungen, die durch Doppelpunkte getrennt werden.  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 Weitere Informationen finden Sie unter [wie: unterbrechen und Kombinieren von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 Der Doppelpunkt (`:`)-Zeichen wird auch verwendet, um eine anweisungsbezeichnung zu identifizieren. Weitere Informationen finden Sie unter [wie: Label-Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Verkettung  
 Verwenden der `&` Operator für *Verkettung*, oder Zeichenfolgen miteinander zu verknüpfen. Verwechseln sie nicht die `+` -Operator, der numerische Werte addiert. Bei Verwendung der `+` Operator zum Verketten, wenn numerische Werte bearbeitet werden kann, falsche Ergebnisse zu erhalten. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 Nach der Ausführung des vorherigen Code den Wert der `resultA` 21.01 und der Wert des `resultB` "10.0111".  
  
## <a name="member-access-operators"></a>Operatoren für den Memberzugriff  
 Zugriff auf einen Member eines Typs, verwenden Sie den Punkt (`.`) oder ein Ausrufezeichen (`!`)-Operator zwischen den vollständigen Typnamen und den Elementnamen.  
  
### <a name="dot--operator"></a>Punkt (.) Operator  
 Verwenden der `.` Operator auf eine Klasse, Struktur, Schnittstelle oder Enumeration als Operator für den Memberzugriff. Das Element kann ein Feld, Eigenschaft, Ereignis oder Methode sein. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a>Ausrufezeichen (!) Operator  
 Verwenden der `!` Operator nur auf eine Klasse oder Schnittstelle wie ein wörterbuchzugriffsoperator. Die Klasse oder Schnittstelle benötigen eine Standardeigenschaft, die ein einzelnes akzeptiert `String` Argument. Der Bezeichner, der unmittelbar nach der `!` Operator wird der Wert des Arguments an die Standardeigenschaft als Zeichenfolge übergeben. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 Die drei Zeilen der Ausgabe `MsgBox` alle zeigt den Wert `32856`. Die erste Zeile verwendet den herkömmlichen Zugriff auf die Eigenschaft `index`, die zweite nutzt die Tatsache, `index` ist die Standardeigenschaft der Klasse `hasDefault`, und die dritte verwendet Wörterbuchzugriff auf die Klasse.  
  
 Beachten Sie, dass der zweite Operand, der die `!` Operator muss ein gültiger Visual Basic-Bezeichner, die nicht in doppelte Anführungszeichen eingeschlossen sein (`" "`). Sie können nicht mit anderen Worten, ein Zeichenfolgenliteral oder eine Zeichenfolgenvariable verwenden. Änderungen an den folgenden zur letzten Zeile der `MsgBox` Aufruf wird ein Fehler generiert, da `"X"` ist ein eingeschlossenen Zeichenfolgenliteral.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  Verweise auf die Standardsammlungen müssen explizit sein. Insbesondere können Sie keine der `!` Operator auf eine spät gebundene Variable.  
  
 Die `!` Zeichen dient auch als die `Single` Zeichen eingeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
