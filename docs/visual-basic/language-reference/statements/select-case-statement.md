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
ms.openlocfilehash: 9d24b455d92cbd00b268df26283aab082b7703a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604574"
---
# <a name="selectcase-statement-visual-basic"></a>Select...Case-Anweisung (Visual Basic)
Führt eine von mehreren Gruppen von Anweisungen, je nach dem Wert eines Ausdrucks.  
  
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
|`testexpression`|Erforderlich. Ausdruck. Muss auf einen der elementare Datentypen ausgewertet werden (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, und `UShort`).|  
|`expressionlist`|Erforderlich eine `Case` Anweisung. Liste der Expression-Klauseln darstellt übereinstimmenden Werte für `testexpression`. Mehrere Ausdrucksklauseln werden durch Kommas getrennt. Jede Klausel kann einen der folgenden Formen annehmen:<br /><br /> -   *expression1* `To` *expression2*<br />-[ `Is` ] *Vergleichsoperator* *Ausdruck*<br />-   *Ausdruck*<br /><br /> Verwenden der `To` Schlüsselwort, um die Grenzen eines Bereichs von Übereinstimmung geben Werte für `testexpression`. Der Wert der `expression1` muss kleiner oder gleich dem Wert des `expression2`.<br /><br /> Verwenden der `Is` Schlüsselwort mit einem Vergleichsoperator (`=`, `<>`, `<`, `<=`, `>`, oder `>=`) auf den übereinstimmenden Werte für eine Einschränkung angegeben `testexpression`. Wenn die `Is` -Schlüsselwort nicht angegeben wird, wird Sie automatisch vor eingefügt *Vergleichsoperator*.<br /><br /> Nur `expression` wird als ein Sonderfall des behandelt die `Is` bilden Where *Vergleichsoperator* ist das Gleichheitszeichen (`=`). Dieses Formular wird ausgewertet, als `testexpression`  =  `expression`.<br /><br /> Die Ausdrücke in `expressionlist` kann einen beliebigen Datentyp aufweisen, vorausgesetzt, dass sie implizit in den Typ des `testexpression` und dem entsprechenden `comparisonoperator` ist gültig für die beiden Typen, die es mit verwendet wird.|  
|`statements`|Dies ist optional. Eine oder mehrere Anweisungen nach `Case` , ausgeführt werden, wenn `testexpression` entspricht jede beliebige Klausel in `expressionlist`.|  
|`elsestatements`|Dies ist optional. Eine oder mehrere Anweisungen nach `Case Else` , ausgeführt werden, wenn `testexpression` entspricht nicht jede beliebige Klausel in der `expressionlist` aller der `Case` Anweisungen.|  
|`End Select`|Beendet die Definition des der `Select`... `Case` Konstruktion.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn `testexpression` beliebige `Case` `expressionlist` -Klausel, die Anweisungen befolgen, die `Case` -Anweisung, die Sie zur nächsten Ausführen `Case`, `Case Else`, oder `End Select` Anweisung. Anschließend wird die folgende Anweisung die Steuerung `End Select`. Wenn `testexpression` entspricht einer `expressionlist` -Klausel in mehr als eine `Case` -Klausel, um nur die Anweisungen nach der ersten Übereinstimmung führen.  
  
 Die `Case Else` -Anweisung wird zum Einführen der `elsestatements` ausführen, wenn keine Übereinstimmung, zwischen gefunden wird den `testexpression` und ein `expressionlist` -Klausel in eine beliebige andere `Case` Anweisungen. Ist zwar nicht erforderlich Es empfiehlt sich, Sie haben, eine `Case Else` -Anweisung in Ihre `Select Case` -Konstruktion behandeln unvorhergesehene `testexpression` Werte. Wenn kein `Case` `expressionlist` Klausel entspricht `testexpression` und es gibt keine `Case Else` Anweisung Steuerelement übergibt die folgende Anweisung `End Select`.  
  
 Sie können mehrere Ausdrücke oder Bereiche in den einzelnen `Case` Klausel. Die folgende Zeile ist z. B. gültig.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  Die `Is` Schlüsselwort in der `Case` und `Case Else` Anweisungen ist nicht identisch mit der [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md), die für den Vergleich von Objektverweisen verwendet wird.  
  
 Sie können Bereiche und mehrere Ausdrücke für Zeichenfolgen angeben. Im folgenden Beispiel `Case` entspricht jeder Zeichenfolge, die "Äpfel" genau gleich ist, verfügt über einen Wert zwischen "Nüsse" und "Suppe" in alphabetischer Reihenfolge oder enthält genauen denselben Wert wie der aktuelle Wert der `testItem`.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 Die Einstellung der `Option Compare` Zeichenfolgenvergleiche auswirken können. Klicken Sie unter `Option Compare Text`, die Zeichenfolgen "Apples" und "Apples" bei einem Vergleich gleich, jedoch unter `Option Compare Binary`, nicht der Fall ist.  
  
> [!NOTE]
>  Ein `Case` ausgesondert, und als eine Anweisung mit mehreren Klauseln *verkürzte*. Visual Basic wertet die Klauseln von links nach rechts, und wenn mindestens eine erzeugt eine Übereinstimmung mit `testexpression`, die verbleibenden Klauseln werden nicht ausgewertet. Verkürzte kann die Leistung verbessern, aber es kann zu unerwarteten Ergebnissen führen, wenn erwartet jeder Ausdruck in wird `expressionlist` ausgewertet werden soll. Weitere Informationen über Kurzschlussverhalten finden Sie unter [boolesche Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Wenn der Code innerhalb einer `Case` oder `Case Else` -Anweisungsblock muss nicht mehr der Anweisungen im Block ausgeführt, beendet den Block kann mithilfe der `Exit Select` Anweisung. Dies überträgt die Steuerung sofort an die Anweisung nach `End Select`.  
  
 `Select Case` Konstruktionen können geschachtelt werden. Jede geschachtelte `Select Case` Konstruktion benötigen einen übereinstimmenden `End Select` Anweisung und muss vollständig in einer einzelnen enthalten `Case` oder `Case Else` Anweisungsblock des äußeren `Select Case` Konstruktion, in dem sie geschachtelt ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Select Case` Konstruktion, um eine Zeile entsprechend dem Wert der Variablen schreiben `number`. Die zweite `Case` -Anweisung enthält den Wert, der den aktuellen Wert der entspricht `number`, sodass die Anweisung, die "zwischen 6 und 8, inclusive" schreibt ausgeführt wird.  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/select-case-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)  
 [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
