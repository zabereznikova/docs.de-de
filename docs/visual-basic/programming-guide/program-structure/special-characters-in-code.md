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
ms.openlocfilehash: 60f815f0d30fa785f4a2166db5a041d3851aa954
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097825"
---
# <a name="special-characters-in-code-visual-basic"></a>Sonderzeichen in Code (Visual Basic)

Manchmal müssen Sonderzeichen in Ihrem Code verwendet werden, d. h. Zeichen, die nicht alphabetisch oder numerisch sind. Die Interpunktions-und Sonderzeichen im Visual Basic Zeichensatz weisen verschiedene Verwendungsmöglichkeiten auf, von der Organisation des Programm Texts bis zur Definition der Aufgaben, die der Compiler oder das kompilierte Programm ausführt. Sie legen keine auszuführende Operation fest.  
  
## <a name="parentheses"></a>Klammern  

 Verwenden Sie Klammern, wenn Sie eine Prozedur definieren, z. b `Sub` `Function` . oder. Alle Prozedur Argumentlisten müssen in Klammern eingeschlossen werden. Außerdem verwenden Sie Klammern zum Platzieren von Variablen oder Argumenten in logischen Gruppen, insbesondere, um die Standard Reihenfolge der Operator Rangfolge in einem komplexen Ausdruck zu überschreiben. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 Nach der Ausführung des vorherigen Codes ist der Wert von `d` 8,225 und der Wert von `e` 3. Die Berechnung für `d` verwendet die Standard Rangfolge von `/` over `+` und entspricht `d = b + (c / a)` . Die Klammern in der Berechnung für über `e` schreiben die Standard Rangfolge.  
  
## <a name="separators"></a>Trennzeichen  

 Trennzeichen tun, was der Name vermuten lässt: Sie trennen Code Abschnitte. In Visual Basic ist das Trennzeichen der Doppelpunkt ( `:` ). Verwenden Sie Trennzeichen, wenn Sie mehrere-Anweisungen in einer einzelnen Zeile anstelle von separaten Zeilen einschließen möchten. Dadurch wird Speicherplatz gespart, und die Lesbarkeit des Codes wird verbessert. Im folgenden Beispiel werden drei durch Doppelpunkte getrennte Anweisungen gezeigt.  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 Weitere Informationen finden Sie unter Gewusst [wie: unterbrechen und Kombinieren von Anweisungen in Code](how-to-break-and-combine-statements-in-code.md).  
  
 Der Doppelpunkt ( `:` ) wird auch verwendet, um eine Anweisungsbezeichnung zu identifizieren. Weitere Informationen finden Sie unter Gewusst [wie: bezeichnen von Anweisungen](how-to-label-statements.md).  
  
## <a name="concatenation"></a>Verkettung  

 Verwenden Sie den- `&` Operator für die *Verkettung*oder das Verknüpfen von Zeichen folgen. Verwechseln Sie diese nicht mit dem- `+` Operator, der numerische Werte addiert. Wenn Sie den- `+` Operator zum Verketten verwenden, wenn Sie numerische Werte verarbeiten, können Sie falsche Ergebnisse erzielen. Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 Nach der Ausführung des vorherigen Codes ist der Wert von `resultA` 21,01 und der Wert von `resultB` "10,0111".  
  
## <a name="member-access-operators"></a>Member-Zugriffs Operatoren  

 Wenn Sie auf einen Member eines Typs zugreifen möchten, verwenden Sie den Punkt ( `.` ) oder den Ausrufezeichen `!` Operator () zwischen dem Typnamen und dem Elementnamen.  
  
### <a name="dot--operator"></a>Punkt (.) KOM  

 Verwenden Sie den- `.` Operator für eine Klasse, eine Struktur, eine Schnittstelle oder eine Enumeration als Member Access Operator. Der Member kann ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode sein. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>Ausrufezeichen (!) KOM  

 Verwenden Sie den- `!` Operator nur für eine Klasse oder Schnittstelle als Wörterbuch Zugriffs Operator. Die Klasse oder Schnittstelle muss über eine Default-Eigenschaft verfügen, die ein einzelnes `String` Argument akzeptiert. Der Bezeichner, der direkt `!` auf den Operator folgt, wird zum Argument Wert, der als Zeichenfolge an die Standard Eigenschaft übermittelt wird Dies wird im folgenden Beispiel veranschaulicht:  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 In den drei Ausgabezeilen von wird `MsgBox` der Wert angezeigt `32856` . Die erste Zeile verwendet die herkömmliche Access-Eigenschaft `index` , die zweite verwendet die Tatsache, dass `index` die Standard Eigenschaft der-Klasse ist `hasDefault` , und die dritte verwendet den Wörterbuch Zugriff auf die-Klasse.  
  
 Beachten Sie, dass der zweite Operand des `!` Operators ein gültiger Visual Basic Bezeichner sein muss, der nicht in doppelte Anführungszeichen () eingeschlossen ist `" "` . Anders ausgedrückt: Sie können keine Zeichenfolgenliterale oder Zeichen folgen Variable verwenden. Die folgende Änderung an der letzten Zeile des `MsgBox` Aufrufes generiert einen Fehler, da `"X"` ein eingeschlossenes zeichenfolgenliteralist.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> Verweise auf Standard Auflistungen müssen explizit sein. Insbesondere kann der- `!` Operator nicht für eine spät gebundene Variable verwendet werden.  
  
 Das `!` Zeichen wird auch als `Single` Typzeichen verwendet.  
  
## <a name="see-also"></a>Siehe auch

- [Programmstruktur und Codekonventionen](program-structure-and-code-conventions.md)
- [Typzeichen](../language-features/data-types/type-characters.md)
