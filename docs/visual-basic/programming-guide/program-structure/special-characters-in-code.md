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
ms.openlocfilehash: 65fcd10521742e287c7934080b3352a06668df7a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835556"
---
# <a name="special-characters-in-code-visual-basic"></a>Sonderzeichen in Code (Visual Basic)
Manchmal müssen Sie Sonderzeichen in Ihrem Code, d. h. Zeichen verwenden, die nicht alphabetisch oder numerisch sind. Die Interpunktions- und Sonderzeichen in der Visual Basic-Zeichensatz haben verschiedene Programmtexts zum Definieren der Aufgaben, die der Compiler oder das kompilierte Programm ausführt. Sie legen keine auszuführende Operation fest.  
  
## <a name="parentheses"></a>Klammern  
 Verwenden Sie Klammern, wenn Sie eine Prozedur, wie z. B. definieren eine `Sub` oder `Function`. Sie müssen alle Prozedur Argumentlisten in Klammern einschließen. Können Sie auch Klammern zum Einfügen von Variablen oder Argumente in logischen Gruppen, die insbesondere um die Standardreihenfolge der Operatorrangfolge in einem komplexen Ausdruck außer Kraft zu setzen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 Nach der Ausführung des vorherigen Code den Wert der `d` "8.225" und der Wert des `e` ist 3. Die Berechnung für `d` verwendet die standardmäßige Rangfolge `/` über `+` entspricht `d = b + (c / a)`. Die Klammern in die Berechnung für `e` außer Kraft setzen der Standardvorrang gilt.  
  
## <a name="separators"></a>Trennzeichen  
 Trennzeichen sind, was ihr Name besagt: Trennen Sie Abschnitte des Codes. In Visual Basic ist das Trennzeichen der Doppelpunkt (`:`). Verwenden Sie Trennzeichen, wenn mehrere Anweisungen in einer einzelnen Zeile anstelle von separaten Zeilen enthalten sein sollen. Dies spart Platz und verbessert die Lesbarkeit des Codes. Das folgende Beispiel zeigt drei Anweisungen, die durch Doppelpunkte getrennt sind.  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 Der Doppelpunkt (`:`)-Zeichen wird auch verwendet, um eine anweisungsbezeichnung zu identifizieren. Weitere Informationen finden Sie unter [Vorgehensweise: Bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Verkettung  
 Verwenden der `&` Operator für *Verkettung*, oder Zeichenfolgen miteinander zu verknüpfen. Ist nicht zu verwechseln mit der `+` -Operator, der numerische Werte addiert. Bei Verwendung der `+` Operator zum Verketten, wenn Sie numerische Werte arbeiten Sie erhalten falsche Ergebnisse. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 Nach der Ausführung des vorherigen Code den Wert der `resultA` 21.01 und den Wert der `resultB` "10.0111".  
  
## <a name="member-access-operators"></a>Operatoren für den Memberzugriff  
 Für den Zugriff auf einen Member eines Typs, die Sie verwenden des Punkts (`.`) oder ein Ausrufezeichen (`!`)-Operator zwischen den Typnamen und den Namen des Members.  
  
### <a name="dot--operator"></a>Punkt (.) Operator  
 Verwenden der `.` Operator auf eine Klasse, Struktur, Schnittstelle oder Enumeration als ein Memberzugriffsoperator. Das Element kann ein Feld, Eigenschaft, Ereignis oder Methode sein. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>Ausrufezeichen (!) Operator  
 Verwenden der `!` -Operator nur auf eine Klasse oder Schnittstelle wie ein wörterbuchzugriffsoperator. Die Klasse oder Schnittstelle benötigen eine Standardeigenschaft, die akzeptiert ein einzelnes `String` Argument. Der Bezeichner sofort nach der `!` Operator wird der Wert des Arguments an die Standardeigenschaft als Zeichenfolge übergeben. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 Die drei Zeilen der Ausgabe `MsgBox` alle zeigt den Wert `32856`. Die erste Zeile verwendet die herkömmlichen Zugriff auf Eigenschaft `index`, die zweite nutzt die Tatsache, `index` ist die Standardeigenschaft der Klasse `hasDefault`, und das dritte verwendet Wörterbuchzugriff auf die Klasse.  
  
 Beachten Sie, dass der zweite Operand, der die `!` Operator muss ein gültiger Visual Basic-Bezeichner, die nicht in doppelte Anführungszeichen eingeschlossen sein (`" "`). Sie können nicht in anderen Worten, ein Zeichenfolgenliteral oder eine String-Variable verwenden. Änderungen an den folgenden auf die letzte Zeile der `MsgBox` Aufruf wird ein Fehler generiert, da `"X"` ist eine eingeschlossene Zeichenfolgenliteral.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  Verweise auf die Standardsammlungen müssen explizit sein. Insbesondere können keine der `!` Operator für eine spät gebundene Variable.  
  
 Die `!` Zeichen dient auch als die `Single` Typzeichen.  
  
## <a name="see-also"></a>Siehe auch

- [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
