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
ms.openlocfilehash: 750e765390ad223976b000fe64e656fa2d62a34b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871786"
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
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`testexpression`|Erforderlich. Ausdruck Muss einen der elementaren Datentypen ( `Boolean` , `Byte` , `Char` , `Date` , `Double` , `Decimal` , `Integer` , `Long` , `Object` , `SByte` , `Short` , `Single` , `String` , `UInteger` , `ULong` und `UShort` ) auswerten.|  
|`expressionlist`|Erforderlich in einer- `Case` Anweisung. Liste der Ausdrucks Klauseln, die die Übereinstimmungs Werte für darstellen `testexpression` . Mehrere Ausdrucks Klauseln werden durch Kommas getrennt. Jede Klausel kann eine der folgenden Formen annehmen:<br /><br /> -   *expression1* `To` *expression2*<br />-[ `Is` ] *ComparisonOperator* - *Ausdruck*<br />-   *Begriff*<br /><br /> Verwenden Sie das- `To` Schlüsselwort, um die Begrenzungen eines Bereichs von Übereinstimmungs Werten für anzugeben `testexpression` . Der Wert von `expression1` muss kleiner oder gleich dem Wert von sein `expression2` .<br /><br /> Verwenden Sie das- `Is` Schlüsselwort mit einem Vergleichs Operator ( `=` , `<>` , `<` , `<=` , `>` oder `>=` ), um eine Einschränkung für die Übereinstimmungs Werte für anzugeben `testexpression` . Wenn das `Is` Schlüsselwort nicht angegeben wird, wird es automatisch vor *ComparisonOperator*eingefügt.<br /><br /> Das Formular, das nur angibt, `expression` wird als Sonderfall des `Is` Formulars behandelt, wobei *ComparisonOperator* das Gleichheitszeichen ( `=` ) ist. Dieses Formular wird als ausgewertet `testexpression`  =  `expression` .<br /><br /> Die Ausdrücke in `expressionlist` können einen beliebigen Datentyp aufweisen, vorausgesetzt, Sie können implizit in den Typ von konvertiert werden, `testexpression` und der entsprechende `comparisonoperator` ist für die beiden Typen gültig, mit denen Sie verwendet wird.|  
|`statements`|Dies ist optional. Mindestens eine-Anweisung nach `Case` der-Anweisung wird ausgeführt, wenn `testexpression` mit einer Klausel in übereinstimmt `expressionlist` .|  
|`elsestatements`|Dies ist optional. Eine oder mehrere der folgenden Anweisungen `Case Else` , die ausgeführt werden, wenn `testexpression` keiner der Klauseln in der einer der `expressionlist` Anweisungen entspricht `Case` .|  
|`End Select`|Beendet die Definition der `Select` ...- `Case` Konstruktion.|  
  
## <a name="remarks"></a>Bemerkungen  

 Wenn `testexpression` mit einer beliebigen Klausel übereinstimmt `Case` `expressionlist` , werden die Anweisungen, die auf diese Anweisung folgen, `Case` bis zur nächsten `Case` Anweisung, oder ausgeführt `Case Else` `End Select` . Dann übergibt die Steuerung an die folgende Anweisung `End Select` . Wenn `testexpression` einer- `expressionlist` Klausel in mehr als einer- `Case` Klausel entspricht, werden nur die Anweisungen nach der ersten Übereinstimmung ausgeführt.  
  
 Die `Case Else` -Anweisung wird verwendet, um die `elsestatements` zur Laufzeit einzuführen, wenn keine Entsprechung zwischen dem `testexpression` und einer- `expressionlist` Klausel in einer der anderen-Anweisungen gefunden wird `Case` . Obwohl es nicht erforderlich ist, empfiehlt es sich, eine- `Case Else` Anweisung in der `Select Case` Konstruktion zu haben, um unvorhergesehene Werte verarbeiten zu können `testexpression` . Wenn keine `Case` `expressionlist` -Klausel übereinstimmt `testexpression` und keine-Anweisung vorhanden ist `Case Else` , wird die Steuerung an die folgende Anweisung weitergeleitet `End Select` .  
  
 Sie können in jeder Klausel mehrere Ausdrücke oder Bereiche verwenden `Case` . Beispielsweise ist die folgende Zeile gültig.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> Das `Is` Schlüsselwort, das in den `Case` Anweisungen und verwendet wird `Case Else` , ist nicht identisch mit dem [is-Operator](../operators/is-operator.md), der für den Objekt Verweis Vergleich verwendet wird.  
  
 Sie können Bereiche und mehrere Ausdrücke für Zeichen folgen angeben. Im folgenden Beispiel entspricht einer `Case` beliebigen Zeichenfolge, die exakt gleich "Äpfel" ist, einen Wert zwischen "Nüsse" und "Suppe" in alphabetischer Reihenfolge aufweist oder genau denselben Wert wie der aktuelle Wert von enthält `testItem` .  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 Die Einstellung von `Option Compare` kann Zeichen folgen Vergleiche beeinflussen. Unter `Option Compare Text` werden die Zeichen folgen "Äpfel" und "Äpfel" als gleich, aber unter `Option Compare Binary` nicht angezeigt.  
  
> [!NOTE]
> Eine- `Case` Anweisung mit mehreren-Klauseln kann das Verhalten aufweisen, das als *Kurzschluss*bezeichnet wird. Visual Basic wertet die Klauseln von links nach rechts aus, und wenn eine Entsprechung mit ergibt `testexpression` , werden die restlichen Klauseln nicht ausgewertet. Kurzschluss kann die Leistung verbessern, kann jedoch zu unerwarteten Ergebnissen führen, wenn Sie erwarten, dass jeder Ausdruck in `expressionlist` ausgewertet wird. Weitere Informationen zum kurzen schließen finden Sie unter [boolesche Ausdrücke](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Wenn der Code in einem- `Case` oder- `Case Else` Anweisungsblock keine weiteren Anweisungen im-Block ausführen muss, kann er den Block mithilfe der- `Exit Select` Anweisung beenden. Dadurch wird die Steuerung sofort an die folgende Anweisung übertragen `End Select` .  
  
 `Select Case` Konstruktionen können eingebettet werden. Jede geschachtelte `Select Case` Konstruktion muss über eine übereinstimmende `End Select` Anweisung verfügen und muss vollständig in einem einzelnen- `Case` oder- `Case Else` Anweisungsblock der äußeren Konstruktion enthalten sein `Select Case` , in der Sie geschachtelt ist.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine- `Select Case` Konstruktion verwendet, um eine Zeile zu schreiben, die dem Wert der-Variablen entspricht `number` . Die zweite `Case` Anweisung enthält den Wert, der mit dem aktuellen Wert von übereinstimmt `number` , sodass die Anweisung, die "zwischen 6 und 8, inklusiv" schreibt, ausgeführt wird.  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End Statement](end-statement.md)
- [If...Then...Else-Anweisung](if-then-else-statement.md)
- [Option Compare-Anweisung](option-compare-statement.md)
- [Exit-Anweisung](exit-statement.md)
