---
title: Select...Case-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
ms.openlocfilehash: 4dddfe5fbf7092c911291ffc6841e76f8c2748e9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352825"
---
# <a name="selectcase-statement-visual-basic"></a>Select...Case-Anweisung (Visual Basic)
Führt eine von mehreren Gruppen von Anweisungen aus, abhängig vom Wert eines Ausdrucks.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`testexpression`|Erforderlich Begriff. Muss zu einem der elementaren Datentypen (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`und `UShort`) ausgewertet werden.|  
|`expressionlist`|Erforderlich in einer `Case`-Anweisung. Liste der Ausdrucks Klauseln, die die Übereinstimmungs Werte für `testexpression`darstellen. Mehrere Ausdrucks Klauseln werden durch Kommas getrennt. Jede Klausel kann eine der folgenden Formen annehmen:<br /><br /> -   *expression1* `To` *expression2*<br />-[`Is`] *ComparisonOperator* - *Ausdruck*<br />-   *Ausdruck*<br /><br /> Verwenden Sie das `To`-Schlüsselwort, um die Grenzen eines Bereichs von Übereinstimmungs Werten für `testexpression`anzugeben. Der Wert `expression1` muss kleiner oder gleich dem Wert `expression2`sein.<br /><br /> Verwenden Sie das `Is`-Schlüsselwort mit einem Vergleichs Operator (`=`, `<>`, `<`, `<=`, `>`oder `>=`), um eine Einschränkung für die Übereinstimmungs Werte für `testexpression`anzugeben. Wenn das `Is`-Schlüsselwort nicht angegeben wird, wird es automatisch vor *ComparisonOperator*eingefügt.<br /><br /> Das Formular, das nur `expression` angibt, wird als Sonderfall des `Is` Formulars behandelt, wobei *ComparisonOperator* das Gleichheitszeichen (`=`) ist. Dieses Formular wird als `testexpression` = `expression`ausgewertet.<br /><br /> Die Ausdrücke in `expressionlist` können einen beliebigen Datentyp aufweisen, vorausgesetzt, Sie können implizit in den Typ der `testexpression` konvertiert werden, und die entsprechende `comparisonoperator` ist für die beiden Typen gültig, mit denen Sie verwendet wird.|  
|`statements`|Optional. Eine oder mehrere Anweisungen nach `Case`, die ausgeführt werden, wenn `testexpression` mit einer Klausel in `expressionlist`übereinstimmt.|  
|`elsestatements`|Optional. Eine oder mehrere Anweisungen nach `Case Else`, die ausgeführt werden, wenn `testexpression` keiner Klausel im `expressionlist` der `Case` Anweisungen entspricht.|  
|`End Select`|Beendet die Definition der `Select`...`Case` Konstruktion.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `testexpression` mit einer `Case` `expressionlist`-Klausel übereinstimmt, werden die Anweisungen, die dieser `Case` Anweisung folgen, bis zur nächsten `Case`-, `Case Else`-oder `End Select`-Anweisung ausgeführt. Das Steuerelement übergibt dann an die Anweisung nach `End Select`. Wenn `testexpression` einer `expressionlist`-Klausel in mehr als einer `Case`-Klausel entspricht, werden nur die Anweisungen nach der ersten Übereinstimmung ausgeführt.  
  
 Die `Case Else`-Anweisung wird verwendet, um die auszuführenden `elsestatements` einzuführen, wenn keine Entsprechung zwischen dem `testexpression` und einer `expressionlist`-Klausel in einer der anderen `Case` Anweisungen gefunden wird. Obwohl es nicht erforderlich ist, empfiehlt es sich, eine `Case Else`-Anweisung in ihrer `Select Case` Konstruktion zu haben, um unvorhergesehene `testexpression` Werte zu verarbeiten. Wenn keine `Case` `expressionlist`-Klausel mit `testexpression` übereinstimmt und keine `Case Else`-Anweisung vorhanden ist, wird die Steuerung an die Anweisung nach `End Select`weitergeleitet.  
  
 In jeder `Case`-Klausel können mehrere Ausdrücke oder Bereiche verwendet werden. Beispielsweise ist die folgende Zeile gültig.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> Das `Is`-Schlüsselwort, das in den `Case`-und `Case Else`-Anweisungen verwendet wird, ist nicht identisch mit dem [is-Operator](../../../visual-basic/language-reference/operators/is-operator.md), der für den Objekt Verweis Vergleich verwendet wird.  
  
 Sie können Bereiche und mehrere Ausdrücke für Zeichen folgen angeben. Im folgenden Beispiel entspricht `Case` einer beliebigen Zeichenfolge, die genau gleich "Äpfel" ist, einen Wert zwischen "Nüsse" und "Suppe" in alphabetischer Reihenfolge aufweist oder genau denselben Wert wie der aktuelle Wert `testItem`enthält.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 Die Einstellung von `Option Compare` kann sich auf Zeichen folgen Vergleiche auswirken. Unter `Option Compare Text`vergleichen die Zeichen folgen "Äpfel" und "Äpfel" als identisch, unter `Option Compare Binary`jedoch nicht.  
  
> [!NOTE]
> Eine `Case`-Anweisung mit mehreren Klauseln kann das Verhalten aufweisen, das als *Kurzschluss*bezeichnet wird. Visual Basic wertet die Klauseln von links nach rechts aus, und wenn eine Entsprechung mit `testexpression`ergibt, werden die restlichen Klauseln nicht ausgewertet. Kurzschluss kann die Leistung verbessern, kann jedoch zu unerwarteten Ergebnissen führen, wenn Sie erwarten, dass jeder Ausdruck in `expressionlist` ausgewertet wird. Weitere Informationen zum kurzen schließen finden Sie unter [boolesche Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Wenn der Code in einem `Case`-oder `Case Else`-Anweisungsblock keine weiteren Anweisungen im-Block ausführen muss, kann er den Block mithilfe der `Exit Select`-Anweisung beenden. Dadurch wird die Steuerung sofort an die Anweisung nach `End Select`übertragen.  
  
 `Select Case` Konstruktionen können eingebettet werden. Jede geschachtelte `Select Case` Konstruktion muss über eine übereinstimmende `End Select` Anweisung verfügen und muss vollständig in einem einzelnen `Case` oder `Case Else` Anweisungsblock der äußeren `Select Case` Konstruktion enthalten sein, in der Sie geschachtelt ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Select Case` Konstruktion verwendet, um eine Zeile zu schreiben, die dem Wert der Variablen `number`entspricht. Die zweite `Case`-Anweisung enthält den Wert, der mit dem aktuellen Wert von `number`übereinstimmt, sodass die Anweisung, die "between 6 und 8, inclusive" schreibt, ausgeführt wird.  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)
- [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
