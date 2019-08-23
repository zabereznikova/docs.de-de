---
title: Select...Case-Anweisung (Visual Basic)
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
ms.openlocfilehash: 627318677270ba4ffa8ee430febea7ddf83bd245
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957647"
---
# <a name="selectcase-statement-visual-basic"></a>Select...Case-Anweisung (Visual Basic)
Führt eine von mehreren Gruppen von Anweisungen aus, abhängig vom Wert eines Ausdrucks.  
  
## <a name="syntax"></a>Syntax  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`testexpression`|Erforderlich. Begriff. Muss zu einem der elementaren Datentypen ausgewertet werden (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, ,`String` ,`ULong`und). `UInteger` `UShort`|  
|`expressionlist`|Erforderlich in einer `Case` -Anweisung. Liste der Ausdrucks Klauseln, die die Übereinstimmungs Werte für `testexpression`darstellen. Mehrere Ausdrucks Klauseln werden durch Kommas getrennt. Jede Klausel kann eine der folgenden Formen annehmen:<br /><br /> -   *expression1* `To` *expression2*<br />-[ `Is` ] *ComparisonOperator* - *Ausdruck*<br />-   *Begriff*<br /><br /> Verwenden Sie `To` das-Schlüsselwort, um die Begrenzungen eines Bereichs von Übereinstimmungs Werten für `testexpression`anzugeben. Der Wert von `expression1` muss kleiner oder gleich dem Wert von `expression2`sein.<br /><br /> Verwenden Sie `Is` das-Schlüsselwort mit einem`=`Vergleichs `<>`Operator ( `<=`, `>`, `<`, `>=`, oder), um eine Einschränkung für die Übereinstimmungs Werte für `testexpression`anzugeben. Wenn das `Is` Schlüsselwort nicht angegeben wird, wird es automatisch vor *ComparisonOperator*eingefügt.<br /><br /> Das Formular, das `expression` nur angibt, wird als Sonderfall `Is` des Formulars behandelt, wobei *ComparisonOperator* das Gleichheits`=`Zeichen () ist. Dieses Formular wird als `testexpression`  =  `expression`ausgewertet.<br /><br /> Die Ausdrücke in `expressionlist` können einen beliebigen Datentyp aufweisen, vorausgesetzt, Sie können implizit in den Typ `testexpression` von konvertiert werden `comparisonoperator` , und der entsprechende ist für die beiden Typen gültig, mit denen Sie verwendet wird.|  
|`statements`|Optional. Mindestens eine-Anweisung nach `Case` der-Anweisung `testexpression` wird ausgeführt, wenn `expressionlist`mit einer Klausel in übereinstimmt.|  
|`elsestatements`|Optional. Eine oder mehrere der folgenden `Case Else` Anweisungen, die `testexpression` ausgeführt werden, wenn keiner der Klauseln `expressionlist` in `Case` der einer der Anweisungen entspricht.|  
|`End Select`|Beendet die Definition des `Select`... `Case` Konstruktion.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `testexpression` mit einer `Case` beliebigen `Case` `Case` `End Select` `Case Else`Klausel übereinstimmt, werden die Anweisungen, die auf diese Anweisung folgen, bis zur nächsten Anweisung, oder ausgeführt. `expressionlist` Dann übergibt die Steuerung an die folgende `End Select`Anweisung. Wenn `testexpression` `Case` einer `expressionlist` -Klausel in mehr als einer-Klausel entspricht, werden nur die Anweisungen nach der ersten Übereinstimmung ausgeführt.  
  
 Die `Case Else` -Anweisung wird verwendet, um `elsestatements` die zur Laufzeit einzuführen, wenn keine Entsprechung `testexpression` zwischen dem `expressionlist` und einer-Klausel in einer `Case` der anderen-Anweisungen gefunden wird. Obwohl es nicht erforderlich ist, empfiehlt es sich, eine `Case Else` -Anweisung in der `Select Case` Konstruktion zu haben, um unvorhergesehene `testexpression` Werte verarbeiten zu können. Wenn keine `Case` `testexpression` `Case Else` -Klausel übereinstimmt und keine-Anweisung vorhanden ist, wird die Steuerung `End Select`an die folgende Anweisung weitergeleitet. `expressionlist`  
  
 Sie können in jeder `Case` Klausel mehrere Ausdrücke oder Bereiche verwenden. Beispielsweise ist die folgende Zeile gültig.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> Das `Is` Schlüsselwort, das `Case` in `Case Else` den Anweisungen und verwendet wird, ist nicht identisch mit dem [is-Operator](../../../visual-basic/language-reference/operators/is-operator.md), der für den Objekt Verweis Vergleich verwendet wird.  
  
 Sie können Bereiche und mehrere Ausdrücke für Zeichen folgen angeben. Im folgenden Beispiel `Case` entspricht einer beliebigen Zeichenfolge, die exakt gleich "Äpfel" ist, einen Wert zwischen "Nüsse" und "Suppe" in alphabetischer Reihenfolge aufweist oder genau denselben Wert wie der aktuelle Wert von `testItem`enthält.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 Die Einstellung von `Option Compare` kann Zeichen folgen Vergleiche beeinflussen. Unter `Option Compare Text`werden die Zeichen folgen "Äpfel" und "Äpfel" als gleich, aber unter `Option Compare Binary`nicht angezeigt.  
  
> [!NOTE]
> Eine `Case` -Anweisung mit mehreren-Klauseln kann das Verhalten aufweisen, das als *Kurzschluss*bezeichnet wird. Visual Basic wertet die Klauseln von links nach rechts aus, und wenn eine Entsprechung mit `testexpression`ergibt, werden die restlichen Klauseln nicht ausgewertet. Kurzschluss kann die Leistung verbessern, kann jedoch zu unerwarteten Ergebnissen führen, wenn Sie erwarten, dass jeder `expressionlist` Ausdruck in ausgewertet wird. Weitere Informationen zum kurzen schließen finden Sie unter [boolesche Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Wenn der Code in einem `Case` - `Case Else` oder-Anweisungsblock keine weiteren Anweisungen im-Block ausführen muss, kann er den Block mithilfe der `Exit Select` -Anweisung beenden. Dadurch wird die Steuerung sofort an die folgende `End Select`Anweisung übertragen.  
  
 `Select Case`Konstruktionen können eingebettet werden. `Case Else` `End Select` `Case` Jede geschachtelte Konstruktion muss über eine übereinstimmende Anweisung verfügen und muss vollständig in einem einzelnen-oder- `Select Case` Anweisungsblock der äußeren Konstruktion enthalten sein, in der Sie geschachtelt ist. `Select Case`  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Select Case` -Konstruktion verwendet, um eine Zeile zu schreiben, die dem `number`Wert der-Variablen entspricht. Die zweite `Case` Anweisung enthält den Wert, der mit dem aktuellen Wert `number`von übereinstimmt, sodass die Anweisung, die "zwischen 6 und 8, inklusiv" schreibt, ausgeführt wird.  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)
- [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
