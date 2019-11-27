---
title: Sonderzeichen in Code
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
ms.openlocfilehash: f4ab35b56d48ae86bdb024ffea27735b39decdc2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347267"
---
# <a name="special-characters-in-code-visual-basic"></a>Sonderzeichen in Code (Visual Basic)
Manchmal müssen Sonderzeichen in Ihrem Code verwendet werden, d. h. Zeichen, die nicht alphabetisch oder numerisch sind. Die Interpunktions-und Sonderzeichen im Visual Basic Zeichensatz weisen verschiedene Verwendungsmöglichkeiten auf, von der Organisation des Programm Texts bis zur Definition der Aufgaben, die der Compiler oder das kompilierte Programm ausführt. Sie legen keine auszuführende Operation fest.  
  
## <a name="parentheses"></a>Klammern  
 Verwenden Sie Klammern, wenn Sie eine Prozedur definieren, z. b. eine `Sub` oder eine `Function`. Alle Prozedur Argumentlisten müssen in Klammern eingeschlossen werden. Außerdem verwenden Sie Klammern zum Platzieren von Variablen oder Argumenten in logischen Gruppen, insbesondere, um die Standard Reihenfolge der Operator Rangfolge in einem komplexen Ausdruck zu überschreiben. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 Nach der Ausführung des vorherigen Codes lautet der Wert von `d` 8,225 und der Wert von `e` 3. Die Berechnung für `d` verwendet die Standard Rangfolge `/` over `+` und entspricht `d = b + (c / a)`. Die Klammern in der Berechnung für `e` die Standard Rangfolge überschreiben.  
  
## <a name="separators"></a>Trennzeichen  
 Trennzeichen tun, was der Name vermuten lässt: Sie trennen Code Abschnitte. In Visual Basic ist das Trennzeichen der Doppelpunkt (`:`). Verwenden Sie Trennzeichen, wenn Sie mehrere-Anweisungen in einer einzelnen Zeile anstelle von separaten Zeilen einschließen möchten. Dadurch wird Speicherplatz gespart, und die Lesbarkeit des Codes wird verbessert. Im folgenden Beispiel werden drei durch Doppelpunkte getrennte Anweisungen gezeigt.  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 Weitere Informationen finden Sie unter Gewusst [wie: unterbrechen und Kombinieren von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 Der Doppelpunkt (`:`) wird auch verwendet, um eine Anweisungsbezeichnung zu identifizieren. Weitere Informationen finden Sie unter Gewusst [wie: bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Verkettung  
 Verwenden Sie den `&`-Operator für die *Verkettung*oder das Verknüpfen von Zeichen folgen. Verwechseln Sie diese nicht mit dem `+`-Operator, der numerische Werte addiert. Wenn Sie den `+` Operator zum Verketten verwenden, wenn Sie numerische Werte verarbeiten, können Sie falsche Ergebnisse erzielen. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 Nach der Ausführung des vorherigen Codes lautet der Wert von `resultA` 21,01 und der Wert von `resultB` "10,0111".  
  
## <a name="member-access-operators"></a>Member-Zugriffs Operatoren  
 Wenn Sie auf einen Member eines Typs zugreifen möchten, verwenden Sie den Punkt (`.`) oder den Ausrufezeichen Operator (`!`) zwischen dem Typnamen und dem Elementnamen.  
  
### <a name="dot--operator"></a>Punkt (.) KOM  
 Verwenden Sie den `.`-Operator in einer Klasse, Struktur, Schnittstelle oder Enumeration als Member Access Operator. Der Member kann ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode sein. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>Ausrufezeichen (!) KOM  
 Verwenden Sie den `!`-Operator nur für eine Klasse oder Schnittstelle als Wörterbuch Zugriffs Operator. Die Klasse oder Schnittstelle muss über eine Default-Eigenschaft verfügen, die ein einzelnes `String` Argument akzeptiert. Der Bezeichner, der direkt auf den `!`-Operator folgt, wird zu dem Argument Wert, der als Zeichenfolge an die Default-Eigenschaft Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 Die drei Ausgabezeilen `MsgBox` alle den Wert `32856`anzeigen. In der ersten Zeile wird der herkömmliche Zugriff auf die Eigenschaft `index`verwendet, die zweite verwendet die Tatsache, dass `index` die Standard Eigenschaft der Klasse `hasDefault`ist, und der dritte verwendet den Wörterbuch Zugriff auf die Klasse.  
  
 Beachten Sie, dass der zweite Operand des `!` Operators ein gültiger Visual Basic Bezeichner sein muss, der nicht in doppelte Anführungszeichen (`" "`) eingeschlossen ist. Anders ausgedrückt: Sie können keine Zeichenfolgenliterale oder Zeichen folgen Variable verwenden. Mit der folgenden Änderung an der letzten Zeile des `MsgBox` Aufrufes wird ein Fehler generiert, da `"X"` ein eingeschlossenes Zeichenfolgenliteral  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> Verweise auf Standard Auflistungen müssen explizit sein. Insbesondere ist es nicht möglich, den `!`-Operator für eine spät gebundene Variable zu verwenden.  
  
 Das `!` Zeichen wird auch als `Single` Type-Zeichen verwendet.  
  
## <a name="see-also"></a>Siehe auch

- [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
