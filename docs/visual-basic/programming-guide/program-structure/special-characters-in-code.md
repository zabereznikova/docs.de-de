---
title: Sonderzeichen in Code (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
dev_langs:
- VB
helpviewer_keywords:
- special characters, in code
- parentheses, using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator
- concatenation operators, special characters in code
- concatenation operators, vs. addition operator
- '! operator'
- separators, using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator
- addition operator
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6d4b6e74ef3dfab3a7174da07cff7100fa4b2a2f
ms.lasthandoff: 03/13/2017

---
# <a name="special-characters-in-code-visual-basic"></a>Sonderzeichen in Code (Visual Basic)
Manchmal müssen Sie Sonderzeichen in Ihrem Code, d. h. Zeichen verwenden, die nicht alphabetisch oder numerisch sind. Interpunktion und Sonderzeichen in den [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Zeichensatz haben verschiedene Funktionen, vom verwalten Programmtext zur Definition der Aufgaben, die der Compiler oder das kompilierte Programm ausführt. Sie legen keine auszuführende Operation fest.  
  
## <a name="parentheses"></a>Klammern  
 Verwenden Sie Klammern bei der Definition einer Prozedur, z. B. ein `Sub` oder `Function`. Sie müssen alle Verfahren Argumentlisten in Klammern einschließen. Sie verwenden auch Klammern zum Einfügen von Variablen oder Argumente in logischen Gruppen, die insbesondere für die Rangfolge der Operatoren in einem komplexen Ausdruck überschreiben. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbcnConventions&#11;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 Nach der Ausführung des vorherigen Code den Wert der `d` "8.225" und der Wert des `e` ist 3. Die Berechnung für `d` verwendet die standardmäßige Rangfolge `/` über `+` und entspricht dem `d = b + (c / a)`. Die Klammern in der Berechnung von `e` außer Kraft setzen der Standardvorrang gilt.  
  
## <a name="separators"></a>Trennzeichen  
 Trennzeichen sind, was ihr Name besagt: Trennen Sie Abschnitte des Codes. In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], das Trennzeichen ist der Doppelpunkt (`:`). Verwenden Sie als Trennzeichen, wenn mehrere Anweisungen in einer einzelnen Zeile anstelle von separaten Zeilen enthalten sein sollen. Dies spart Platz und verbessert die Lesbarkeit des Codes. Das folgende Beispiel zeigt drei Anweisungen, die durch Doppelpunkte getrennt.  
  
 [!code-vb[VbVbcnConventions&#12;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 Weitere Informationen finden Sie unter [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
 Der Doppelpunkt (`:`)-Zeichen wird auch verwendet, um eine Anweisungsmarke zu identifizieren. Weitere Informationen finden Sie unter [wie: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
## <a name="concatenation"></a>Verkettung  
 Verwenden der `&` Operator für *Verkettung*, oder Verknüpfen von Zeichenfolgen. Ist nicht zu verwechseln mit der `+` -Operator, der numerische Werte addiert. Bei Verwendung der `+` Operator verkettet wird, wenn Sie mit numerischen Werten arbeiten Sie falsche Ergebnisse erhalten. Das folgende Beispiel veranschaulicht das.  
  
 [!code-vb[VbVbcnConventions&#13;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 Nach der Ausführung des vorherigen Code den Wert der `resultA` 21.01 und der Wert des `resultB` "10.0111".  
  
## <a name="member-access-operators"></a>Operatoren für den Memberzugriff  
 Zugriff auf einen Member eines Typs, verwenden Sie den Punkt (`.`) oder ein Ausrufezeichen (`!`)-Operator zwischen dem Typnamen und den Elementnamen.  
  
### <a name="dot--operator"></a>Punkt (.) Operator  
 Verwenden der `.` Operator auf eine Klasse, Struktur, Schnittstelle oder Enumeration als Operator für den Memberzugriff. Das Element kann ein Feld, Eigenschaft, Ereignis oder Methode. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
 [!code-vb[VbVbcnConventions&14;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a>Ausrufezeichen (!) Operator  
 Verwenden der `!` Operator nur auf eine Klasse oder Schnittstelle als Operator für den Wörterbuchzugriff. Die Klasse oder Schnittstelle müssen eine Default-Eigenschaft, die ein einzelnes akzeptiert `String` Argument. Der Bezeichner direkt nach dem `!` Operator wird der Wert des Arguments an die Standardeigenschaft als Zeichenfolge übergeben. Das folgende Beispiel veranschaulicht das.  
  
 [!code-vb[VbVbcnConventions&#15;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 Die drei Zeilen der Ausgabe `MsgBox` alle zeigt den Wert `32856`. Die erste Zeile wird der herkömmliche Zugriff auf Eigenschaft verwendet `index`, die zweite nutzt die Tatsache, `index` ist die Standardeigenschaft der Klasse `hasDefault`, und die dritte Wörterbuchzugriff auf die Klasse verwendet.  
  
 Beachten Sie, dass der zweite Operand des der `!` Operator muss ein gültiger Visual Basic-Bezeichner nicht in Anführungszeichen eingeschlossen sein (`" "`). Sie können nicht in anderen Worten, ein Zeichenfolgenliteral oder eine String-Variable verwenden. Die folgende Änderung der letzten Zeile der `MsgBox` Aufruf wird ein Fehler generiert, da `"X"` ist eine eingeschlossene Zeichenfolgenliteral.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  Verweise auf Standardsammlungen müssen explizit erfolgen. Insbesondere können keine der `!` Operator auf eine spät gebundene Variable.  
  
 Die `!` Zeichen dient auch als die `Single` Zeichen eingeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
